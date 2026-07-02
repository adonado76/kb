---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Finanças de TI Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financeiro"
  - "Finanças de TI"
source_path: "cost-transparency/it-financials/itf-getting-started.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Finanças de TI Introdução

## Introdução

Use os componentes de Finanças de TI para carregar e gerenciar os dados financeiros necessários para relatórios sobre OpEx e CapEx gastos. O componente CTF-Cost Source fornece os dados financeiros básicos para todos OpEx os relatórios. O componente CapEx opcional CTF permite CapEx-specific a geração de relatórios e garante que CapEx os campos sejam exibidos apenas quando sua organização utilizar CapEx os dados.

Instale e configure esses componentes antes de carregar seus dados financeiros. Após a instalação dos componentes, carregue seus conjuntos de dados de custos e orçamento e mapeie-os para as tabelas de dados mestres apropriadas.

## Instalação de componentes

**CTF - Fonte de custos (instalado automaticamente)**

O componente CTF-Fonte de Custos é instalado automaticamente quando o projeto Padrão de Custos é criado. Ele fornece a estrutura de dados mestre necessária para todos OpEx os relatórios. Você utilizará este componente ao carregar custos reais, orçamentos de custos e campos de mapeamento para a tabela Dados mestre da fonte de custos.

**CTF- CapEx (Componente adicional)**

O componente CapEx CTF separa CapEx os relatórios dos OpEx relatórios. Instale este componente se sua organização carregar CapEx dados ou exigir relatórios CapEx específicos.

Use este componente quando:

- Você deseja analisar as despesas de capital por conta, pool de custos e centro de custos.
- Você precisa revisar CapEx as variações nos relatórios de orçamento e previsão.

**CTF - Relatórios de Origem de Custos NX (Componente Adicional)**

Este componente fornece relatórios NX predefinidos com base nos dados da Origem de Custos para a análise de custos em centros de custo, grupos de contas e períodos.

Use este componente quando:

- Você precisa de relatórios de custos padrão
- Você deseja comparar os valores reais com os orçamentos
- Você precisa de relatórios consistentes sobre fontes de custo

**Para instalar o componente:**

1. Abra o projeto Padrão de Cálculo de Custos.
2. Selecione **Projeto** > **Componentes**.
3. Selecione **CTF – CapEx**.
4. Clique em **Instalar**.

Após a instalação, prossiga com o carregamento dos dados nas tabelas de dados mestre.

## Fontes comuns de dados

Os valores relativos a custos e orçamentos são normalmente extraídos de fontes como o livro razão e o plano de contas. Esses dados são frequentemente fornecidos por aplicativos como Oracle, SAP, Lawson, Netsuite e Cognos Financial Statement Reporting. Os dados que você usar determinarão o nível de detalhes disponível e as colunas que você mapeará para a tabela Dados mestre da fonte de custo.

**Conjuntos de dados**

Pode ser necessário carregar várias tabelas e mapeá-las para as tabelas principais fornecidas com os componentes. As tabelas são:

- Contabilidade geral (GL): fonte de verdade para todas as transações financeiras, categorizadas por conta e frequentemente associadas a centros de custo ou proprietários regionais.
- Plano de Contas: Uma lista completa das contas utilizadas no sistema financeiro. Determina a granularidade disponível no nível da conta para relatórios. Uma conta é um registro exclusivo para cada tipo de ativo, passivo, patrimônio líquido, receita e despesa.
- Hierarquia organizacional: define a estrutura da organização, incluindo a propriedade do centro de custos e as relações hierárquicas.
- Orçamento: gastos previstos por centro de custos e conta. Necessário para a análise de variações orçamentárias e previsões.
