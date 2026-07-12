---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Visão geral do fluxo de dados"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura de dados"
source_path: "studio/new-uc/concepts-architecture/data-architecture/data-flow-overview.html"
images:
  - "resources/images/studio_images/3stage-pipeline.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Visão geral do fluxo de dados

O TBM Studio processa dados por meio de um fluxo de trabalho em três etapas. Cada etapa corresponde a um dos principais componentes da plataforma, e os dados circulam por elas em uma sequência bem definida.

## O fluxo de trabalho em três etapas

Em termos gerais, o fluxo de dados segue este caminho:

![Tubulação de três estágios](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/3stage-pipeline.png)

- **Data Studio** é onde os dados entram na plataforma. Você faz upload de arquivos, conecta-se a bancos de dados externos ou insere dados manualmente. Data Studio também limpa, transforma e prepara seus dados para modelagem.
- **O Model Studio** é onde ocorre a alocação de custos. Ele utiliza as tabelas preparadas em Data Studio e aplica regras de negócios para alocar custos de fontes (como lançamentos no razão geral) a destinos relevantes para o negócio (como aplicativos ou unidades de negócios).
- **O Report Studio** é onde você visualiza e analisa os resultados. Os relatórios utilizam os resultados dos modelos e apresentam informações por meio de tabelas, gráficos e painéis. Os dados também podem sair da plataforma por meio de tabelas publicadas e APIs.

## Pontos-chave da transformação

Os dados são transformados em vários pontos críticos à medida que percorrem o pipeline:

|  |  |  |
| --- | --- | --- |
| **Ponto de Transformação** | **O que acontece** | **Onde ocorre** |
| Ingestão de dados | Os arquivos externos são analisados, os tipos de coluna são detectados e os dados são importados para o TBM Studio | Data Studio |
| Pipeline de transformação | Os dados são limpos, combinados, filtrados, mapeados e enriquecidos por meio de uma série de etapas configuráveis | Data Studio |
| Particionamento por data | Os dados de vários meses são divididos em períodos individuais para uma análise centrada nos meses | Data Studio |
| Mapeamento do conjunto de dados mestre | Fontes heterogêneas (GL, Orçamento, Previsão) são mapeadas para um esquema canônico unificado | Data Studio |
| Alocação de custos | Os dados preparados são alocados das fontes de custo para os destinos por meio de regras baseadas em fatores determinantes | Estúdio de Modelagem |
| Cálculo do relatório | Os resultados do modelo são agregados, filtrados e formatados para apresentação | Report Studio |

## Dados armazenados vs. dados calculados

Uma distinção arquitetônica importante no TBM Studio é entre os dados armazenados de forma persistente e os dados calculados sob demanda.

- **Dados armazenados** : As tabelas brutas e transformadas em Data Studio contêm dados armazenados. Depois de enviar um arquivo ou salvar uma transformação, esses dados permanecem no banco de dados do projeto. As entradas editáveis da tabela também são dados armazenados.
- **Dados calculados** : as alocações do modelo e os resultados dos relatórios são calculados durante as operações de compilação (cálculos em ambiente de teste ou de produção). Esses resultados refletem o estado atual das suas transformações, regras do modelo e configurações de intervalo de tempo.

Nota:

**Implicações práticas**

Como os resultados do modelo são calculados em vez de armazenados estaticamente, a alteração de dados a montante (como o envio de um novo arquivo de contabilidade geral) não altera imediatamente seus relatórios. É necessário executar uma compilação para recalcular o modelo com os dados atualizados.
