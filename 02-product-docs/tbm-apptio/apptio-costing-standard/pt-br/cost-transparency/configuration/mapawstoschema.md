---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Mapear as tags AWS para o esquema Apptio"
breadcrumb: []
source_path: "cost-transparency/configuration/mapawstoschema.html"
images:
  - "resources/images/ct_images/check-out-aws-master.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Mapear as tags AWS para o esquema Apptio

Este artigo o ajudará a mapear as tags de alocação de custos do site AWS para seu esquema Apptio. As tags de alocação de custos ajudam a categorizar e rastrear os custos do AWS.

Quando você aplica tags aos seus recursos do AWS (como instâncias do Amazon EC2 ou buckets do Amazon S3 ) e ativa as tags, o AWS gera um relatório de alocação de custos como um arquivo CSV (valor separado por vírgula) com seu uso e custos agregados pelas tags ativas. Você pode aplicar tags que representam categorias de negócios (como centros de custo, nomes de aplicativos ou proprietários) para organizar seus custos em vários serviços.

Aplica-se a: Apptio Costing Standard em TBM Studio 12.3.3 e posterior

## Sobre esta tarefa

Os seguintes recursos do site AWS fornecem informações básicas sobre tags:

- [O que é uma etiqueta?](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-what-is.html "(Abre em uma nova guia ou janela)")
- [Restrições de etiquetas](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/allocation-tag-restrictions.html "(Abre em uma nova guia ou janela)")
- [Configuração do relatório mensal de alocação de custos](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/configurecostallocreport.html "(Abre em uma nova guia ou janela)")
- [AWS Faturamento e gerenciamento](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html "(Abre em uma nova guia ou janela)") de custos (Esse site também fornece um arquivo.pdf com informações sobre faturamento e gerenciamento de custos da Amazon)

Tags recomendadas

Nem todas as tags AWS são necessárias para Apptio. A lista a seguir é recomendada como um guia para os dados que serão importantes em sua implementação do Costing Standard .

| **Etiqueta** | **Descrição** | **Valor em Apptio** |
| --- | --- | --- |
| Nome do aplicativo | Nome do aplicativo suportado pelo recurso marcado | - Fornecer análises para ajudar a entender os gastos com a nuvem por aplicativos que consomem serviços de nuvem - Alocar gastos a aplicativos para calcular o TCO |
| Ambiente de aplicativos (produção, desenvolvimento, teste, DR) | Ambiente suportado pelo recurso marcado | Fornecer análises para ajudar a entender os gastos com a nuvem por ambiente de aplicativo criado em serviços de nuvem |
| Camada de aplicativos (servidor da Web, lógica de negócios, banco de dados) | Nível de aplicativo do recurso marcado | Fornecer análises para ajudar a entender os gastos com a nuvem por nível de aplicativo criado em serviços de nuvem |
| Centro de custos | Centro de custos responsável pela operação do recurso etiquetado | - Fornecer análises para ajudar a entender os gastos com a nuvem por centro de custo que consome serviços de nuvem - Alocar e mostrar despesas de retorno/chargeback para os clientes de TI |
| Proprietário do sistema | Indivíduo responsável pela operação do recurso etiquetado | - Fornecer análises para ajudar a entender os gastos com a nuvem por centro de custo que consome serviços de nuvem - Alocar e mostrar despesas de retorno/chargeback para os clientes de TI |
| Projeto | Projeto associado ao recurso marcado | - Fornecer análises para ajudar a entender os gastos com a nuvem por projeto de custo que impulsiona os serviços de nuvem - Alocar gastos para projetos de TI |

## Para o relatório mensal de alocação de custos

### Procedimento

1. Navegue até TBM Studio.
2. Selecione **AWS Cost Allocation Bill Master Data** e confira.

   ![AWS Dados mestre da fatura de alocação de custos](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/check-out-aws-master.png)
3. No pipeline de transformação, clique na etapa **Append** e, em seguida, clique em **Edit** em AWS Cost Allocation Raw.

   Uma caixa de diálogo é aberta, permitindo que você mapeie colunas da tabela bruta AWS Cost Allocation Raw para a tabela Apptio AWS Cost Allocation Bill Master Data.
4. Preencha os mapeamentos das colunas a seguir que são relevantes para as tags AWS e a estrutura de pagador/conta vinculada de sua organização:

   **IMPORTANTE Não se esqueça de clicar em **Salvar após** concluir os mapeamentos.**
   - Unidade de negócios (padrão para Conta do pagador)
   - Department (padrão para Linked Account)
   - Equipe
   - Proprietário do sistema
   - Centro de custos
   - Aplicativo
   - Meio ambiente
   - Projeto
   - Propósito
5. Clique em **Salvar** e, em seguida, verifique seu trabalho.
