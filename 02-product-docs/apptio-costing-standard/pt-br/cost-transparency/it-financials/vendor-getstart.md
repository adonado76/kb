---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Introdução para fornecedores"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financeiro"
  - "Fornecedor"
source_path: "cost-transparency/it-financials/vendor-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Introdução para fornecedores

Use o recurso Fornecedores para analisar os gastos com fornecedores de TI em toda a organização e apoiar a transparência, a consolidação e as decisões de otimização dos fornecedores. Os relatórios de fornecedores são ativados através da instalação do componente **CTF – Fornecedores** e do carregamento dos dados de gastos com fornecedores no projeto Padrão de Custos.

Antes de usar os relatórios de fornecedores, instale os componentes necessários e certifique-se de que os dados dos fornecedores sejam carregados e mapeados para a tabela de dados mestres de fornecedores.

## Instalação de componentes

- **CTF – Fornecedores** – O componente **CTF – Fornecedores** permite a análise de gastos por fornecedor no Costing Standard. Ele não é instalado automaticamente e deve ser adicionado explicitamente ao projeto.

Este componente permite:

- Visibilidade dos gastos com fornecedores em toda a organização
- Análise da concentração e fragmentação dos fornecedores
- Relatórios de gastos com fornecedores em centros de custo, projetos e torres de recursos de TI

Após instalar este componente, os dados do fornecedor devem ser carregados e mapeados para a tabela de dados mestre do fornecedor para preencher os relatórios do fornecedor.

**CTF - Relatórios de fornecedores NX (componente adicional)**

Este componente oferece relatórios NX predefinidos com base nos dados dos fornecedores para a análise de custos entre fornecedores, categorias e períodos.

Use este componente quando:

- Você precisa de relatórios de custos padrão dos fornecedores
- Você deseja comparar os valores reais com os orçamentos
- Você precisa de relatórios consistentes dos fornecedores

## Pré-requisitos

**CTF – Fonte de custos** – Fornece os dados básicos de custos necessários para associar os gastos aos fornecedores.

**Fontes comuns de dados** - Os dados dos fornecedores são normalmente obtidos do livro razão ou dos dados mestres dos fornecedores mantidos nos sistemas financeiros. Esses sistemas fornecem os identificadores dos fornecedores e os gastos associados necessários para a geração de relatórios no nível do fornecedor.

## Conjuntos de dados principais

- **Dados mestre do fornecedor** - A tabela Dados mestre do fornecedor armazena identificadores de fornecedores e atributos relacionados usados para análise no nível do fornecedor. Normalmente, uma tabela de dados de um único fornecedor é carregada e anexada a essa tabela de dados mestre.

O conjunto de dados carregado deve incluir campos que possam ser mapeados para a estrutura de dados mestre do fornecedor, a fim de permitir relatórios precisos.
