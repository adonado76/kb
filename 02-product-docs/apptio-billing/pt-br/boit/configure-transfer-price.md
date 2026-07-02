---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Configurar o preço de transferência"
breadcrumb: []
source_path: "boit/configure-transfer-price.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Configurar o preço de transferência

aplica-se a: Billing Standard em TBM Studio 12.7 e posterior

O preço de transferência refere-se às regras e aos métodos para determinar o preço de transações dentro e entre entidades jurídicas que estão sob propriedade ou controle comum. Muitas organizações multinacionais, especialmente nos setores de serviços bancários e financeiros, dividem seus negócios em entidades jurídicas separadas (por exemplo, separando as operações de banco de investimento das operações de banco comercial) entre os países em que operam.

Quando os serviços são consumidos entre pessoas jurídicas, um preço de transferência ou uma margem de lucro é frequentemente aplicado a esses serviços. Os analistas financeiros das empresas globais precisam cobrar e alocar com precisão esses custos e preços de serviços entre as entidades jurídicas e ajustar as faturas para atender aos requisitos de relatórios regulamentares e de conformidade.

**VEJA TAMBÉM** : [Relatório de Transferência Interempresarial e Cobrança Cruzada (Preços de Transferência) - Billing Standard](transfer-pricing-report.html "(Abre em uma nova guia ou janela)")

Pré-requisitos

- Instale e configure os seguintes componentes do site Billing Standard :
  - Billing Standard Fundação
  - Billing Standard Preço
- Colete os seguintes dados:
  - Nomes e relacionamentos entre entidades jurídicas geográficas, os serviços que prestam e o mecanismo de preço de transferência usado em cada caso
  - Regras de tributação que se aplicam à marcação de preços de transferência entre localizações geográficas específicas
  - Uma tabela de regras seguidas por unidades de negócios de cobrança cruzada que residem na mesma entidade legal que uma entidade legal consumidora (consulte a tabela a seguir para obter mais informações)

**Conjuntos de dados e modelos de preços de transferência**

Os seguintes conjuntos de dados são usados na configuração:

- **Dados mestre de preços de transferência entre empresas** - Esse conjunto de dados usa dados de clientes que definem taxas de marcação de preços de transferência entre entidades jurídicas específicas.
- **Inter Company Transfer Pricing (Preços** de transferência entre empresas) - Essa é a versão modelada dos dados mestre de preços de transferência entre empresas.
- **Dados mestre de tributação de entidades jurídicas** - Esse conjunto de dados usa dados de clientes que definem as taxas de tributação de markup de preços de transferência entre entidades jurídicas específicas.

Os modelos a seguir são criados com o caso de uso de preço de transferência. As setas vermelhas indicam a origem dos motoristas.

Configurar o preço de transferência

1. Faça o upload dos seguintes conjuntos de dados:   

   | Conjunto de dados | Caso de uso | Descrição | Colunas chave |
   | --- | --- | --- | --- |
   | Taxas de preços de transferência | Preços de transferência, preços de transferência com tributação | Define taxas de marcação de preços de transferência entre entidades jurídicas e, em alguns casos, serviço por serviço | Entidade jurídica fornecedora, local de fornecimento, serviço (opcional), entidade jurídica consumidora, local de consumo, taxa de marcação (por exemplo, insira 0.15 para uma marcação de 15%) |
   | Taxas de tributação de preços de transferência | Preços de transferência com tributação | Define as taxas de tributação da marcação de preços de transferência entre entidades jurídicas e, em alguns casos, serviço por serviço | Entidade jurídica fornecedora, local de fornecimento, serviço (opcional), entidade jurídica consumidora, local de consumo, taxa de tributação de marcação (por exemplo, insira 0.15 para uma taxa de imposto de 15%) |
2. Anexar os conjuntos de dados aos conjuntos de dados mestre correspondentes.
3. Verifique se as métricas modeladas estão fluindo corretamente do preço de transferência entre empresas, por meio de unidades de negócios, para entidades jurídicas e cobranças cruzadas.
