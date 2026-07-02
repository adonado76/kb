---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Salvar comportamento"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Componentes do relatório: Tabelas editáveis nos relatórios"
source_path: "studio/new-uc/reference/report-studio-reference/save-behavior.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Salvar comportamento

As tabelas editáveis utilizam um processo de salvamento em duas etapas: salvamento local (persistência das alterações na tabela editável) e publicação (atualização da tabela de transformação associada).

**Salvar processo**

Quando os usuários fazem alterações:

1. As alterações são rastreadas no lado do cliente até serem explicitamente salvas
2. Clique em “Salvar” na parte inferior da tabela para salvar as alterações
3. As alterações salvas atualizam a tabela editável, mas ainda não o pipeline de transformação
4. A opção “Mostrar alterações” exibe todas as modificações pendentes

**Processo de publicação**

Para transferir os dados salvos para o pipeline de transformação:

1. Clique em “Publicar” na parte inferior da tabela
2. Confirme a ação de publicação na caixa de diálogo de aviso
3. Digite uma descrição e clique em “Check-in”
4. A tabela de transformação associada é atualizada com os novos dados

A publicação sempre sobrescreve todo o conjunto de dados da tabela editável na tabela de transformação associada.

**Pré-requisitos:** *A publicação manual requer acesso de desenvolvedor e acesso ao ambiente de teste, mas não requer acesso ao TBM Studio nem acesso de administrador.*

**Tratamento de erros ao salvar**

Quando o salvamento ou a publicação falham:

- **Erros de validação:** dados inválidos impedem a publicação; corrija os erros e tente novamente
- **Erros de conexão:** tente novamente a operação; as alterações permanecem no estado local
- **Conflitos de edição simultânea:** consulte a seção Controle de concorrência abaixo

**Controle de concorrência**

As tabelas editáveis aplicam bloqueio no nível das células para evitar conflitos:

- Quando um usuário começa a editar uma célula, essa célula fica bloqueada para os outros usuários
- O bloqueio permanece até que o usuário salve ou cancele a edição
- Outros usuários podem editar diferentes células na mesma linha simultaneamente
- Se todas as células nas linhas filtradas estiverem bloqueadas, as opções “Adicionar linha”, “Excluir linha” e “Duplicar linha” ficam desativadas

**Tópico principal:** [Componentes de relatórios: Tabelas editáveis em relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
