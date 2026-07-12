---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Personalizações e como elas afetam as atualizações de conteúdo"
breadcrumb:
  - "Costing Standard"
  - "Administração"
  - "Atualização do padrão de cálculo de custos"
source_path: "cost-transparency/admin/cust-contet.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Personalizações e como elas afetam as atualizações de conteúdo

Se você personalizou o conteúdo do IBM Apptio e atualizar um componente, o processo de atualização não atualizará os elementos personalizados do componente. A atualização manterá os elementos personalizados intactos (nenhuma alteração será aplicada) e atualizará todos os elementos que não foram personalizados.

Por exemplo, se você alterou um conjunto de dados mestre e não fez outras personalizações, não obterá a nova versão do conjunto de dados mestre ao atualizar. No entanto, você receberá outros relatórios, bem como a atualização dos outros elementos de conteúdo relacionados a esse componente, como o conjunto de dados mestre e as métricas.

Se você não personalizou seu conteúdo Apptio, o processo de atualização substituirá suas versões dos mesmos elementos de conteúdo pela versão mais recente.

Observe que isso pode resultar em uma alteração na funcionalidade.

## Customizações

As ações a seguir são consideradas personalizações de um projeto, se realizadas em elementos prontos para uso, como tabelas, relatórios e métricas.

- Removendo uma coluna de um conjunto de dados mestre
- Alterando um componente do relatório
- Alterando uma métrica, perspectiva ou campo publicado
- Alterar o tipo de coluna de dados, por exemplo, de Numérico para Rótulo

## Configurações

As seguintes ações não são consideradas uma personalização do projeto. São configurações.

- Mapeamento de um conjunto de dados para um conjunto de dados mestre
- Alterando a configuração de visibilidade de um conjunto de dados, como Ocultar do mecanismo de inferência
- Alterando a configuração da categoria de um conjunto de dados

## Identificar personalizações

A seção Elementos personalizados da página Detalhes do componente identifica as personalizações entre seu projeto e a versão atual.

Clique no sinal de mais (+) ao lado dos elementos identificados para obter mais informações sobre a personalização.
