---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Projetos Introdução"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financeiro"
  - "Projetos"
source_path: "cost-transparency/it-financials/project-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Projetos Introdução

## Introdução

Use o recurso Projetos para acompanhar, analisar e gerenciar os gastos com projetos de TI em centros de custo, projetos e torres de TI. O componente **CTF – Projetos** permite visibilidade dos investimentos em projetos, adesão ao orçamento e tendências de gastos, apoiando um melhor controle financeiro e alinhamento estratégico.

Antes de usar os relatórios de projetos, instale o componente necessário e carregue os dados de custos do projeto na tabela de dados mestre.

## Instalação de componentes

**CTF - Projetos**

O componente Projetos CTF fornece a estrutura de dados necessária para analisar os gastos do projeto por tipo, centro de custos, projeto e torre de TI.

**Pré-requisitos**

- CTF - Fonte de custos
- CTF - Trabalho
- CTF - Unidades de Trabalho ou CTF - Controle de Tempo

Após instalar o componente, você deve carregar os dados do projeto e mapeá-los para a tabela **Dados Mestre do Projeto** para habilitar os relatórios e análises de gastos do projeto.

**Fontes comuns de dados**

Os dados do projeto são normalmente obtidos a partir de aplicativos de gerenciamento de projetos e portfólios que acompanham as finanças, os cronogramas e a propriedade do projeto. Esses sistemas fornecem detalhes como orçamentos de projetos, gastos reais, status do projeto e classificação do investimento.

As fontes comuns incluem ServiceNow, Project Portfolio Suite, Clarity PPM, Jira Align / Jira Advanced Roadmaps, MS Project Online / Project Server, Planview etc.

## Conjuntos de dados principais

**Tabela de dados mestre do projeto:** define os dados necessários para relatórios de custos e orçamento do projeto. Para preencher esta tabela, carregue um conjunto de dados do projeto e mapeie-o para os campos apropriados na tabela de dados mestre. Normalmente, você carrega um único conjunto de dados do projeto, que é anexado e mapeado na tabela Dados-mestre do projeto.

**Tabela de mapeamento de projetos para aplicações:** esta tabela é usada para associar projetos às aplicações que eles afetam. Esse mapeamento permite visibilidade sobre como os investimentos em projetos contribuem para os custos, mudanças e esforços de modernização das aplicações.
