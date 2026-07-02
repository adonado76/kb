---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Comportamento de entrada"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório - Componentes de entrada"
source_path: "studio/new-uc/reference/report-studio-reference/input-behavior.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Comportamento de entrada

**Bloqueio em nível de célula (controle de concorrência)**

O TBM Studio evita edições conflitantes por meio de bloqueios no nível das células:

- Quando o usuário A começa a editar uma célula, essa célula é bloqueada
- O usuário B vê a célula como bloqueada e não consegue editá-la
- O bloqueio permanece até que o usuário A salve ou cancele
- Evita atualizações parciais e colisões de dados

**Salvar fluxo de trabalho**

O TBM Studio utiliza um modelo de salvamento manual, e não de salvamento automático:

- Editar: O usuário altera os valores das células
- Salvar: o usuário clica em Salvar para confirmar as alterações na tabela editável
- Publicar: o usuário clica em “Publicar” para enviar os dados para a tabela de transformação

Importante: Ao salvar, as alterações são aplicadas à tabela editável. A publicação envia essas alterações para a tabela de transformação a jusante e aciona o recálculo.

**Tópico principal:** [Componentes do relatório - Componentes de entrada](../../../../studio/new-uc/reference/report-studio-reference/report-component-input-components.html)
