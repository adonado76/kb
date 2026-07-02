---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configuração da coluna"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas"
source_path: "studio/new-uc/reference/report-studio-reference/column-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuração da coluna

Cada coluna de uma tabela pode ser configurada individualmente no que diz respeito à exibição, formatação e comportamento.

**Tipos de colunas**

|  |  |  |
| --- | --- | --- |
| **Tipo de coluna** | **Descrição** | **Origem** |
| Dimension | Colunas de rótulos/texto das tabelas. Usado na área “Linhas” para agrupamento. | Seção "Tabelas" no Explorador de Projetos |
| Métrica | Colunas numéricas com formatação predefinida. Inclui o modelo e as métricas calculadas. | Seção de métricas no Explorador de Projetos |
| Fórmula | Colunas calculadas personalizadas usando fórmulas. Pode fazer referência a outras colunas e funções. | Criado na guia Dados > Nova coluna |
| Calculado | Colunas derivadas: Contagem, Porcentagem, Variação, Comparação, Ícones de limiar. | Criado por meio das configurações do campo de valor |
| Baseado no calendário | Valores agregados por período: acumulado no ano (YTD), acumulado no trimestre (QTD), ano fiscal (FY), último ano fiscal (LFY), anual (ANN), últimos 12 meses (LTM), etc. | Criado na guia Fórmulas > Datas |
| Gráfico de tendência | Pequena linha de tendência que mostra dados históricos. | Criado na guia Fórmulas > Datas > Gráfico de tendência |
| Indicador de status | Ícones que indicam o status do valor (vermelho/amarelo/verde, setas, etc.). | Criado através da função Ícone |
| Total | Somatar os totais das linhas em várias colunas de valores. | Criado na guia Dados > Soma |
| Espaçador | Coluna em branco para separação visual. | Criado na guia Dados > Inserir > Coluna espaçadora |
| Editável | Coluna editável pelo usuário em tabelas editáveis. | Configuração editável da tabela |

**Adicionar colunas de fórmula**

As colunas de fórmula permitem realizar cálculos personalizados utilizando dados da tabela.

**Para adicionar uma coluna de fórmula:**

1. Selecione a tabela e clique na guia Dados.
2. Clique em “Nova coluna”.
3. Digite um nome para a coluna.

1. Selecione “Inserir fórmula” e insira a fórmula no formato “ table.column ”.
2. Selecione o Formato, o Tipo e, se desejar, ative a opção "Somatável".
3. Clique em OK.

**Referência de propriedades de coluna**

|  |  |  |
| --- | --- | --- |
| **Propriedade** | **Descrição** | **Valores** |
| Nome | Nome de exibição da coluna. Aceita caracteres alfanuméricos. | Qualquer texto |
| Tipo | Tipo de dados dos valores da coluna. | Automático, Numérico, Etiqueta, Data |
| Formato | Formato de exibição dos valores. | Número, Moeda, Porcentagem, Data, Avançado (fórmula) |
| Somável | Se a coluna pode ser somada com segurança quando agrupada. Desativar para colunas de proporção calculada. | Sim/Não (padrão: Não) |
| Decimais | Número de casas decimais para valores numéricos. | 0-10 (varia de acordo com o formato) |
| Usar separador de agrupamento | Adiciona o separador de milhares de acordo com a configuração regional do projeto. | Sim/não |

**Largura da coluna**

**Para ajustar o tamanho de uma coluna:**

- Posicione o ponteiro do mouse sobre a borda direita do cabeçalho da coluna. Quando o cursor se transformar em uma seta de redimensionamento, clique e arraste.
- Clique com o botão direito do mouse no cabeçalho da coluna > Formatação > Definir largura e insira a largura em pixels.

**Visibilidade da coluna**

As colunas podem ser ocultadas durante a configuração da tabela. As colunas ocultas continuam a participar dos cálculos, mas não são exibidas.

**Para ocultar uma coluna:**

- Clique com o botão direito do mouse no nome da coluna na área Valores do painel Configuração do componente e selecione Ocultar. O nome da coluna está desativado.

**Para exibir uma coluna oculta:**

- Clique com o botão direito do mouse no nome da coluna em cinza no painel "Configuração do componente" e selecione "Mostrar".

**Tópico principal:** [Componentes do relatório: Tabelas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
