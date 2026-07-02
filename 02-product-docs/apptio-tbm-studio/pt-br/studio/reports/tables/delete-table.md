---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Excluir uma tabela editável"
breadcrumb: []
source_path: "studio/reports/tables/delete-table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Excluir uma tabela editável

1. Confira a tabela editável.
2. Na guia **Início**, no grupo **Documento**, clique em **Excluir**.
3. Verifique a tabela editável.

Essas tabelas não podem ser recuperadas posteriormente por meio da reversão do registro de auditoria. Para avisar o usuário sobre essa consequência, é exibida uma mensagem de aviso, conforme mostrado.

![Confirmar exclusão](../../../resources/images/studio_images/r-notes/purge%20sql%202_582x354.png)

Você deve excluir todos os dependentes antes de excluir a tabela editável, pois nenhuma tabela de banco de dados de apoio estará disponível. Se um editável tiver dependentes (exceto relatórios), o botão de confirmação de exclusão será desativado e uma mensagem de erro será exibida, conforme mostrado.

![Confirmar a opção Excluir](../../../resources/images/studio_images/r-notes/purge%20sql%201_576x404.png)
