---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "APIs de análise de variância"
breadcrumb:
  - "Planning"
  - "APIs"
  - "Visão geral do planejamento de APIs REST"
source_path: "it-planning/planning/variance-analysis-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# APIs de análise de variância

**As APIs de análise de** variação permitem a exportação programática de dados de análise de variação para um plano específico.

As exportações são geradas como arquivos do tipo ` CSV ` e suportam parâmetros opcionais para controlar a formatação, a filtragem e a estrutura de saída, tornando os dados adequados para ferramentas de análise e visualização posteriores.

## POST /planning/api/v1/plans/<planId>/varianceanalysis/export

**Descrição**

Exporta os dados da análise de variação para um plano específico. A exportação é gerada como um arquivo do tipo ` CSV `, com base nos parâmetros fornecidos.

**Solicitação**

```
POST https://app.apptio.com/planning/api/v1/plans/<planId>/varianceanalysis/export>
```

Observação: Certifique-se de que o endereço URL corresponda à sua região (por exemplo, app-eu.apptio.com, app-au.apptio.com ). Use a API GET de planos para obter o ID do plano a ser exportado.

**Parâmetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Valores permitidos** | **Necessário** | **Descrição** |
| departmentCode | <code> ou em branco | falso | O código do departamento para o qual os dados da análise de variação devem ser exportados. Padrão: Deixe em branco para exportar os dados para todos os departamentos. |
| basePercentage | ONE CEM | falso | Formato no qual a porcentagem deve ser exibida. Padrão: UM |
| characterEncoding | UTF\_8 SHIFT\_JIS | falso | Codificação do arquivo de entrada Padrão: UTF\_8 |
| columnDelimiter | COMMA ponto e vírgula  TAB | falso | CSV delimitador Padrão: VÍRGULA |
| dateFormat | *Formatos de data compatíveis:* *aaaa-MM-dd*  *aaaa/MM/dd*  *yyyy.MM.dd*  *dd-mm-aa*  *dd/mm/aa*  *yy.MM.dd*  *dd-m-a*  *dd/M/a*  *yy.M.d*  *mm-dd-aaaa*  *mm/dd/aaaa*  *MM.dd.yyyy*  *dd-mm-aa*  *dd/MM/aa*  *MM.dd.yy*  *m-d-aaaa*  *M/d/aaaa*  *M.d.yyyy*  *dd-mm-aa*  *M/d/aa*  *M.d.yy*  *dd-MM-aaaa*  *dd/MM/aaaa*  *dd.MM.yyyy*  *dd-MM-aa*  *dd/MM/aa*  *dd.MM.yy*  *d-M-aa*  *d/M/aa*  *d.M.yy*  *d-M-aaaa*  *d/M/aaaa*  *d.M.yyyy* | falso | Formato dos campos de data no arquivo de importação. Padrão: aaaa-MM-dd |
| decimalPrecision | ZERO ONE  TWO  THREE  FOUR  Cinco  SEIS  SETE  OITO | falso | Número de casas decimais aplicado aos valores numéricos Padrão: OITO |
| decimalSymbol | PERÍODO COMMA | falso | Separador decimal Padrão: PERIOD |

**Resposta**

Um arquivo do tipo “ CSV ” para download contendo os detalhes da análise de variação do plano selecionado.

## Erros

|  |  |
| --- | --- |
| **Código** | **Significado** |
| 400 | Solicitação inválida |
| 403 | Desautorizado |

**Tópico principal:** [Visão geral do planejamento de APIs REST](../../it-planning/planning/plan-api.html "As APIs REST do Planning do Apptio oferecem acesso programático e seguro a planos, dados de planejamento, metadados e artefatos relacionados no Planning d Apptio. Essas APIs foram projetadas para oferecer suporte à automação e às integrações de sistemas em casos de uso relacionados a planejamento, previsão, análise, governança e troca de dados.")
