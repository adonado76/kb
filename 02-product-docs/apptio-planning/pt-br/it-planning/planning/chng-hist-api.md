---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "API de histórico de alterações"
breadcrumb:
  - "Planning"
  - "APIs"
  - "Visão geral do planejamento de APIs REST"
source_path: "it-planning/planning/chng-hist-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# API de histórico de alterações

**As APIs** de histórico de alterações permitem exportar dados do log de eventos que registram as alterações realizadas no Apptio Planning.Change. Os dados do histórico são exportados como um arquivo CSV e podem ser usados para auditar as modificações de um plano específico, incluindo **quais alterações foram feitas**, **quem as fez** e **quando ocorreram**.

## POST /at/api/v1/planning/export

**Descrição**

O histórico de alterações das exportações é registrado em um arquivo. CSV com base nos filtros selecionados, como intervalo de datas, nome de usuário, contêiner etc.

**Solicitação**

```
POST https://app.apptio.com/at/api/v1/planning/export
```

Observação: Certifique-se de que o endereço URL corresponda à sua região (por exemplo, app-eu.apptio.com, app-au.apptio.com )

**Cabeçalhos**

|  |  |  |
| --- | --- | --- |
| **Cabeçalho** | **Valor** | **Descrição** |
| apptio-opentoken | <open-token> | Token de autenticação gerado na etapa 2 dos pré-requisitos |
| apptio-ambiente-atual | <environment-id> | UUID do ambiente necessário obtido na etapa 3 dos pré-requisitos |

**Parâmetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Valores permitidos** | **Necessário** | **Descrição** |
| startDate | aaaa-MM-dd aaaa/MM/dd  yyyy.MM.dd  yyyy-MM-ddThh:mm:ssZ | TRUE | Data de início para exportar registros de eventos. Nota:  - Os valores que contêm apenas a data são convertidos para o início do dia (00:00:00 UTC). - Formatos ambíguos, como MM/dd/aaaa ou dd/MM/aaaa, são rejeitados para evitar erros nos dados. |
| endDate | aaaa-MM-dd/MM/dd yyyy.MM.dd  yyyy-MM-ddThh:mm:ssZ | TRUE | Data de início para exportar registros de eventos. Nota:  - Os valores que contêm apenas a data são convertidos para o início do dia (00:00:00 UTC). - Formatos ambíguos, como MM/dd/aaaa ou dd/MM/aaaa, são rejeitados para evitar erros nos dados. |
| eventTypes | Matriz de cadeias de caracteres | falso | Tipos de eventos para filtrar |
| userNames | Matriz de cadeias de caracteres | falso | Nomes de usuário para filtrar por |
| contêiner |  | falso | Valor do contêiner pelo qual filtrar |
| item |  | falso | Valor do item pelo qual filtrar |
| contexto |  | falso | Valor de contexto para filtrar por |
| áreas | Matriz de cadeias de caracteres | falso | Tipos de área para filtrar |
| itemTypes | Matriz de cadeias de caracteres | falso | Tipos de itens para filtrar |
| contextTypes | Matriz de cadeias de caracteres | falso | Tipos de contexto para filtrar |

**Resposta**

Um arquivo do tipo “ CSV ” para download que inclui dados do log de eventos para os filtros selecionados.

**Tópico principal:** [Visão geral do planejamento de APIs REST](../../it-planning/planning/plan-api.html "As APIs REST do Planning do Apptio oferecem acesso programático e seguro a planos, dados de planejamento, metadados e artefatos relacionados no Planning d Apptio. Essas APIs foram projetadas para oferecer suporte à automação e às integrações de sistemas em casos de uso relacionados a planejamento, previsão, análise, governança e troca de dados.")
