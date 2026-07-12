---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Requisitos relativos aos dados do motorista"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
  - "Motoristas"
source_path: "studio/new-uc/reference/model-studio-reference/driver-data-requirements.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Requisitos relativos aos dados do motorista

**Requisitos da coluna**

|  |  |  |
| --- | --- | --- |
| **Requisito** | **Descrição** | **Consequências caso não seja cumprido** |
| Tipo numérico | A coluna "Driver" deve conter valores numéricos | Driver ignorado; não há fluxo de valores |
| Valores diferentes de nulo | A coluna deve conter valores para as linhas | As linhas com valores nulos representam $0 |
| Dados do período | Devem existir dados para o período ativo | Não há valor de driver para esse período |
| Transformar o sucesso | A transformação da tabela deve ser concluída | Cálculos do modelo bloqueados |

Aviso: Se uma coluna numérica contiver pelo menos um valor não numérico, os drivers que fazem referência a essa coluna podem falhar sem exibir nenhuma mensagem de erro. Verifique sempre os tipos de dados em Data Studio.

**Tópico principal:** [Motoristas](../../../../studio/new-uc/reference/model-studio-reference/drivers.html)
