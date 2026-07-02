---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Kubernetes Provisionamento de cluster"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "product/k8s-cluster-provisioning.html"
images:
  - "images/container-ua-1.png"
  - "images/container-ua-12.png"
  - "images/container-ua-13.png"
  - "images/container-ua-14.png"
  - "images/container-ua-15.png"
  - "images/container-ua-16.png"
  - "images/container-ua-2.png"
  - "images/container-ua-3.png"
  - "images/container-ua-4.png"
  - "images/container-ua-5.png"
  - "images/container-ua-6.png"
  - "images/container-ua-7.png"
  - "images/container-ua-8.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Kubernetes Provisionamento de cluster

Para coletar os dados necessários para realizar a alocação de custos de contêineres, você precisará implantar o *IBM FinOps Agent*, o agente de coleta de dados de última geração para o Cloudability Containers. Neste documento, você encontrará referências relacionadas a um cenário de migração do agente de métricas antigo do Cloudability; caso esteja realizando o provisionamento pela primeira vez, pode ignorar essas informações.

Configurar o [Agente do IBM FinOps](https://github.com/kubecost/finops-agent-chart/blob/main/charts/finops-agent/README.md "(Abre em uma nova guia ou janela)") para o Cloudability

Isso é obtido por meio de uma implementação do HELM provisionada para cada cluster. Esses comandos HELM podem ser gerados seguindo estas etapas:

1. Navegue até **Insights > Contêineres**.
2. Selecione o botão “**Provisionar clusters** ”.
3. Preencha o formulário com o nome do seu cluster e indique se está usando a versão Kubernetes ou a versão *OpenShift*.
4. Clique em **Avançar > Gerar comando**.

Implantar o Unified Agent

Pré-requisitos:

Google Kubernetes Engine ( GKE ) instruções específicas

Você precisa adicionar uma [etiqueta de cluster](https://cloud.google.com/kubernetes-engine/docs/how-to/creating-managing-labels "(Abre em uma nova guia ou janela)") em cada cluster da seguinte forma:

- Legenda: `gke-cluster`
- Valor: O nome do cluster que você definiu no ` Helm ` como o ID do cluster. Isso permite que o Cloudability mapeie os clusters do GKE para itens de linha no arquivo de faturamento do GCP e aloque custos aos seus clusters. Ele deve ser único em todos os seus clusters provisionados pelo GKE.

Cloudability será necessário importar um arquivo de faturamento com as etiquetas do cluster que você adicionou, o que pode levar até 48 horas. Assim que o Apptio tiver processado o novo arquivo de faturamento, você precisará criar um novo [mapeamento de tags](build-an-aws-cost-by-tag-report.html) no Cloudability. Defina uma dimensão de tag do Cloudability como “Nome do cluster do GKE ” e associe-a à `gke-cluster` tag.

Certifique-se de que sua conta tenha a função de administrador de cluster antes de implantar o agente de métricas. Por padrão, uma conta de usuário não tem a função de administrador de cluster. Execute o seguinte comando no cluster GKE para conceder a função cluster-admin a um usuário:

```
"kubectl create clusterrolebinding username-cluster-admin-binding --
clusterrole=cluster-admin --user=username@emailaddress.com"
```

**Requisitos de rede**

O agente unificado requer acesso de saída aos seguintes locais:

- Cloudability Pontos de extremidade da API
- Pontos de extremidade da API do Frontdoor
- S3 Buckets de upload

Para obter detalhes sobre a rede de saída, consulte o arquivo README em GitHub para o agente unificado aqui: [IBM Gráfico do FinOps Agent Helm](https://github.com/kubecost/finops-agent-chart/blob/main/charts/finops-agent/README.md "(Abre em uma nova guia ou janela)")

**Requisitos de armazenamento:**

O agente do IBM FinOps requer uma reivindicação de volume persistente configurável (padrão: 8Gi ). Essa alteração foi feita para reduzir a chance de perda de dados se/quando o agente for reprogramado. O agente agora armazena amostras nesse volume e tentará recuperar quaisquer amostras após uma reinicialização. Esse aprimoramento melhora muito a capacidade do agente de recuperar dados em cenários de falha.

**Container Registry mudança:**

O agente IBM FinOps não é armazenado no Docker, ao contrário do agente de métricas existente. Em vez disso, o agente IBM FinOps é armazenado no ICR. Portanto, talvez seja necessário atualizar a lista de permissões do seu registro de contêineres para permitir que a implantação do Agente IBM FinOps baixe a imagem ICR. O registro de contêineres do IBM FinOps Agent é:

```
icr.io/ibm-finops/agent:vx.x.x
```

Se precisar extrair a imagem localmente para copiar para o registro do contêiner. Você pode executar o seguinte comando docker/podman pull:

```
 podman pull icr.io/ibm-finops/agent:v0.0.25 --platform=linux/amd64
```

**Autenticação:**

É importante ressaltar que o agente de métricas antigo do Cloudability utilizava uma chave de API específica para contêineres. O Agente do IBM FinOps **não utilizará nem oferecerá suporte a essa chave de API**. Em vez disso, os clientes precisam criar uma **chave de API** para o agente no Frontdoor e reunir sua **ID de ambiente** do Frontdoor.

**Criação de usuário para gerenciar a chave de API do contêiner:**

É necessário que as chaves de API estejam ativadas no seu ambiente Frontdoor para que o recurso Container Insights funcione

Recomenda-se que os clientes criem um usuário de "conta de serviço" específico para o contêiner dentro de seu próprio domínio para gerenciar sua chave de API daqui em diante. Dessa forma, a chave da API de upload não fica associada a um usuário específico que possa ser desativado no futuro. A pessoa responsável pela criação do novo usuário e da chave de API precisa ser um usuário administrador no ambiente Frontdoor.

1. Navegue até "Access Wizard" (Assistente de acesso) em "Access Administration" (Administração de acesso), selecione "Add User(s)" (Adicionar usuário(s)), defina "Customer" (Cliente) e "Environment" (Ambiente). Por fim, pressione "Confirm" (Confirmar)

   ![](../../../../03-media/cloudability-premium/images/container-ua-1.png)
2. Insira as informações do usuário e pressione "Next" (Avançar)

   ![](../../../../03-media/cloudability-premium/images/container-ua-2.png)
3. Selecione "Grant Role(s)" (Conceder função), "Do not send User an activation Email" (Não enviar e-mail de ativação ao usuário) e clique em "Confirm" (Confirmar) para criar o usuário

   ![](../../../../03-media/cloudability-premium/images/container-ua-3.png)
4. Certifique-se de que o usuário esteja selecionado para conceder funções

   ![](../../../../03-media/cloudability-premium/images/container-ua-4.png)
5. Conceda a função “CloudabilityContainerUploader” ao usuário e clique em "Next"/"Confirm".

   ![](../../../../03-media/cloudability-premium/images/container-ua-5.png)
6. Navegue até "Home", procure o usuário recém-criado e clique em seu "Username" (Nome de usuário)

   ![](../../../../03-media/cloudability-premium/images/container-ua-6.png)
7. Clique em "View User Profile" (Exibir perfil do usuário)

   ![](../../../../03-media/cloudability-premium/images/container-ua-7.png)
8. Adicionar uma chave de API para o usuário

   ![](../../../../03-media/cloudability-premium/images/container-ua-8.png)
9. Digite um nome para a chave de API (por exemplo: IBM -Finops-agent), defina "No Expiration" (Sem expiração) se ainda não estiver definido e pressione confirmar.
10. Armazene as credenciais da chave de API (**chave pública** e **chave privada** ) para serem usadas posteriormente na instalação do helm do agente.
11. Pressione "Grant Access" (Conceder acesso)
12. Selecione seu ambiente e clique em "Next" (Avançar)

    ![](../../../../03-media/cloudability-premium/images/container-ua-12.png)
13. Adicione a função “CloudabilityContainerUploader” à chave e clique em "Next" (Avançar). Essa função tem acesso limitado ao endpoint de upload de contêineres.

    ![](../../../../03-media/cloudability-premium/images/container-ua-13.png)
14. Verifique se sua chave foi criada e se tem a função correta

    ![](../../../../03-media/cloudability-premium/images/container-ua-14.png)

**Coleta de ID de ambiente de porta de entrada**

1. Navegue até Frontdoor
2. No canto superior direito, selecione o logotipo Profile (Perfil) e clique em "User Account" (Conta de usuário)

   ![](../../../../03-media/cloudability-premium/images/container-ua-15.png)
3. Navegue até a guia Acesso ao ambiente
4. Obtenha o ID do ambiente na guia Ambiente da tabela

   1. Garantir que o ambiente seja o mesmo que você usa para acessar Cloudability

      ![](../../../../03-media/cloudability-premium/images/container-ua-16.png)
   2. Exemplo de formato de ID: `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`

Implantação do metrics-agent com o ` Helm `

Pré-requisitos:

- Instalação: é necessário instalar o pacote “ [Helm](https://www.ibm.com/links?url=https%3A%2F%2Fhelm.sh%2F "(Abre em uma nova guia ou janela)") ” para utilizar os gráficos. Consulte [a documentação](https://www.ibm.com/links?url=https://helm.sh/docs/ "(Abre em uma nova guia ou janela)") do Helm para começar.
- Atualizar as políticas de rede do cluster para permitir os novos requisitos de rede (se necessário)
- Reunir chaves públicas e privadas da API
- Coletar ID do ambiente da porta de entrada

Importante:

Recomendamos enfaticamente o uso de um nome exclusivo `clusterId` (nome do cluster) para cada cluster do Kubernetes. O uso de nomes duplicados pode causar discrepâncias nos dados ou uma alocação de custos imprecisa nos relatórios d Cloudability.

Depois que o site Helm tiver sido configurado corretamente, adicione o repositório da seguinte forma:

```
helm repo add ibm-finops https://kubecost.github.io/finops-agent-chart
```

Se você já adicionou esse repositório anteriormente, atualize-o:

```
helm repo update
```

Instalar o Helm Repo

```
helm install ibm-finops-agent ibm-finops/finops-agent \   
--set agent.cloudability.enabled=true \
--set agent.cloudability.uploadRegion=<uploadRegion> \      
--set agent.cloudability.parseMetricData=false \
--set agent.cloudability.secret.create=true \
--set agent.cloudability.secret.cloudabilityAccessKey="<PublicKey>" \
--set agent.cloudability.secret.cloudabilitySecretKey="<PrivateKey>" \
--set agent.cloudability.secret.cloudabilityEnvId="<FDEnvID>" \
--set clusterId="<ClusterName>" \
--create-namespace -n ibm-finops-agent
```

Para desinstalar o Helm Repo:

```
helm uninstall ibm-finops-agent
```

Se o seu cluster estiver executando atualmente o antigo agente de métricas Cloudability, fique à vontade para mantê-lo em execução até que o novo agente FinOps IBM comece a fazer uploads com sucesso por 24 horas. O agente IBM FinOps pode ser instalado e executado em paralelo ao agente de métricas Cloudability, mas recomenda-se desativar o agente de métricas Cloudability assim que o novo agente estiver estável no seu cluster.

**UploadRegion** depende da região em que se encontra o ambiente Cloudability do cliente. Os valores suportados são os seguintes

- EUA: us (ou us-west-2 )
- UE: eu (ou eu-central-1 )
- AU: au (ou ap-southeast-2 )
- ME: eu (ou me-central-1 )
- CA: ca (ou ca-central-1 )
- Hybrid EU *(clientes que têm frontdoor da UE, mas fazem upload de dados de contêineres para a região dos EUA)* : hybrid-eu
- AU híbrido *(clientes que têm frontdoor AU, mas fazem upload de dados de contêineres para a região dos EUA):* hybrid-au
- ME híbrido *(clientes que têm frontdoor ME, mas fazem upload de dados de contêineres para a região dos EUA)* : hybrid-me

O nome do `clusterId` cluster deve ser único e, caso tenha sido provisionado anteriormente pelo agente de métricas legado, deve corresponder ao nome do cluster `CLOUDABILITY_CLUSTER_NAME` **para evitar quaisquer problemas na ingestão de custos**.

Nota:

O agente unificado suporta muitas das mesmas configurações do agente de métricas de saída Cloudability. Caso seu agente de métricas atual tenha alguma configuração específica **(por exemplo, configurações de PROXY)**, consulte [aqui](https://github.com/kubecost/finops-agent-chart/blob/main/charts/finops-agent/README.md#:~:text=%22%22-,Agent%20Configuration,-Name "(Abre em uma nova guia ou janela)") os parâmetros suportados pelo Helm.

Você pode adicioná-los ao seu comando de instalação, por exemplo:

```
helm install ibm-finops-agent ibm-finops/finops-agent \   
--set agent.cloudability.enabled=true \
--set agent.cloudability.uploadRegion=<uploadRegion> \      
--set agent.cloudability.parseMetricData=false \
--set agent.cloudability.secret.create=true \
--set agent.cloudability.secret.cloudabilityAccessKey="<PublicKey>" \
--set agent.cloudability.secret.cloudabilitySecretKey="<PrivateKey>" \
--set agent.cloudability.secret.cloudabilityEnvId="<FDEnvID>" \
--set agent.cloudability.outboundProxy="http://x.x.x.x:8080" \
--set agent.cloudability.parseMetricsData="true"
--set clusterId="<ClusterName>" \
--create-namespace -n ibm-finops-agent
```

1. Certifique-se de que o pod ibm-finops-agent esteja em execução

   ```
   kubectl get pods -n ibm-finops-agent

   ### Example Output Below ###
   NAME                                READY   STATUS    RESTARTS   AGE
   ibm-finops-agent-7bbf99d9fb-kmhh9   1/1     Running   0          1m
   ```
2. Verifique os registros dos pods para confirmar que o agente está carregando dados com êxito em Cloudability. **Levará 10 minutos para ver o primeiro registro de upload bem-sucedido.**

   ```
   kubectl logs <POD_NAME> -n ibm-finops-agent

   ### Example Output Below ###
   INF Starting IBM Finops Agent...
   DBG HTTP server started on port 9003
   INF Initializing cldy emitter
   INF emitting sample to Cldy 0
   INF added sample to Cldy
   INF emitting sample to Cldy 1
   INF added sample to Cldy
   INF emitting sample to Cldy 2
   INF added sample to Cldy
   INF Attempt 1: performing login request to FrontDoor using KeyAccess and KeySecret
   INF Attempt 1: acquiring presigned URL from Cloudability with acquired Open-token
   INF Attempt 1: uploading sample to Cloudability S3 using presigned URL
   INF successfully uploaded metric sample xxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_xxxx-xx-xx-xx-xx-xx.tgz to cloudability
   ```

**Mais uma vez, levará 10 minutos para que o registro "successfully uploaded metric sample to cloudability" seja exibido. Esse é um ponto comum de falha nos agentes se eles não tiverem as configurações corretas de whitelisting/proxy ativadas.**

Após 24 horas de funcionamento do Agente do IBM FinOps e após o upload ter sido concluído com sucesso. Se você ainda estiver executando uma implantação do agente de métricas Cloudability, agora pode desativar essa infraestrutura e manter em execução apenas o gráfico Helm do agente IBM FinOps.

Nota:

Os dados do cluster devem aparecer no Container Insights dentro de 24 a 48 horas. Se você tiver algum problema com a implantação, entre em contato com o suporte do IBM Apptio.

Provisionamento de contêineres avançados d Cloudability

Se você atualizou para o [Cloudability Advanced Containers](advanced-containers.html), poderá começar facilmente a provisionar clusters usando o guia de configuração integrado ao produto, disponível na **página de provisionamento de agentes** em seu ambiente ( [https://api.cloudability.com/v3/kubecost/monitor:clusters:connect](https://api.cloudability.com/v3/kubecost/monitor:clusters:connect "(Abre em uma nova guia ou janela)") ). O guia oferece suporte a novas instalações, atualizações de agentes anteriores e ambientes em que o estado atual do agente é desconhecido. Ele fornece instruções passo a passo para instalar o agente, verificar a conectividade e confirmar se a instalação foi bem-sucedida.

Durante a configuração, o guia configura os dois emissores necessários: o emissor do Container Insights, que mantém seus relatórios existentes sobre contêineres do Cloudability, e o emissor do Advanced Containers, que permite a alocação de custos do Kubernetes, recomendações de otimização e recursos adicionais de relatórios. Após a instalação, os dados do cluster podem demorar alguns minutos para aparecerem em " Cloudability " > "Advanced Containers".

- **[Provisionamento de clusters para otimização de contêineres](../product/k8s-cluster-provisioning-premium.html)**
