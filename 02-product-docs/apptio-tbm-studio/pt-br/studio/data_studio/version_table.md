---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Versão de uma tabela"
breadcrumb: []
source_path: "studio/data_studio/version_table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Versão de uma tabela

**Aplica-se a** : TBM Studio 12.0 e posterior

Pode haver ocasiões em que os dados em uma tabela sejam alterados. Por exemplo, as contas atribuídas aos departamentos podem ser alteradas no início de um novo ano fiscal. Isso pode afetar os cálculos em um modelo. Você deseja preservar as atribuições anteriores para que os cálculos históricos permaneçam corretos, mas deseja que os novos dados sejam aplicados no novo ano fiscal. Para preservar os dados antigos e dar suporte à inserção dos novos dados, versione a tabela.

As regras a seguir se aplicam às versões:

- Você deve verificar uma tabela para versioná-la.
- O tempo deve ser configurado para o projeto.
- Não é possível excluir uma versão se houver apenas uma.
- Você só pode excluir uma versão se a hora estiver definida como o primeiro período da versão e se houver uma versão anterior.
- Não é possível criar uma versão se a hora estiver definida como o primeiro período da versão.

Para criar uma versão de uma tabela, na guia **Home**, clique em **Create Version (Criar versão** ).

Para excluir uma versão, na guia **Home**, clique em **Remove Version (Remover versão** ).
