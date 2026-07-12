---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Complete as dependências de configuração do site AWS"
breadcrumb: []
source_path: "cost-transparency/configuration-additional/completeawsconfidependencies.html"
images:
  - "resources/images/ct_images/7848_1.png"
  - "resources/images/ct_images/7848_2.png"
  - "resources/images/ct_images/7848_3.png"
  - "resources/images/ct_images/7848_4.png"
  - "resources/images/ct_images/7848_5.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Complete as dependências de configuração do site AWS

- Aplica-se a: Apptio Costing Standard ou Apptio Cloud Cost Management em TBM Studio 12.3.3 e posterior

Conclua as etapas a seguir para as dependências de configuração do Amazon Web Services ( AWS ).

## Criar um bucket S3

Para criar um bucket S3, siga estas etapas:

1. Faça login no Console de gerenciamento AWS para a conta com a qual você deseja se integrar.
2. No menu Services (Serviços), navegue até o console Amazon S3.
3. Selecione **Create Bucket**.
4. Digite um nome para o bucket e selecione uma região onde o bucket residirá.
5. Clique em **Create**.

Para definir permissões para o bucket, siga estas etapas:

1. No Console de gerenciamento AWS, navegue até My Billing Dashboard.
2. Selecione **Preferências**.
3. Em Receive Billing Reports (Receber relatórios de faturamento), digite o nome do intervalo S3 e selecione **Sample policy (Política de amostra** ).
4. Copie a política.
5. Navegue até o console Amazon S3 e selecione o bucket que você criou.
6. Clique em **Propriedades**, **Permissões** e selecione **Adicionar política de bucket**.
7. Cole a política que você copiou e clique em **Salvar**.

## Ativar relatórios de faturamento (alocação de custos)

Para ativar todas as opções de recebimento de faturamento:

1. No Console de gerenciamento AWS, navegue até My Billing Dashboard e selecione **Preferences (Preferências** ).
2. Em Receber relatórios de cobrança, certifique-se de que o nome do seu bucket S3 apareça em **Salvar no bucket S3**.
3. Ative todas as opções de relatório de faturamento selecionando as seguintes caixas: Relatório mensal, Relatório de faturamento detalhado, Relatório de alocação de custos e Relatório de faturamento detalhado com recursos e tags.
4. Clique em **Save Preferences (Salvar preferências** ).

## Habilitar tags para relatórios de faturamento

Para ativar todas as tags em seus relatórios de faturamento:

1. No Console de gerenciamento AWS, navegue até My Billing Dashboard.
2. Selecione **Tags de alocação de custos**.
3. Habilite todas as tags que você usará para analisar suas despesas.

DataLink pode se autenticar em AWS para obter permissões de acesso a AWS Data Sources.

**Delegação** - O DataLink assumirá uma função IAM do AWS que sua organização criou para obter permissões temporárias de acesso aos dados do AWS. Recomendamos essa abordagem do ponto de vista da segurança.

## Delegação

1. No novo conector DataLink AWS, selecione **Use Delegation (Usar delegação) na seção AWS Credentials (Credenciais** ) e copie toda a cadeia de caracteres no campo **External ID (ID externo** ).

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7848_1.png)
2. Se as políticas de segurança ainda não tiverem sido criadas, em seu ambiente AWS, crie as políticas de segurança do IAM a serem anexadas à função do IAM. Isso será configurado em AWS e assumido pelo conector AWS. Consulte a seção [Políticas de segurança](#completeawsconfidependencies__Securitypolicies) abaixo para obter as políticas específicas a serem criadas.
3. No console AWS, navegue até o serviço IAM e crie uma nova função IAM.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7848_2.png)
4. Especifique um nome de função. Esse nome de função será inserido no conector DataLink AWS, portanto, crie um nome que seja DataLink-specific.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7848_3.png)
5. Em seguida, especifique o tipo de função:

   Selecione **a função para acesso entre contas**. Em seguida, escolha **Fornecer acesso entre sua conta AWS e uma conta AWS de terceiros**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7848_4.png)
6. Digite a ID da conta Apptio Datalink (Classic) (007579627371) e a ID externa (disponível no conector AWS - consulte a etapa 1 acima).

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/7848_5.png)
7. Anexe as políticas apropriadas (criadas na etapa 2 acima) à função.
8. No novo conector DataLink AWS, digite o ID da conta AWS e o nome da função que acabou de ser criada.

## Políticas de segurança

Isso criará uma política que permite que o titular (um usuário, grupo ou, no nosso caso, uma função) leia itens do bucket especificado. Substitua "my-bucket" pelo nome do bucket que você gostaria que o DataLink acessasse.

S3
:   ```
    { "Version": "2012-10-17", "Statement": [ { "Sid": "Stmt1468715091000", "Effect": "Allow", "Action": [ "s3:GetBucketLocation", "s3:GetObject", "s3:ListBucket" ], "Resource": [ "arn:aws:s3:::my-bucket" ] }, { "Effect": "Allow", "Action": [ "s3:GetObject" ], "Resource": [ "arn:aws:s3:::my-bucket/*" ] } ] }
    ```

Descreva as instâncias reservadas do EC2
:   ```
    { "Version": "2012-10-17", "Statement": [ { "Sid": "Stmt1431460354000", "Effect": "Allow", "Action": [ "ec2:DescribeReservedInstances", "ec2:DescribeReservedInstancesListings", "ec2:DescribeReservedInstancesModifications", "ec2:DescribeReservedInstancesOfferings" ], "Resource": [ "*" ] } ] }
    ```

Descreva as instâncias reservadas do RDS
:   ```
    { "Version": "2012-10-17", "Statement": [ { "Action": [ "rds:DescribeReserved*", "rds:ListTagsForResource" ], "Effect": "Allow", "Resource": "*" } ] }
    ```

Descreva as verificações do Trusted Advisor
:   Essa política é fornecida pelo site AWS por padrão: AWSSupportAccess

    ```
    { "Version": "2012-10-17", "Statement": [ { "Effect": "Allow", "Action": ["support:*" ], "Resource": "*" } ] }
    ```

Para obter mais informações sobre como criar uma função em Amazon Web Services, consulte [Criação de funções de IAM - AWS Identity and Access Management](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_create.html "(Abre em uma nova guia ou janela)").
