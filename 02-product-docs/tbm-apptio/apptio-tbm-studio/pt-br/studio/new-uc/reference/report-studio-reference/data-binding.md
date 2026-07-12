---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Ligação de dados"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório - Componentes de entrada"
source_path: "studio/new-uc/reference/report-studio-reference/data-binding.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Ligação de dados

Os componentes de entrada vinculam-se às colunas editáveis da tabela, que armazenam os dados inseridos pelo usuário no banco de dados do projeto.

**Vinculação a colunas editáveis da tabela**

Todos os componentes de entrada são configurados na etapa “Configurar colunas” da tabela editável:

- Selecione a tabela editável no Explorador de Projetos
- Vá para Etapas > Configurar colunas
- Selecione ou adicione uma coluna para configurar
- Defina as propriedades da coluna (tipo, validação, valores possíveis, etc.)

**Comportamento de vinculação bidirecional**

As alterações feitas nos componentes de entrada do relatório são refletidas no sistema da seguinte forma:

- O usuário edita uma célula no relatório
- O valor é armazenado no lado do cliente (estado pendente)
- O usuário clica em “Salvar” para confirmar as alterações na tabela editável
- O usuário clica em “Publicar” para enviar os dados para a tabela de transformação associada
- Os cálculos de compilação ou de teste incorporam os valores atualizados

Importante: A ligação não é em tempo real. Os usuários devem salvar e publicar explicitamente as alterações para que elas tenham efeito no modelo de custos.

**Tópico principal:** [Componentes do relatório - Componentes de entrada](../../../../studio/new-uc/reference/report-studio-reference/report-component-input-components.html)
