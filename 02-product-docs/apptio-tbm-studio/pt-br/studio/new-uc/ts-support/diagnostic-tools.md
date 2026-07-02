---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Ferramentas de diagnóstico"
breadcrumb:
  - "TBM Studio"
  - "Solução de problemas e suporte"
source_path: "studio/new-uc/ts-support/diagnostic-tools.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Ferramentas de diagnóstico

O TBM Studio oferece várias ferramentas para diagnosticar problemas de desempenho, monitorar compilações e analisar o comportamento do sistema.

## Calc Explorer

O Calc Explorer permite que os administradores analisem o desempenho da compilação e identifiquem componentes que exigem muitos cálculos. Acesse pela guia "Build" > "Calc Explorer".

**Definições principais:**

|  |  |
| --- | --- |
| **Termo** | **Descrição** |
| Construir | Um ponto específico no processo de check-in que pode ser calculado |
| Tipo de cálculo | Todos (cálculo completo), Parcial (apenas entidades dependentes) ou Nenhum (não é necessário cálculo) |
| Esforço de cálculo | Uma estimativa dos recursos necessários, expressa em milhões (por exemplo, 3.2M ) |
| Consulta | A menor unidade de cálculo, geralmente uma entidade referente a um período específico |

**Como usar o diagrama de Sankey:**

Para todas as compilações, o Calc Explorer exibe um diagrama de Sankey que mostra as entidades dimensionadas e classificadas por esforço de cálculo. Clique na entidade “Relatórios” para acessar os 10 principais relatórios. Passe o mouse sobre os nomes dos relatórios para ver as porcentagens de esforço de cálculo. Clique com o botão direito do mouse para abrir documentos ou ver os caminhos completos dos arquivos. Continue a investigação para identificar componentes específicos que apresentam problemas.

## Fila de cálculos

A Fila de Cálculos mostra o status das compilações em todos os ambientes. Acesse pela guia Compilação > Fila de cálculos.

|  |  |
| --- | --- |
| **Estado** | **Descrição** |
| Pendente | A compilação está na fila e aguardando processamento |
| Calculando | Construção em andamento (mostra os cálculos concluídos em relação ao total) |
| Término | Compilação concluída (mostra o tempo decorrido desde a conclusão e a duração) |

## Painel de erros

O Painel de Erros oferece uma visão consolidada de todos os erros do projeto. Acesse pela guia Projeto > Erros. Analise a lista de erros, clique em cada um para ver os detalhes e acesse o documento afetado. Os erros impedem o cálculo do modelo até que sejam resolvidos.

## Histórico de check-in

Acompanhe as alterações feitas nos documentos ao longo do tempo. Selecione um documento no Explorador de Projetos, clique com o botão direito do mouse na guia na parte inferior e selecione Histórico de Check-in. Visualizar a data, o usuário, o status e as mensagens de cada check-in. A partir daqui, você também pode reverter para uma configuração anterior, se necessário.
