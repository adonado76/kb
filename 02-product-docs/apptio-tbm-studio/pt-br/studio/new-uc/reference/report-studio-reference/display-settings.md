---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurações de exibição"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Propriedades do relatório"
source_path: "studio/new-uc/reference/report-studio-reference/display-settings.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurações de exibição

As configurações de exibição controlam a apresentação visual e o comportamento de atualização dos relatórios.

**Atualização diferida**

A atualização diferida controla a rapidez com que os relatórios são atualizados quando os usuários interagem com filtros, segmentadores e seletores. Essa configuração ajuda a gerenciar o desempenho de relatórios complexos.

|  |  |
| --- | --- |
| **Opção** | **Comportamento** |
| Atraso na atualização: 3s | O sistema aguarda 3 segundos após a seleção de um filtro antes de atualizar o relatório. Permite que os usuários façam várias seleções antes que a atualização ocorra. Esta é a configuração padrão. |
| Atualização manual | O relatório não é atualizado até que o usuário clique explicitamente em “Atualizar”. Recomendado para relatórios extensos com vários filtros e seletores, nos quais cada atualização leva muito tempo. |

**Padrão no nível do projeto:** acesse a guia Projeto > Configurações do projeto > Atualização diferida para definir o padrão para todos os relatórios.

**Substituição no nível do relatório:** faça o check-out do relatório e, em seguida, altere a configuração de atualização na guia Relatório.

**Paleta de cores**

Os relatórios podem utilizar paletas de cores personalizadas para garantir a consistência da identidade visual em gráficos e visualizações. As paletas de cores são definidas no nível do ambiente pelos administradores e podem ser aplicadas tanto no nível da coleção de relatórios quanto no nível de cada relatório individual.

**Hierarquia da paleta de cores:**

1. A paleta no nível do relatório (se definida) tem prioridade
2. A paleta de coleta de relatórios é aplicada se não houver uma substituição no nível do relatório
3. As cores padrão do Apptio serão aplicadas caso não haja uma paleta personalizada definida

**Para aplicar uma paleta de cores:**

1. Confira o relatório
2. Vá até a guia Relatório > Paleta de cores
3. Escolha entre paletas personalizadas ou opções predefinidas

Nota: *As paletas de cores afetam a maioria dos tipos de gráficos, exceto os gráficos em cascata e os mapas de árvore. Elas não afetam a formatação da tabela, as fontes, os filtros, os planos de fundo nem os componentes de KPI.*

**Tópico principal:** [Propriedades do relatório](../../../../studio/new-uc/reference/report-studio-reference/report-properties.html)
