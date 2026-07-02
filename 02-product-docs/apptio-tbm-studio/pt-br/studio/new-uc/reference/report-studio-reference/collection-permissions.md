---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Permissões de coleta"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Coleções de relatórios"
source_path: "studio/new-uc/reference/report-studio-reference/collection-permissions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permissões de coleta

**Visão geral do modelo de permissões**

O TBM Studio oferece suporte a permissões tanto no nível da coleção quanto no nível de cada relatório. Entender como essas permissões interagem é essencial para proteger adequadamente seus relatórios.

|  |  |
| --- | --- |
| **Nível de permissão** | **Descrição** |
| Nível de coleção | Determina quais funções podem visualizar e acessar a coleção como um todo. Os usuários sem acesso a uma coleção não a verão na barra de navegação. |
| Nível do relatório | Determina quais funções podem visualizar relatórios específicos dentro de uma coleção. Um usuário pode ter acesso a uma coleção, mas não a todos os relatórios nela contidos. |
| Nível de componente | Controla a visibilidade de componentes específicos (tabelas, gráficos, grupos) dentro de um relatório com base na função do usuário. |

**Herança de permissões**

Quando um usuário tenta acessar um relatório em uma coleção, o TBM Studio avalia as permissões na seguinte ordem:

- **Acesso à coleção:** O usuário deve ter acesso à coleção para visualizá-la na navegação
- **Acesso ao relatório:** O usuário deve ter permissão para visualizar o relatório específico
- **Visibilidade dos componentes:** cada componente pode ser ocultado ou exibido de acordo com a função

As permissões no nível do relatório não são herdadas automaticamente das permissões no nível da coleção. Você deve configurar ambos se quiser restringir o acesso em vários níveis.

**Definir permissões de coleção**

As permissões de coleção são configuradas na caixa de diálogo “Gerenciar coleções de relatórios”. Os administradores podem definir quais funções têm acesso para visualizar relatórios em cada coleção.

Para obter informações detalhadas sobre como configurar permissões *de* relatórios, consulte a seção “Trabalhar com permissões de relatórios” na documentação do TBM Studio.

**Visibilidade dos componentes por função**

Em casos em que diferentes funções precisam visualizar diferentes componentes dentro do mesmo relatório, é possível usar grupos de relatórios com visibilidade baseada em funções. Isso permite criar um único relatório que exibe conteúdos diferentes para diferentes funções de usuário.

- Adicione um grupo de relatórios por função, contendo os componentes visíveis para essa função
- Configure cada grupo para que seja visível apenas a uma função
- Organize os grupos na área de relatórios de forma que a função do usuário determine quais grupos ele visualiza

Observação: Se um usuário tiver duas funções, cada uma com seu próprio grupo visível, ele verá os componentes da função cujo grupo estiver no topo da pilha.

**Tópico principal:** [Coleções de relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-collection.html)
