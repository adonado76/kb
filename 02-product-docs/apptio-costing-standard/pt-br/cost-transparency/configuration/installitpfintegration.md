---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Instalar os componentes de integração do ITPF"
breadcrumb: []
source_path: "cost-transparency/configuration/installitpfintegration.html"
images:
  - "resources/images/ct_images/gear_icon.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Instalar os componentes de integração do ITPF

Três componentes estão disponíveis como parte do módulo Costing Standard Foundation para conectar o Costing Standard (CT) ao IT Planning Foundation (ITPF).

## Introdução

Use os componentes de integração do ITPF para fazer o seguinte:

- Assegurar que os dados de referência do CT e do ITP tenham uma fonte de verdade em TBM Studio e disponibilizar os dados para o ITP.
- Disponibilize os dados reais no aplicativo Costing Standard para o aplicativo ITP.
- Disponibilizar os dados de orçamento e previsão no aplicativo ITP para o aplicativo CT.

Nota:

A troca de dados é iniciada a partir do aplicativo ITP.

Para que a integração funcione, você deve configurar o CT e o ITPF.

Componentes

- Apptio Integração ITPF - Esse componente passa dados orçamentários, de previsão e reais entre o CT e o ITPF. O componente Cost Source deve ser instalado antes de você instalar o componente Apptio ITPF Vendor Integration. Três conjuntos de dados são instalados:
  - O ITPF Actuals é uma transformação dos dados mestre da origem de custos que permite a transferência de dados reais do CT para o ITPF.
  - O ITPF Budget e o ITPF Forecast são os destinos do orçamento do ano fiscal e dos últimos dados de previsão transferidos do ITPF para o CT. Esses conjuntos de dados são mapeados para os dados mestre da fonte de custos no CT.
- Apptio Integração de ativos do ITPF - Esse componente passa os dados do plano de ativos do ITPF para o CT. O componente instala os conjuntos de dados ITPF Asset Budget e ITPF Asset Forecast. Os seguintes componentes devem ser instalados antes de você instalar o componente de integração Apptio ITPF:
  - Fonte de custos
  - Ativos fixos
- Apptio Integração do fornecedor ITPF - Esse componente passa os dados relacionados aos planos de contrato do fornecedor do ITPF para o CT. O componente instala os conjuntos de dados ITPF Contract Budget e ITPF Contract Forecast. O componente Cost Source deve ser instalado antes de você instalar o componente Apptio ITPF Vendor Integration.

## Instalar os componentes

Para instalar os componentes:

1. Abra o site TBM Studio.
2. Na guia Projeto, clique em **Componentes**.
3. Clique no componente **Apptio ITPF Integration**.
4. Clique em **Install (Instalar** ).
5. Clique no componente **Apptio ITPF Asset Integration**.
6. Clique em **Install (Instalar** ).
7. Clique no componente **Apptio ITPF Vendor Integration**.
8. Clique em **Install (Instalar** ).

Se você quiser usar os componentes Fornecedores e Ativos no ITP, deverá instalar os componentes Integração do fornecedor do ITPF e Integração do ativo do ITPF para garantir que os seguintes conjuntos de dados estejam instalados:

- Dados mestre do fornecedor de ITP
- ITPF Tipo de contrato Master
- Orçamento do contrato de ITPF
- Previsão de contrato de ITPF
- Mestre de classes de ativos ITP

## Dados principais

Para obter uma descrição dos campos da tabela de dados mestre e dos relatórios instalados com cada componente, consulte a descrição listada em cada componente. Para exibir as descrições, faça o seguinte:

1. Na guia Projeto, clique em **Componentes**.
2. Clique em um componente para abri-lo na página de descrição.

## Configurar o aplicativo ITPF

Para configurar o ITPF, abra o aplicativo ITPF, clique no ícone Configurações (![ícone de configurações](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/gear_icon.png)) e, em seguida, clique em **Cost Transparency Integration**. Para obter informações sobre o preenchimento dos campos obrigatórios, consulte [Integrar com Costing
Standard](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=administration-integrate-cost-transparency "(Abre em uma nova guia ou janela)").
