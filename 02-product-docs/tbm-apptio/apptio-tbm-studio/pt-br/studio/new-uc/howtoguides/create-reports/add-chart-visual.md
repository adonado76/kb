---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Adicionar gráficos e visualizações"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar relatórios"
  - "Noções básicas sobre relatórios"
source_path: "studio/new-uc/howtoguides/create-reports/add-chart-visual.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adicionar gráficos e visualizações

**Objetivo:** Adicionar gráficos para visualizar padrões, tendências e comparações de dados

**Quando usar:** Quando você quiser comunicar insights rapidamente, mostrar tendências ao longo do tempo, comparar categorias ou destacar proporções

**Tempo estimado:** 10 a 15 minutos

## Escolhendo o tipo de gráfico certo

Antes de inserir um gráfico, pense na mensagem que você quer transmitir:

|  |  |  |
| --- | --- | --- |
| **Tipo de gráfico** | **Ideal para** | **Exemplo de caso de uso** |
| **Barra (horizontal)** | Comparando categorias com nomes longos | Custos por nome do aplicativo |
| **Coluna (vertical)** | Comparando categorias | Custos por unidade de negócios |
| **Torta/Donut** | Mostrando proporções (partes de um todo) | Distribuição orçamentária entre os departamentos |
| **Linha/Tendência** | Mostrando a evolução ao longo do tempo | Tendências dos custos mensais |
| **Queda de água** | Análise de variância | Variação de custos em relação ao ano anterior |

## Orientações para a escolha dos tipos de gráficos:

- **Use gráficos de barras/colunas** ao comparar itens distintos (centros de dados, unidades de negócios, fornecedores)
- **Use gráficos de linhas** quando tiver dados de séries temporais e quiser mostrar tendências
- **Use gráficos de pizza com moderação** — eles funcionam melhor com 3 a 7 categorias e apenas valores positivos
- **Use gráficos empilhados** quando precisar mostrar tanto os totais quanto os detalhes
- **Use gráficos em cascata** para a análise de variação ou para mostrar o efeito cumulativo de valores sequenciais

## Passos

1. Abra o seu relatório e **dê uma olhada**.
2. Clique na guia **Relatório** e, em seguida, clique em **Gráfico**. É exibido um gráfico provisório (por padrão, uma barra horizontal) e o painel “Configuração de Componentes Ad Hoc” é aberto.
3. Selecione um **objeto de modelo** no menu suspenso na parte superior do painel Configuração.
4. Arraste um campo de dimensão para a área **da legenda**. Por exemplo, arraste “Data Center” para criar barras para cada data center.
5. Arraste uma métrica para a área **Valores**. Por exemplo, arraste “Custo” para medir os custos.
6. (Opcional) Para gráficos de tendências, arraste um campo de tempo para a área **do eixo**.
7. Para alterar o tipo de gráfico, clique na guia **“Ad Hoc”** e selecione um estilo de gráfico na seção **“Visualizar”** (Barra, Coluna, Barra/Coluna empilhada, Circular, Linha).

## Resultados esperados

- O gráfico apresenta seus dados de forma visual
- Ao passar o mouse sobre os elementos do gráfico, são exibidas dicas de ferramentas com os valores
- Clicar nos itens da legenda oculta/exibe essa série

## Armadilhas comuns

- **Gráficos de pizza com números negativos:** os gráficos de pizza não podem exibir valores negativos. Se os seus dados puderem conter valores negativos, use um gráfico de barras.
- **Excesso de itens na legenda:** gráficos com mais de 7 a 10 séries tornam-se difíceis de ler. Use filtros ou mude para uma tabela.
- **Dados de tendência ausentes:** Se o seu gráfico de tendências parecer incorreto, verifique se o campo de tempo está na área do eixo, e não na legenda.

**Tópico principal:** [Noções básicas sobre relatórios](../../../../studio/new-uc/howtoguides/create-reports/report-basic.html)
