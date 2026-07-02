---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Conexão com AWS - Guia de integração do cliente"
breadcrumb:
  - "Cloudability Premium"
  - "Obtendo dados em Cloudability"
source_path: "admin/aws-credentialing-premium-home.html"
images:
  - "images/AWS-VC.png"
  - "images/AWSp.png"
  - "images/TurboTarget.png"
  - "images/clip_image001_1499665667.png"
  - "images/clip_image002_-1577046812.png"
  - "images/curP.png"
  - "images/curP1.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conexão com AWS - Guia de integração do cliente

Visão geral

Este guia orienta você passo a passo pelo processo de conexão segura do seu ambiente do AWS aos sites IBM, Cloudability e Turbonomic. Depois de conectado, você terá acesso a uma experiência aprimorada do FinOps tanto em Cloudability quanto em Turbonomic.

Observação: Para garantir total compatibilidade e suporte, siga as etapas de conexão conforme descrito. Configurações CUR personalizadas não são suportadas. Se tiver alguma dúvida, entre em contato com **o suporte** do IBM.

Pré-requisitos

Antes de começar, verifique se você tem acesso a:

- AWS Console
- Privilégios de administrador (ou similares) em AWS para criação de S3 e permissões de IAM
- Acesso de administrador às credenciais do fornecedor Cloudability

Cloudability o processo de credenciamento do AWS requer duas etapas principais:

- Credenciamento de contas de gerenciamento
- Credenciamento de contas vinculadas

AWS Credenciamento de contas de gerenciamento

Cloudability usa o credenciamento da AWS Management Account para:

- Trazer dados de custo e uso para contas de gerenciamento credenciadas.
- Sincronização das contas vinculadas na(s) conta(s) de gerenciamento.

Observação: para que isso funcione, você deve ter o faturamento consolidado ativado e suas contas vinculadas devem ser transferidas (do ponto de vista do faturamento) para sua conta de gerenciamento.

O processo de credenciamento envolve algumas etapas que exigirão que você tome medidas em AWS e Cloudability em várias fases.

Vamos começar com o processo de credenciamento:

1. **AWS Console - Crie um relatório de custo e uso do AWS**
   1. No **Console de gerenciamento AWS**, selecione o nome da sua conta no canto superior direito e selecione **Billing and Cost Management**.
   2. Na página **Billing & Cost Management Dashboard**, selecione **Data Exports (em Cost and Usage Analysis)**.
   3. Selecione **Criar**.

Cloudability suporta CUR e AWS CUR legados 2.0 em ambos os formatos.

- gzip - texto/csv
- Pavimento em parquet - Pavimento em parquet

Aqui estão as etapas necessárias para configurar qualquer um deles.

Observação: Outras exportações de dados do “ AWS ” não são compatíveis (por exemplo, CUR pro forma)

- Cloudability suporta exportações de dados criadas em um nível de conta de gerenciamento.

Tabela 1. Tabela de configuração

| Etapas em AWS | Legado CUR | 2.0 |
| --- | --- | --- |
| Criar exportação > Detalhes da exportação | Exportação de CUR legado | Exportação de dados padrão |
| Criar exportação > Configurações de conteúdo da tabela de dados | Selecione **Incluir IDs de recursos**. **Os dados de alocação de custos divididos** devem estar **desmarcados**.  Selecione **Atualizar automaticamente nas configurações de atualização de dados.** | Selecione **CUR 2.0**.  - Selecione **Incluir IDs de recursos**. - **Os dados de alocação de custos divididos** devem ser **desmarcados** - Selecione **Hourly** para a granularidade de tempo dos dados do relatório.  Seleção de coluna - Deixe como **padrão** (todas as colunas) |
| Para opções de entrega de exportação de dados, selecione o seguinte. | Selecione **Hourly** para a granularidade de tempo dos dados do relatório.  Selecione Criar **nova versão de relatório.**  Observação: Isso é necessário para garantir um funcionamento integrado entre Cloudability e Turbonomic.  As opções de integração de dados do relatório não devem ser selecionadas.  Certifique-se de que o tipo de compactação esteja definido como **gzip ou parquet** | Certifique-se de que o tipo de compactação esteja definido como **gzip-text/cs ou parquet.**  Certifique-se de que a opção Criar **novo arquivo de exportação de dados** para controle de versão de relatório esteja selecionada.  Observação: Isso é necessário para garantir um funcionamento integrado entre Cloudability e Turbonomic |
| Para configurações de armazenamento de exportação de dados. | Seus arquivos de relatório de custo e uso residirão nesse compartimento. Você pode;   - Insira um bucket e um prefixo pré-existentes do site S3 OU - Selecione **Configure (Configurar** ). Se Configurar for selecionado   - Selecione **Create a Bucket** (ou selecione um bucket existente, se já tiver sido criado)   - Digite um nome de bucket S3   - Selecione a região para criar um novo bucket   - Clique em **Create Bucket**   - Adicionar um **prefixo de caminho s3**   - Adicione quaisquer tags **(opcional)**   - Selecione **Criar relatório** | Seus arquivos de relatório de custo e uso residirão nesse compartimento. Você pode;   - Insira um bucket e um prefixo pré-existentes do site S3 OU - Selecione **Configure (Configurar** ). Se Configurar for selecionado   - Selecione **Create a Bucket** (ou selecione um bucket existente, se já tiver sido criado)   - Digite um nome de bucket S3   - Selecione a região para criar um novo bucket   - Clique em **Create Bucket**   - Adicionar um **prefixo de caminho s3**   - Adicione quaisquer tags **(opcional)**   - Selecione **Criar** |

Observação: O comando `Cloudability ` procura o arquivo de manifesto no seguinte local:

**CUR herdado** - <prefixo do relatório de custo e uso>/<nome do relatório de custo e uso>/YYYYMMDD-YYYYMMDD/<nome do relatório de custo e uso> -Manifest.json

**CUR 2.0** - <Prefixo do relatório de custo e uso>/<Nome do relatório de custo e uso>/metadata/BILLING\_PERIOD=YYYYY-MM/<Nome do relatório de custo e uso> -Manifest.json

![cur](../../../../03-media/cloudability-premium/images/curP.png)![cur](../../../../03-media/cloudability-premium/images/curP1.png)

Observação: os clientes podem configurar a criptografia do lado do servidor com chaves gerenciadas do Amazon S3 ( SSE-S3 ) em seus buckets S3. Cloudability não suporta criptografia usando KMS ou chaves de criptografia fornecidas pelo cliente.

Registre os detalhes abaixo, pois eles serão inseridos em Cloudability nas etapas seguintes:

1. **ID DA CONTA DO PAGADOR: ID da conta de gerenciamento AWS**
2. **S3 NOME DO BUCKET:** O bucket que contém seu relatório de custo e uso criado anteriormente
3. **COST AND USAGE REPORT NAME** criado anteriormente
4. **PREFIXO DO RELATÓRIO DE CUSTO E USO** criado anteriormente

Observação: Os clientes existentes no AWS Legacy CUR podem continuar a usar o Legacy CUR. Se você deseja migrar para o CUR 2.0, será necessário atualizar as credenciais em Cloudability com o CUR 2.0, pois não é possível atualizar o CUR antigo para o CUR 2.0.The. A exportação de dados criada de acordo com as etapas do Cloudability, por padrão, carregará os dados no local acima. Se algum dado histórico for obtido, o cloudability espera que os arquivos de manifesto estejam no local acima.

Para obter detalhes sobre a mudança do Legacy CUR para o CUR 2.0, consulte as perguntas frequentes

Por favor, deixe as opções abaixo desmarcadas

- Dados de alocação de custos divididos
- Incluir colunas de reserva de capacidade e granularidade
- Descontos compatíveis manualmente

2. AWS Console - Ativar tags de alocação de custos

1. No **Painel** de Faturamento e Gestão de Custos, acesse [**“Tags de Alocação de**](https://console.aws.amazon.com/billing/home#/tags "(Abre em uma nova guia ou janela)") Custos”.
2. Selecione as tags que você deseja incluir.

   Observação: Cuidado com a caixa de camelo. Por exemplo: Se você tiver "Nome" ou "nome" como uma chave de tag, ambos precisam ser ativados para que sejam gravados no CUR.
3. Selecione **Ativar**.

3. Cloudability - Configurar credenciais para a conta de gerenciamento AWS

Você deve ter direitos de administrador do site Cloudability para concluir esse procedimento. Se não tiver direitos de administrador, entre em contato com o administrador principal do site Cloudability da sua organização para obter ajuda.

Em Cloudability, navegue até **Settings >** **Vendor Credentials >** **Add Datasource e selecione > AWS**.

1. Em **Credenciais**, digite o seguinte:
   - **ID da conta do pagador (obrigatório)**
   - **S3 Nome do Bucket (Obrigatório):** O bucket que contém seu relatório de custo e uso
   - **Nome do relatório de custo e uso (obrigatório)**
   - **Prefixo do relatório de custo e uso (obrigatório)**
   - **AWS Região habilitada para SCP (opcional)**
     - Caso você tenha aplicado [uma Política de Controle de Serviço (SCP) AWS](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.aws.amazon.com%2Forganizations%2Flatest%2Fuserguide%2Forgs_manage_policies_scps.html "(Abre em uma nova guia ou janela)") que restrinja o acesso em algumas regiões AWS, indique a região *permitida*; por exemplo: us-east-2. Caso contrário, isso pode ser deixado em branco. Isso ajuda o site Cloudability a fazer chamadas de verificação para a região especificada.
     - Atualmente, o site Cloudability suporta a adição de uma única região SCP.
   - **Credenciamento automatizado de conta(s) vinculada(s) (recomendado)**
     - Recomendamos o uso do [credenciamento automatizado de contas vinculadas AWS](aws-credentialing-premium-linked.html) se você tiver um número significativo de contas vinculadas. Isso simplificará seu processo de credenciamento agora e para a futura adição de novas contas.
     - Para usar o recurso de credenciamento automatizado de contas vinculadas Cloudability, é necessário realizar um trabalho adicional em Cloudability e AWS, que inclui o download de um modelo CloudFormation de uma conta vinculada e sua implementação como StackSet (garantindo que a função correta do IAM esteja em vigor para que as contas vinculadas herdem as permissões do IAM). Isso é abordado em detalhes em Credenciamento de conta vinculada.
   - **Escolha entre o redimensionamento avançado em modo somente leitura e a automatização de ações**
     - A seleção **"Somente leitura"** significa que você está concedendo permissões de monitoramento para Cloudability cost, Turbonomic cost e Turbonomic para que elas possam ler seu ambiente, mas não realizar ações.
     - **A** seleção de “ Cloudability ” implica que você está concedendo todas as permissões de e Turbonomic, incluindo aquelas relacionadas a ações automatizadas, ou seja, Turbonomic execução e execução de faturamento do Turbonomic.

   Observação: quando a opção “Credenciamento automático de contas vinculadas do AWS ” estiver selecionada, a sua escolha entre **“Somente leitura”** e **“Automatizar ações”** será aplicada às suas contas vinculadas. Se essa opção **NÃO** estiver selecionada, a escolha entre **“Somente leitura”** e ****“Automatizar ações”**** deverá ser feita individualmente para cada conta vinculada.
2. Selecione **Salvar**.
3. Selecione **Generate Template (Gerar modelo** ).
4. Selecione **Download**.
5. Um modelo AWS CloudFormation será baixado localmente - salve-o em um local seguro para a próxima etapa, pois ele precisará ser carregado no console AWS.![aws](../../../../03-media/cloudability-premium/images/AWS-VC.png)

4. AWS Console - Carregue o modelo CloudFormation no console de gerenciamento AWS

1. No **Console de gerenciamento AWS**, pesquise 'CloudFormation' e selecione-o.
2. Na página **AWS CloudFormation** página, selecione **Criar pilha (com novos recursos (padrão))**.
3. Em **Specify template (Especificar modelo** ), faça o seguinte:
   - Selecione **Carregar um arquivo de modelo**.
   - Selecione **Choose file (Escolher arquivo** ) e carregue o modelo que você baixou de Cloudability.
   - Selecione **Next**.
4. Na página **Especificar detalhes da pilha**, faça o seguinte:
   - Digite um **nome de pilha** (por exemplo, ' Cloudability ').
   - Verifique os **parâmetros** preenchidos.
   - Selecione **Next**.
5. Percorra a página **Configure stack options (Configurar opções de pilha** ) e marque a opção "I acknowledge that AWS CloudFormation might create IAM resources with customized names" (Eu reconheço que pode criar recursos IAM com nomes personalizados) e clique em Next (Avançar).
6. Na página **Review (Revisão** ), selecione **Submit (Enviar** ).

Sua nova pilha tem inicialmente o status de **CREATE\_IN\_PROGRESS**. Quando o status muda para **CREATE\_COMPLETE**, você pode verificar sua credencial em Cloudability. Talvez seja necessário atualizar a página CloudFormation na interface do usuário para confirmar isso.

5. Cloudability - Verificar a credencial da conta

1. Em Cloudability, navegue até **Settings > Vendor Credentials > AWS**.
2. Clique em... ao lado da conta que está sendo credenciada e selecione Re-Verificar.
   - Uma marca de seleção verde (![../../resources/cldy_images/clip_image001_-1832790195.png](../../../../03-media/cloudability-premium/images/clip_image001_1499665667.png)) indica sucesso, enquanto um ponto de exclamação vermelho (![../../resources/cldy_images/clip_image002_-821243953.png](../../../../03-media/cloudability-premium/images/clip_image002_-1577046812.png)) indica erros.

Observação: esse processo acima criará uma função do IAM chamada CloudabilityRole, que será usada pelo Cloudability para verificar as permissões. Se a verificação falhar, tente novamente após 15 minutos.

![aws](../../../../03-media/cloudability-premium/images/AWSp.png)

Após a conclusão desse processo, em poucas horas,

- Cloudability passará a exibir seus dados de cobrança e as tags “ AWS ” no site Cloudability.
- Os dados de preços também seriam importados.
- Cloudability também exibirá as contas vinculadas.

Como próximo passo, você precisará autenticar as contas vinculadas.

**Status de credenciais**

Cloudability A tela de credenciais do fornecedor exibe o status da conta a partir de:

- Cloudability
- Turbonomic

Depois que os modelos mais recentes forem executados, o status da conta deverá estar sincronizado entre Cloudability e Turbonomic. Para obter detalhes sobre o status da conta, verifique a seção de detalhes da conta.

![](../../../../03-media/cloudability-premium/images/TurboTarget.png)

[AWS Credenciamento de contas vinculadas](aws-credentialing-premium-linked.html)

[AWS Atualização de clientes existentes do Cloudability para Cloudability Premium](aws-credentialing-premium-upgrading.html)

[AWS Obtenção de métricas de memória para instâncias do EC2 - Windows e Linux](aws-credentialing-premium-memory.html)

[AWS PERGUNTAS FREQUENTES](aws-credentialing-premium-faq.html)

- **[AWS Credenciamento de contas vinculadas](../admin/aws-credentialing-premium-linked.html)**
- **[AWS Credenciamento usando ações em massa](../admin/aws-credentialing-bulk-actions.html)**
- **[Conectando-se com AWS - Atualizando os clientes existentes de Cloudability para Cloudability Premium](../admin/aws-credentialing-premium-upgrading.html)**
- **[AWS Tags](../admin/support-for-aws-tags.html)**
- **[Conexão com AWS - Obtenção de métricas de memória para instâncias de EC2 (Windows e Linux )](../admin/aws-credentialing-premium-memory.html)**
- **[Referência de permissões Amazon Web Services](../admin/permissions-reference-aws.html)**
- **[Perguntas frequentes sobre como se conectar com AWS](../admin/aws-credentialing-premium-faq.html)**
