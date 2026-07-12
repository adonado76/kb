---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configuração de cores"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/color-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuração de cores

**Paletas de cores personalizadas**

**Aplicável a:** TBM Studio 12.10.10 e versões posteriores

É possível aplicar paletas de cores personalizadas à maioria dos tipos de gráficos. Acesse as paletas de cores na guia Relatório > opção Paleta de cores. As paletas podem ser aplicadas no nível do relatório ou no nível da coleção de relatórios.

**Limitações:** As paletas de cores personalizadas não podem ser aplicadas aos gráficos de árvore ou em cascata. As paletas de cores também não afetam tabelas, cores de fontes/rótulos, filtros, planos de fundo ou componentes de KPI.

**Sintaxe de especificações de cor**

Para um controle mais preciso das cores de cada métrica, use a propriedade Color Spec. Insira as especificações de cor no seguinte formato:

`metric=color-spec[;metric=color-spec]`

**Exemplo:** `Cost=blue;Budget=green;!purple`

Isso define o Custo como azul, o Orçamento como verde e exclui o roxo da atribuição automática de cores.

**Palavras-chave de cores disponíveis**

**Cores sólidas:** preto, cinza, cinza claro, cinza escuro, branco, transparente

**Cores em degradê:** azul, vermelho, verde, amarelo, violeta, marrom, azul-celeste, verde-claro, laranja, azul-escuro, verde-escuro, roxo, azul-turquesa, rosa, azul-petróleo, carmesim

**Dica:** coloque o prefixo “flat” antes das cores com gradiente para obter versões sem gradiente (por exemplo, flatblue). Também são aceitos códigos hexadecimais (por exemplo, Cost=#082f6d ).

**Tópico principal:** [Componentes do relatório: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
