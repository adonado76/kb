---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Propriedades comuns dos gráficos"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/common-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Propriedades comuns dos gráficos

Todos os gráficos compartilham um conjunto comum de propriedades configuráveis, acessíveis pela caixa de diálogo Propriedades. Selecione um gráfico e acesse suas propriedades através do ícone Propriedades na guia Autor, do menu Ações (pequeno triângulo no cabeçalho do gráfico) ou clicando com o botão direito do mouse no gráfico.

**Propriedades da guia Gráfico**

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Etiqueta do eixo X | Selecione a coluna de origem para os valores do eixo X. |
| Etiqueta de valor Y | Selecione a coluna de origem para os valores do eixo Y. |
| Escala do eixo Y | Selecione a escala linear ou logarítmica para o eixo Y. |
| Especificações de cor | Insira sequências de formatação de cores para personalizar as cores das métricas (por exemplo, "Custo=azul;Orçamento=verde"). |
| Formato do número do gráfico | Digite um formato para os números dos eixos (por exemplo, "#,###" para o separador de milhares). |
| Prefixo do número da tabela | Texto exibido antes dos números (por exemplo, "$" para dólares). |
| Sufixo do número do gráfico | Texto exibido após os números (por exemplo, “M” para milhões). |
| Mostrar valores dos dados | Exibir os valores dos dados para cada ponto do gráfico. |
| Localização da legenda | Posicione a legenda: Norte, Sul, Leste, Oeste ou Oculta. O padrão é o Sul. |
| Ocultar linhas da grade | Remova as linhas de grade horizontais e verticais do gráfico. |
| Incluir o zero no eixo Y | Forçar o eixo Y a começar em 0, em vez de usar o dimensionamento automático. |

**Propriedades da guia Dados**

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Número máximo de linhas | Limita os elementos exibidos. Em gráficos de barras: número de barras. Em gráficos de pizza: número de fatias. Itens excedentes agrupados em "Outros". |
| Incluir colunas\* | Restringir as colunas exibidas às selecionadas (apenas gráficos antigos). |
| Excluir colunas\* | Permitir todas as colunas, exceto as selecionadas (apenas gráficos antigos). |
| Mostrar linhas com todos os valores iguais a zero\* | Substituir o comportamento padrão para exibir linhas com valor zero (apenas gráficos antigos). |
| Conjunto de dados de referência\* | Trocar os eixos X e Y no gráfico (apenas gráficos antigos). |

*\* Apenas gráficos antigos*

**Propriedades da guia Geral**

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Nome | O título exibido no cabeçalho do gráfico (quando a opção “Mostrar cabeçalho” está ativada). |
| Legenda | Informações adicionais exibidas ao lado do gráfico. HTML permitido (sem links por motivos de segurança). |
| Posição da legenda | Posicione a legenda: em cima, embaixo, à esquerda, à direita ou ocultar. |
| Mostrar borda | Exiba uma borda ao redor do gráfico. As bordas ocultas aparecem ao passar o mouse sobre elas no modo de edição. |
| Mostrar cabeçalho | Exibir o nome do gráfico como cabeçalho. A configuração padrão está ativada. |
| Título do resumo | Quebre nomes de gráficos longos para que se ajustem à largura do gráfico. |

**Propriedades da guia "Avançado"**

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Período de dados | Fixar o gráfico a um período específico, independentemente da data selecionada no relatório. |
| Ocultar aviso de hidratação | Suprimir avisos quando um gráfico exibir intencionalmente dados de várias fontes. |
| Atualização automática ao concluir o cálculo | Atualizar automaticamente o gráfico quando os cálculos em segundo plano forem concluídos. |
| Encurtar automaticamente os nomes das colunas | Exibir apenas a parte dos nomes das colunas após o separador de ponto. |

**Tópico principal:** [Componentes do relatório: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
