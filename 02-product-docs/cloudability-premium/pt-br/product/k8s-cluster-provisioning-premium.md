---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Provisionamento de clusters para otimização de contêineres"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
  - "Kubernetes Provisionamento de cluster"
source_path: "product/k8s-cluster-provisioning-premium.html"
images:
  - "images/conatiner-ua-19.png"
  - "images/containers-metrics-agent-provisioning-2.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Provisionamento de clusters para otimização de contêineres

No ` Cloudability Premium `, o provisionamento de clusters ` Kubernetes ` requer a instalação **de dois agentes distintos** : o **` IBM ` ` FinOps Agent** ` e o **`Kubeturbo Agent` (Agente de Otimização de Contêineres)**.

Esta página aborda especificamente a instalação e a configuração do **Agente** Kubeturbo (Otimização) — caso precise instalar o *Agente* FinOps para alocação de custos, consulte a página sobre [o provisionamento de clusters](k8s-cluster-provisioning.html) do Kubernetes.

## Implantar o agente Kubeturbo

Baixe o script do agente de otimização de contêineres do Cloudability (Kubeturbo do Turbonomic )

1. Acesse Insights > Contêineres.
2. Selecione o botão “Provisionar clusters ”.
3. Preencha o formulário com o nome de seu cluster e a versão Kubernetes ou a versão OpenShift.
4. Selecione “Gerar script do agente” na seção “Agente de otimização de contêineres ”.

![](../../../../03-media/cloudability-premium/images/conatiner-ua-19.png)

*Os passos a seguir descrevem o procedimento de instalação do Kubeturbo Agent após o download do script.*

Adicionar namespace para o cluster

Por padrão, o Kubeturbo é implantado em um namespace chamado turbo. Recomendamos que você mantenha o nome padrão. No entanto, se você quiser especificar um nome personalizado durante a implementação, forneça um nome que atenda aos seguintes requisitos:

- Deve começar com caracteres alfanuméricos minúsculos ou com o símbolo de traço (-), e deve começar e terminar com um caractere alfanumérico. Por exemplo, my-name e 123-abc são nomes válidos.
- Para um cluster de produção, considere não usar o namespace padrão.
- Evite criar namespaces com o prefixo kube-. Ele é reservado para os namespaces do sistema Kubernetes.

Configurar a função do cluster

Você pode definir a variável KUBETURBO\_ROLE como turbo-cluster-admin ou turbo-cluster-reader.

- A função turbo-cluster-admin especifica as permissões mínimas de que o Kubeturbo necessita para monitorar suas cargas de trabalho e executar as ações de otimização geradas pel Turbonomic
- A função turbo-cluster-reader especifica as permissões mínimas que o Kubeturbo precisa para monitorar apenas suas cargas de trabalho. Quaisquer ações de otimização geradas pelo Turbonomic só podem ser executadas externamente (por exemplo, fora do cluster).

Para obter mais informações, consulte [Funções de cluster do Kubeturbo](https://www.ibm.com/docs/en/tarm/8.16.x?topic=requirements-cluster-roles-kubeturbo "(Abre em uma nova guia ou janela)")

Configurar o repositório de imagens privadas

Quando KUBETURBO\_REGISTRY\_USRNAME e KUBETURBO\_REGISTRY\_PASSWRD forem fornecidos, o script os usará para criar um segredo de extração de imagem para acessar o repositório privado e extrair as imagens necessárias.

KUBETURBO\_REGISTRY especifica o prefixo do seu registro e repositório privados. Ele substitui o prefixo padrão icr.io/ cpopen nos caminhos da imagem original.

- Prefixo original : icr.io/ cpopen
- Prefixo de registro privado : myregistry.mycompany.com/kubeturbo

Observação: Todas as imagens necessárias devem ser espelhadas no seu registro privado com exatamente as mesmas tags da fonte original.

Configurar o proxy e as credenciais de registro

Forneça o PROXY\_SERVER e o KUBETURBO\_REGISTRY\_PASSWRD como cadeias de caracteres base64-encoded.

Especifique as seguintes configurações de proxy:

- Nome do host do proxy ou endereço IP : especifique o endereço do proxy usado para este destino.
- Porta do proxy: Especifique a porta a ser usada com o proxy usado para esse destino. Por padrão, a porta é 8080.
- Nome de usuário do proxy : especifique o nome de usuário a ser usado com o proxy.
- Senha do proxy : especifique a senha a ser usada com o proxy.
- Conectar-se usando HTTPS : Selecione esta opção se o Turbonomic for se conectar ao proxy através de HTTPS.

Etapas de instalação

Depois que o script for baixado, copie-o para o local de onde você deseja executá-lo, em um ambiente no qual você esteja conectado ao cluster de destino onde deseja que o agente seja implantado.

Execute o comando seguindo o exemplo abaixo:

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

Confirme as configurações acima [S/n]: S

Seu contexto atual do Kubernetes está definido da seguinte forma.

```
NAME                     CLUSTER                  AUTHINFO                                                NAMESPACE
concise-lobster-aks      concise-lobster-aks      clusterUser_concise-lobster-rg_concise-lobster-aks
```

Confirme se o script deve ser executado no cluster acima [S/n]: S

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

Execute o comando abaixo para verificar se os dois pods estão em execução, conforme mostrado no exemplo a seguir:

```
kubectl get pods -n turbo
```

```
NAME                                  READY   STATUS    RESTARTS   AGE 
kubeturbo-operator-857855c6b5-d9x2c   1/1     Running   0          105s 
kubeturbo-release-7d499cf568-cg5sm    1/1     Running   0          87s
```

A imagem a seguir ilustra a instalação.

![Captura de tela da instalação do Kubeturbo](../../../../03-media/cloudability-premium/images/containers-metrics-agent-provisioning-2.jpg)

**Tópico principal:** [Kubernetes Provisionamento de cluster](../product/k8s-cluster-provisioning.html)
