---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Gráficos em cascata"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/waterfall-chart.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos em cascata

**Aplicável a:** TBM Studio 12.2 e versões posteriores

Os gráficos em cascata (também chamados de gráficos em ponte) mostram o efeito cumulativo de valores positivos e negativos sucessivos sobre um valor inicial. Eles se destacam na explicação de variações, como a diferença entre os custos orçados e os reais ou entre um período e outro.

**Entendendo os componentes do gráfico em cascata**

- Valores de referência: As colunas inteiras de início e fim (e, opcionalmente, colunas de períodos intermediários, como trimestres).
- Etapas intermediárias: Colunas flutuantes entre os valores de base, indicando contribuições positivas (para cima) ou negativas (para baixo).
- Coluna “Inexplicável”: Representa qualquer variação não explicada pelas etapas intermediárias definidas.
- Tabela explicativa: Uma tabela configurável abaixo do gráfico onde são definidas as etapas intermediárias.

**Criação de um gráfico em cascata**

1. Na guia Relatório, clique no ícone Cascata.
2. No painel "Configuração em cascata", selecione um objeto de modelo na lista suspensa.
3. Na seção Métricas, arraste uma métrica modelada para a área Valores (isso define o valor inicial).
4. Arraste uma segunda métrica para a área Métricas (isso cria o valor final).
5. Para alterar os intervalos de tempo, clique com o botão direito do mouse no intervalo de tempo, clique em Shift e, em seguida, digite um número positivo ou negativo.

**Adicionando etapas intermediárias**

Os passos intermediários explicam a variação entre os valores de referência. Eles devem ser adicionados no ambiente de produção:

1. Mude para o ambiente de produção.
2. Abra o relatório com o gráfico em cascata.
3. Clique em “Adicionar explicação” na parte inferior da tabela de etapas intermediárias.
4. Insira um rótulo na coluna “Etapa”, um valor positivo ou negativo na coluna “Valor” e uma descrição na coluna “Explicação”.
5. Reorganize os passos clicando com o botão direito do mouse e selecionando “Subir” ou “Descer”.

Observação: as explicações são armazenadas no banco de dados de planejamento de TI. Se esse banco de dados não estiver instalado, não será possível adicionar explicações.

**Opções do gráfico em cascata (guia Cascata)**

- Mostrar tabela: exibe a tabela explicativa abaixo do gráfico. Ao desmarcar esta opção, a tabela fica oculta para os visualizadores.
- Mostrar linhas detalhadas: exibe etapas intermediárias associadas a valores específicos do filtro na parte inferior da tabela de etapas (somente leitura).
- Explicação nas dicas de ferramenta: exibe o texto do campo “Explicação” ao passar o mouse sobre as barras.
- Número: Formata os números exibidos no gráfico em cascata.
- Cores: Personalize as cores das barras de aumento, das barras de diminuição e das barras de total.

Importante: Os valores do gráfico em cascata são sempre exibidos na moeda base definida para o projeto. Os gráficos em cascata não suportam várias moedas.

**Tópico principal:** [Componentes do relatório: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
