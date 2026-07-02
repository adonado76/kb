---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Propriedades da tabela"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas"
source_path: "studio/new-uc/reference/report-studio-reference/table-properties.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Propriedades da tabela

Acesse a caixa de diálogo Propriedades clicando com o botão direito do mouse na barra Total da tabela e selecionando Propriedades. As propriedades estão organizadas nas guias Dados, Geral e Avançado.

**Propriedades dos dados**

|  |  |  |
| --- | --- | --- |
| **Propriedade** | **Descrição** | **Padrão** |
| Número máximo de linhas | Número de linhas por página. Controla a paginação. | Padrão do sistema |
| Ocultar barra de navegação | Oculta os controles de paginação. Só são exibidas as linhas máximas. | Desativado |
| Incluir colunas | Limitar as colunas exibidas às selecionadas. | Todas as colunas |
| Excluir colunas | Ocultar as colunas especificadas da exibição. | Nenhum |
| Pesquisa automática | Adiciona campos de pesquisa abaixo dos cabeçalhos das colunas. | Desativado |

**Propriedades Gerais**

|  |  |  |
| --- | --- | --- |
| **Propriedade** | **Descrição** | **Padrão** |
| Nome | Nome de exibição mostrado no cabeçalho da tabela. | Nome da tabela |
| Legenda | Texto descritivo adicional. Suporta HTML (sem links). | Vazio |
| Posição da legenda | Posição da legenda em relação à tabela: Superior, Inferior, Esquerda, Direita, Ocultar. | Ocultar |
| Mostrar cabeçalho | Exiba o cabeçalho da tabela com o nome. | Ativado |
| Mostrar borda | Exiba uma borda ao redor da tabela. | Ativado |
| Título do resumo | Quebre o texto de títulos longos para que se ajuste à largura da tabela. | Desativado |

**Propriedades avançadas**

|  |  |  |
| --- | --- | --- |
| **Propriedade** | **Descrição** | **Padrão** |
| Atualização automática ao concluir os cálculos | Atualiza a tabela quando os cálculos em segundo plano forem concluídos. Disponível apenas com a política de cálculo de Publicação Dinâmica. | Desativado |
| Encurtar automaticamente os nomes das novas colunas pontilhadas | Exibe apenas a parte após o ponto final. E.g., “ Data.Cost ” aparece como “Custo”. | Desativado |
| Linhas por linha | Para tabelas com quebra automática de linha. Deixe em branco para usar o valor padrão. | Em Branco |
| Número máximo de colunas a exibir | Número máximo de colunas processadas da tabela de origem. | Todos |
| Incluir coluna PK | Inclui a coluna da chave primária padrão. | Automática |
| Usar aliases de coluna | Permite a configuração correta quando dois objetos compartilham nomes de colunas. Recomendado: Deixe selecionado. | Ativado |
| Ocultar aviso de hidratação | Suprime avisos quando os componentes exibem dados de contextos diferentes (por exemplo, ao comparar unidades de negócios). | Desativado |

**Propriedades da tabela dinâmica (versão antiga)**

|  |  |
| --- | --- |
| **Propriedade** | **Descrição** |
| Coluna de pivô | Coluna que fornece os valores da primeira coluna da tabela dinâmica. |
| Pivot Col Col | Coluna que fornece títulos para as colunas de dados na tabela dinâmica. |
| Ponto de virada Val Col | Coluna que apresenta os valores das células na tabela dinâmica. |

**Tópico principal:** [Componentes do relatório: Tabelas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
