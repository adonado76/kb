---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Configurar seu agente de contêiner"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Alocação de custos de contêineres"
source_path: "product/container-metrics-agent-provisioning.html"
images:
  - "images/conatiner-ua-19.png"
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
  - "images/containers-metrics-agent-provisioning-2.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configurar seu agente de contêiner

Nota:

**Migração do Agente de Métricas Legado**

IBM Cloudability está migrando do agente de métricas de contêineres antigo para o novo agente IBM FinOps. O agente de métricas antigo está sendo descontinuado e deixará de funcionar em 19 de novembro de 2026. Siga as instruções abaixo para obter orientações sobre a migração.

Visão geral

Para coletar os dados de que precisamos para realizar a alocação de um determinado cluster, você precisará implantar o IBM FinOps Agent, o agente de coleta de dados de última geração para Cloudability Containers. Para obter recomendações de otimização de contêineres, você precisará implantar o agente kubeturbo do Turbonomic em cada cluster sobre o qual deseja gerar relatórios.

Isso é obtido por meio de uma implementação do HELM provisionada para cada cluster. Esses comandos HELM podem ser gerados seguindo estas etapas:

Provisione o Cloudability Metrics Agent

1. Navegue até **Insights > Contêineres**.
2. Selecione o botão **Provisionar clusters**.
3. Preencha o formulário com o nome de seu cluster e a versão Kubernetes ou a versão OpenShift.
4. 4. Clique em Next -> **Generate Command**.

Nota:

Os dados do cluster devem ser exibidos em Cloudability no dia seguinte. Se tiver algum problema com a implementação, entre em contato com o suporte Apptio.

Google Kubernetes Engine Instruções específicas para o GKE

Você precisa adicionar uma [etiqueta de cluster](https://cloud.google.com/kubernetes-engine/docs/how-to/creating-managing-labels "(Abre em uma nova guia ou janela)") em cada cluster da seguinte forma:

- chave: gke-cluster
- valor: O(s) nome(s) do cluster que você definiu no formulário/YAML. Isso permite que o Cloudability mapeie os clusters do GKE para as linhas de item no arquivo de faturamento do GCP e aloque custos aos seus clusters.

Cloudability precisará ingerir um arquivo de faturamento com os rótulos de cluster que você adicionou, o que pode levar até 48 horas. Assim que o Apptio tiver processado o novo arquivo de faturamento, você precisará criar um novo [mapeamento de tags](build-an-aws-cost-by-tag-report.html) no aplicativo Cloudability. Defina um Cloudability Dimension como gke-cluster e mapeie-o para a tag gke-cluster. Essa é uma necessidade única, não por cluster.

Certifique-se de que sua conta tenha a função de administrador de cluster antes de implantar o agente Metrics. Por padrão, uma conta de usuário não tem a função de administrador de cluster. Execute o seguinte comando no cluster GKE para atribuir a função cluster-admin a um usuário:

```
"kubectl create clusterrolebinding username-cluster-admin-binding --
clusterrole=cluster-admin --user=username@emailaddress.com"
```

Implantar o agente

**Pré-requisitos:**

**Requisitos de rede:**

No agente de métricas do Cloudability, os requisitos de rede foram documentados no arquivo [README](https://github.com/cloudability/metrics-agent#:~:text=Networking%20Requirement%20for%20Metrics%20Agent "(Abre em uma nova guia ou janela)").

O agente unificado atualizou os requisitos de rede para funcionar corretamente e fazer upload de dados para o site Cloudability S3.

Os **novos** requisitos de rede para o agente são os seguintes:

> O contêiner que hospeda o agente de métricas deve permitir solicitações HTTPS para os seguintes pontos de extremidade:
>
> - https://frontdoor.apptio.com porta 443
>
>   - https://frontdoor-eu.apptio.com se Cloudability estiver na UE
>   - https://frontdoor-au.apptio.com se Cloudability estiver em AU
>   - https://frontdoor-me.apptio.com se Cloudability estiver em ME
> - https://api.cloudability.com porta 443
>
>   - https://api-eu.cloudability.com se Cloudability estiver na UE
>   - https://api-au.cloudability.com se Cloudability estiver em AU
>   - https://api-me.cloudability.com se Cloudability estiver em ME
>
> O contêiner que hospeda o agente de métricas deve ter acesso de gravação aos seguintes buckets Apptio S3 :
>
> - apptio\* (balde prefixado com apptio)
>
>   - Se precisar de informações mais detalhadas sobre os requisitos de whitelisting, entre em contato com nossa equipe de suporte

**Requisitos de armazenamento:**

O agente Finops do IBM (Finops-Agent) oferece suporte opcional a um volume persistente (PV) configurável (padrão: 8Gi ). O PV deve ser utilizado em ambientes em que a conexão com o armazenamento de objetos do Kubecost ou com a API d Cloudability e seja regularmente interrompida. Isso é improvável na maioria dos ambientes. Com o volume ativado, o agente armazenará amostras nesse volume e tentará recuperar quaisquer amostras após uma reinicialização. Esse aprimoramento melhora muito a capacidade do agente de recuperar dados em cenários de falha.

**Container Registry mudança:**

O IBM -Finops-Agent não é armazenado no docker como o metrics-agent existente. Em vez disso, o IBM -Finops-Agent é armazenado no ICR. Portanto, talvez seja necessário atualizar a lista de permissões do registro de contêineres para permitir que a implantação do IBM -Finops-Agent extraia a imagem do ICR. O registro do contêiner IBM -Finops-Agent é:

```
icr.io/ibm-finops/agent:vx.x.x
```

Se precisar extrair a imagem localmente para copiar para o registro do contêiner. Você pode executar o seguinte comando docker/podman pull:

```
 podman pull icr.io/ibm-finops/agent:v0.0.25 --platform=linux/amd64
```

**Autenticação:**

É importante ressaltar que o Cloudability metrics-agent usou uma chave de API específica de contêineres. O agente IBM finops **não usará/suportará mais essa chave de API**. Em vez disso, os clientes precisam criar uma **chave de API** para o agente no Frontdoor e reunir sua **ID de ambiente** do Frontdoor.

**Criação de usuário para gerenciar a chave de API do contêiner:**

É necessário que o ambiente do Frontdoor tenha chaves de API ativadas para que o recurso de contêineres funcione

Recomenda-se que os clientes criem um usuário de serviço específico para contêineres em seu próprio domínio para gerenciar sua chave de API daqui para frente. Dessa forma, a chave da API de upload não está associada a um usuário específico que pode ser desativado no futuro. A pessoa que cria o novo usuário e a chave de API precisa ser um usuário administrador em seu ambiente Frontdoor.

1. Navegue até "Access Wizard" (Assistente de acesso) em "Access Administration" (Administração de acesso), selecione "Add User(s)" (Adicionar usuário(s)), defina "Customer" (Cliente) e "Environment" (Ambiente). Por fim, pressione "Confirm" (Confirmar)

   ![](../../../../03-media/cloudability-premium/images/container-ua-1.png)
2. Insira as informações do usuário e clique em "Next" (Avançar)

   ![](../../../../03-media/cloudability-premium/images/container-ua-2.png)
3. Selecione "Grant Role(s)" (Conceder função), "Do not send User an activation Email" (Não enviar e-mail de ativação ao usuário) e clique em "Confirm" (Confirmar) para criar o usuário

   ![](../../../../03-media/cloudability-premium/images/container-ua-3.png)
4. Certifique-se de que o usuário esteja selecionado para conceder funções

   ![](../../../../03-media/cloudability-premium/images/container-ua-4.png)
5. Conceda a função “CloudabilityContainerUploader” ao usuário e clique em "Next"/"Confirm".

   ![](../../../../03-media/cloudability-premium/images/container-ua-5.png)

   **Criação de usuário para gerenciar a chave de API do contêiner:**
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
   2. Exemplo de formato de id: **xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx**

Implementando o metrics-agent com Helm

Pré-requisitos:

- Instalação: é necessário instalar o pacote “ [Helm](https://www.ibm.com/links?url=https%3A%2F%2Fhelm.sh%2F "(Abre em uma nova guia ou janela)") ” para utilizar os gráficos. Consulte [a documentação](https://www.ibm.com/links?url=https%3A%2F%2Fhelm.sh%2Fdocs%2F "(Abre em uma nova guia ou janela)") do Helm para começar.
- Atualizar as políticas de rede do cluster para permitir os novos requisitos de rede (se necessário)
- Reunir chaves públicas e privadas da API
- Coletar ID do ambiente da porta de entrada

Depois que o Helm tiver sido configurado corretamente, adicione o repositório da seguinte forma:

```
helm repo add ibm-finops https://kubecost.github.io/finops-agent-chart
```

Se você já tiver adicionado esse repositório anteriormente, atualize-o:

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
--set agent.cloudability.secret.cloudabilityAccessKey='<AccessKey>' \
--set agent.cloudability.secret.cloudabilitySecretKey='<SecretKey>' \
--set agent.cloudability.secret.cloudabilityEnvId='<EnvID>' \
--set clusterId='<ClusterName> \
--create-namespace -n ibm-finops-agent
```

Para desinstalar o Helm Repo:

```
helm uninstall ibm-finops-agent
```

Se o seu cluster estiver executando o antigo Cloudability metrics-agent, fique à vontade para mantê-lo em execução até ver o novo ibm-finops-agent iniciar o upload com êxito por 24 horas. O ibm-finops-agent pode ser instalado e executado em paralelo ao Cloudability metrics-agent, mas é recomendável desativar o Cloudability metrics-agent quando o novo agente estiver estável em seu cluster.

**UploadRegion** depende da região em que se encontra o ambiente Cloudability do cliente. Os valores suportados são os seguintes

- EUA: us (ou us-west-2 )
- UE: eu (ou eu-central-1 )
- AU: au (ou ap-southeast-2 )
- ME: eu (ou me-central-1 )
- Hybrid EU *(clientes que têm frontdoor da UE, mas fazem upload de dados de contêineres para a região dos EUA)* : hybrid-eu
- AU híbrido *(clientes que têm frontdoor AU, mas fazem upload de dados de contêineres para a região dos EUA):* hybrid-au
- ME híbrido *(clientes que têm frontdoor ME, mas fazem upload de dados de contêineres para a região dos EUA)* : hybrid-me

**ClusterName** deve ser o mesmo valor do que está atualmente no metrics-agent CLOUDABILITY\_CLUSTER\_NAME **para evitar problemas de ingestão de custos**.

Nota:

O agente unificado suporta muitas das mesmas configurações que o agente de métricas de saída Cloudability. Caso seu agente de métricas atual tenha alguma configuração específica **(por exemplo, configurações de PROXY)**, consulte [aqui](https://github.com/kubecost/finops-agent-chart/blob/main/charts/finops-agent/README.md#:~:text=%22%22-,Agent%20Configuration,-Name "(Abre em uma nova guia ou janela)") os parâmetros suportados pelo Helm.

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
2. Verifique os registros dos pods para confirmar se o agente está carregando os dados com êxito em Cloudability. **Levará 10 minutos para ver o primeiro registro de upload bem-sucedido.**

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

Após 24 horas de execução e upload bem-sucedido do ibm-finops-agent. Se você ainda estiver executando uma implantação do Cloudability metrics-agent, poderá agora desmontar essa infraestrutura e manter apenas o helm chart do ibm-finops-agent em execução.

Provisionamento do Agente de Otimização de Contêineres d Cloudability ( Turbonomic kubeturbo)

1. Navegue até Insights > Contêineres.
2. Selecione o botão Provisionar clusters.
3. Preencha o formulário com o nome de seu cluster e a versão Kubernetes ou a versão OpenShift.
4. Selecione Generate Agent Script (Gerar script do agente ) na seção Container optimization Agent (Agente de otimização de contêineres ).

![](../../../../03-media/cloudability-premium/images/conatiner-ua-19.png)

Observação: o site Cloudability gera um arquivo de script de shell para download e você pode executar a implantação do agente depois de conectado ao cluster de destino. Depois de concluído, o site Cloudability começará a receber dados para o cluster em algumas horas.

Nota:

Os dados do cluster devem ser exibidos em Cloudability no dia seguinte. Se tiver algum problema com a implementação, entre em contato com o suporte Apptio.

Etapas de instalação

Depois de fazer o download do script, copie-o para o local em que deseja executá-lo, em um ambiente em que esteja conectado ao cluster de destino em que deseja implantar o agente.

Execute o comando usando o exemplo abaixo:

```
chmod +x new-js-aks.sh &&./new-js-aks.sh
```

O resumo da instalação é o seguinte.

```
Parameter            Value
---------            ---------
Mode                 Create/Update
Kubeconfig           default
Host                 https://20.116.237.9
Namespace            turbo
Target Name          new-js-aks
Target Subtype       Kubernetes
Role                 turbo-cluster-admin
Version              8.14.5
Auto-Update          false
Auto-Logging         false
Proxy Server         false
Private Registry     false
```

Confirme as configurações acima [Y/n]: Y

Seu contexto atual do Kubernetes está definido como o seguinte.

```
NAME                     CLUSTER                  AUTHINFO                                                NAMESPACE
concise-lobster-aks      concise-lobster-aks      clusterUser_concise-lobster-rg_concise-lobster-aks
```

Confirme se o script deve funcionar no cluster acima [Y/n]: Y

```
Creating turbo namespace to deploy Kubeturbo operator
namespace/turbo created
secret/turbonomic-credentials created
% Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
Dload  Upload   Total   Spent    Left  Speed
100  159k  100  159k    0     0   920k      0 --:--:-- --:--:-- --:--:--  923k

customresourcedefinition.apiextensions.k8s.io/kubeturbos.charts.helm.k8s.io unchanged
serviceaccount/kubeturbo-operator created
clusterrole.rbac.authorization.k8s.io/kubeturbo-operator unchanged
Skip patching ClusterRoleBinding kubeturbo-operator as the clusterRole has bound to the operator service account already.
deployment.apps/kubeturbo-operator created
namespace/turbo configured
Waiting for deployment 'kubeturbo-operator' to start...
Resource is not ready, re-attempt after 10s ... (1/10)
pod/kubeturbo-operator-857855c6b5-d9x2c condition met
apply Kubeturbo CR ...
kubeturbo.charts.helm.k8s.io/kubeturbo-release created
Waiting for deployment 'kubeturbo-release' to start...
Resource is not ready, re-attempt after 10s ... (1/10)
pod/kubeturbo-release-7d499cf568-cg5sm condition met
Successfully apply Kubeturbo in turbo namespace!

NAME                                SECRETS   AGE
serviceaccount/kubeturbo-operator   0         32s
serviceaccount/turbo-user           0         12s

NAME                                     READY   STATUS    RESTARTS   AGE
pod/kubeturbo-release-7d499cf568-cg5sm   1/1     Running   0          12s

NAME                                 READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/kubeturbo-operator   1/1     1            1           30s
deployment.apps/kubeturbo-release    1/1     1            1           12s

NAME                                       DATA   AGE
configmap/turbo-config-kubeturbo-release   2      12s
Done!
```

Execute o comando abaixo para verificar se os 2 pods estão em execução, conforme mostrado no exemplo abaixo:

```
kubectl get pods -n turbo
```

```
NAME                                  READY   STATUS    RESTARTS   AGE 
kubeturbo-operator-857855c6b5-d9x2c   1/1     Running   0          105s 
kubeturbo-release-7d499cf568-cg5sm    1/1     Running   0          87s
```

A imagem a seguir ilustra a instalação.

![captura de tela da instalação do kubeturbo](../../../../03-media/cloudability-premium/images/containers-metrics-agent-provisioning-2.jpg)

**Tópico pai:** [Alocação de custos de contêineres](../product/k8s-cost-allocation.html)
