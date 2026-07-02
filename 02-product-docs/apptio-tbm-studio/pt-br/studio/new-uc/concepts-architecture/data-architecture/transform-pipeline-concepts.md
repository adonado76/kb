---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Conceitos de pipeline de transformação"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura de dados"
source_path: "studio/new-uc/concepts-architecture/data-architecture/transform-pipeline-concepts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conceitos de pipeline de transformação

O pipeline de transformação é o mecanismo de processamento que constitui o núcleo do Data Studio. Cada tabela possui um fluxo de processamento — uma sequência de etapas que transformam os dados, desde sua forma bruta inicial, em resultados limpos e estruturados, prontos para a modelagem de custos.

## Etapas da transformação

Uma etapa de transformação é uma única operação de processamento de dados dentro do pipeline. As etapas são executadas em sequência, de cima para baixo, e a saída de cada etapa passa a ser a entrada da etapa seguinte. Você pode adicionar, remover e reorganizar etapas para criar exatamente a lógica de processamento de que precisa.

Todo pipeline de tabela começa com duas etapas automáticas:

- **Fonte:** Define de onde vêm os dados (carregamento de arquivo, tabela existente, conector do DataLink ou tabela editável).
- **Tabela:** Exibe o resultado final de todo o pipeline. Esta etapa sempre aparece no final.

Para fontes de upload de arquivos, duas etapas adicionais são adicionadas automaticamente:

- **Carregar:** Permite selecionar e gerenciar o arquivo carregado.
- **Importação:** controla como o arquivo é analisado — detecção da linha de cabeçalho, linha inicial dos dados, detecção do tipo de coluna e configurações de delimitadores.

## Tipos de etapas de transformação disponíveis

Você pode adicionar as etapas a seguir ao pipeline de qualquer tabela para transformar os dados:

|  |  |  |
| --- | --- | --- |
| **Tipo de degrau** | **O que faz** | **Caso de uso comum** |
| Colunas do mapa | Adapta a saída da tabela para que corresponda a um esquema padrão (como a taxonomia ATUM ) e mapeia as colunas da fonte para o destino | Mapeamento de dados GL para categorias de centro de custo |
| Junção | Combina dados de duas ou mais tabelas em linhas únicas com base na correspondência de valores em colunas comuns | Enriquecer os dados de custos com informações de fornecedores provenientes de uma tabela separada |
| Anexo | Empilha as linhas de uma tabela abaixo das linhas de outra tabela | Combinação de arquivos mensais do Razão em um único conjunto de dados |
| Filtro | Remove linhas com base em condições aplicadas a uma ou mais colunas | Excluindo os centros de custo não relacionados à TI da análise |
| Fórmula | Cria novas colunas calculadas, altera os tipos de coluna ou substitui valores existentes | Calcular uma classificação derivada ou converter uma moeda |
| Grupo | Agrupa as linhas de acordo com os valores em uma ou mais colunas de texto, agregando os valores numéricos | Resumo das transações por centro de custo |
| Partição de data | Utiliza os valores de data no arquivo (em linhas ou colunas) para distribuir os dados por períodos de tempo | Dividir uma exportação do Razão com vários meses em períodos mensais individuais |
| Ocultar e renomear | Oculta colunas desnecessárias ou renomeia colunas para maior clareza | Remover IDs internos antes que os dados entrem no modelo |
| Atribuir linhas | Utiliza aprendizado de máquina e regras criadas pelo usuário para mapear dados para conceitos de taxonomia | Automatização da atribuição de grupos de custos por meio da classificação por aprendizado de máquina |
| Simplificar a hierarquia | Adiciona uma coluna para cada nível em uma hierarquia de dados | Ativação da filtragem baseada em filtros em estruturas organizacionais hierárquicas |

## Ordem de execução das etapas

As etapas de transformação são executadas estritamente de cima para baixo. A saída de uma etapa passa a ser a entrada da seguinte. Esse modelo sequencial significa que a ordem das etapas é importante:

- Uma etapa de filtragem colocada antes de uma junção reduzirá o número de linhas antes da operação de junção, o que pode melhorar o desempenho.
- Uma etapa de fórmula colocada após uma junção pode fazer referência a colunas de ambas as tabelas unidas.
- A etapa “Map Columns” geralmente aparece na parte final do pipeline, após a conclusão da limpeza e do enriquecimento.

Você pode arrastar as etapas para reordená-las no fluxo de trabalho, com exceção de certas etapas fixas (Fonte, Upload, Importação e Tabela), que devem permanecer em suas posições designadas.

Nota:

**Melhores práticas**

Estruture seu pipeline de forma que a filtragem e a redução de dados ocorram no início, as junções e o enriquecimento ocorram no meio e o mapeamento e a formatação final ocorram no final. Esse padrão melhora tanto a clareza quanto o desempenho.

## Linhagem de dados

A linhagem de dados refere-se à capacidade de rastrear um dado desde sua origem (o arquivo de origem carregado) passando por todas as transformações pelas quais ele passa, até a saída final do modelo e o relatório.

Compreender a linhagem de dados é importante por várias razões:

- **Precisão:** Quando um relatório apresenta um valor inesperado, a linha de origem ajuda a rastrear o problema até sua origem — seja nos dados de origem, em uma etapa de transformação ou em uma regra de alocação do modelo.
- **Auditabilidade:** As equipes de finanças e conformidade precisam verificar se as alocações de custos podem ser rastreadas até as transações de origem.
- **Análise de impacto:** antes de alterar uma transformação, você pode acompanhar a linhagem para entender quais objetos de modelo e relatórios serão afetados.

O TBM Studio rastreia a linhagem por meio do modelo de etapas sequenciais do pipeline. Como a saída de cada etapa alimenta a entrada da etapa seguinte, a cadeia de transformações é sempre explícita e verificável. O diagrama do Model Studio amplia ainda mais essa linha de descendência, mostrando como os dados fluem das tabelas de transformação, passando pelos objetos de alocação, até as unidades de negócios finais.

## Melhores práticas de design da Transform

- **Mantenha as transformações principais centralizadas:** crie um único conjunto de dados mestre (como um Mestre de Fontes de Custos) que unifique vários arquivos de origem. As transformações posteriores e os objetos de modelo devem fazer referência a esse arquivo mestre, em vez de arquivos de origem individuais.
- **Evite duplicar a lógica:** se várias tabelas precisarem da mesma transformação, crie uma transformação intermediária compartilhada em vez de repetir a lógica em cada pipeline.
- **Valide os tipos de coluna logo no início:** a definição incorreta do tipo de coluna (por exemplo, um campo numérico detectado como "Rótulo") causa erros que se propagam para as etapas posteriores. Confirme os tipos durante a etapa de importação.
- **Use nomes descritivos:** nomeie tabelas e etapas de forma clara para que os outros membros da equipe possam entender o pipeline sem precisar verificar a configuração de cada etapa.
- **Monitorar tabelas não utilizadas:** O TBM Studio pode identificar tabelas que não são referenciadas por nenhum relatório ou objeto de modelo. Revise e elimine periodicamente as tabelas não utilizadas para reduzir a complexidade.
