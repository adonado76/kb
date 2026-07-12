---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tipos de permissão"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Report Studio"
  - "Permissões do relatório"
source_path: "studio/new-uc/reference/report-studio-reference/permission-typs.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tipos de permissão

**Visualizar permissões**

As permissões de visualização determinam quais funções podem ver um relatório ao navegar pelo Explorador de Projetos ou pelas Coleções de Relatórios.

**Configurando permissões de visualização:**

1. Confira o relatório
2. Na guia Relatório, no grupo Avançado, clique em Permissões
3. Selecione as funções que devem ter acesso para visualizar o relatório
4. Escolha uma das seguintes opções:

**Todos** : Todos os usuários com acesso ao projeto podem visualizar o relatório

**Funções selecionadas** : Somente os usuários atribuídos a funções específicas podem visualizar o relatório

**Recursos do visualizador:**

- Acesse e visualize o relatório
- Use segmentadores e filtros para explorar os dados
- Exportar dados do relatório (se as permissões de exportação permitirem)
- Imprimir relatórios ou gerar PDFs
- Inscreva-se para receber notificações por e-mail (se configurado)

**Restrições de visualização:**

Os usuários com funções de apenas visualização não podem:

- Verificar ou alterar a configuração do relatório
- Alterar as configurações ou o layout do componente
- Modificar permissões do relatório
- Criar tabelas ou gráficos personalizados (a menos que tenha sido designado para a função de Analista)

**Editar permissões**

As permissões de edição são normalmente controladas por meio de funções definidas no nível do projeto, e não por configurações individuais dos relatórios. Os usuários com permissão para editar relatórios devem ter:

- Uma função que inclui permissões para criação de conteúdo
- A possibilidade de fazer o check-out de documentos no projeto

**Recursos do editor:**

1. Verificar e modificar o layout do relatório
2. Adicionar, remover ou configurar componentes de relatório
3. Modificar configurações de tabelas e gráficos
4. Alterar as propriedades e configurações do relatório
5. Salvar e confirmar as alterações

**Permissão para editar relatórios pessoais**

Uma permissão específica chamada “Editar relatórios pessoais” permite que os usuários criem relatórios visíveis apenas para eles mesmos. Esta permissão:

- É atribuído à função de Analista por padrão
- Pode ser atribuído a qualquer função personalizada
- Permite a criação de relatórios pessoais sem afetar outros usuários
- Cria relatórios que não aparecem nas coleções de outros usuários

**Permissões de administrador**

Os recursos de administração de relatórios estão vinculados à função de administrador (ou a funções personalizadas com permissões equivalentes). Os administradores podem:

- Configurar permissões no nível do relatório
- Gerenciar membros da coleção de relatórios
- Excluir relatórios personalizados (os relatórios padrão não podem ser excluídos)
- Desativar relatórios para impedir o cálculo
- Ocultar relatórios das coleções de relatórios
- Gerenciar assinaturas de e-mail de outros usuários
- Configurar a visibilidade dos componentes por função

**Medidas administrativas disponíveis:**

|  |  |  |
| --- | --- | --- |
| **Ação** | **Local** | **Notas** |
| Definir permissões de relatório | Guia Relatório → Permissões | É necessário finalizar a compra |
| Adicionar à coleção | Guia Relatório → Atribuir à coleção | É necessário finalizar a compra |
| Excluir o relatório | Guia "Página inicial" → Excluir | Apenas relatórios personalizados |
| Desativar relatório | Guia Relatório → Caixa de seleção “Limpar ativo” | Impede o cálculo |
| Ocultar da coleção | Guia "Projeto" → Coleções de relatórios | Alternar a visibilidade |

**Permissões de execução (assinaturas por e-mail)**

A execução de relatórios por meio de assinaturas de e-mail programadas requer permissões específicas:

|  |  |
| --- | --- |
| **Permissão** | **Recurso** |
| **EmailSubscriptionsCreate** | Criar assinaturas de e-mail para si mesmo e para outras pessoas |
| **EmailSubscriptionsFilteredCreate** | Criar assinaturas com parâmetros de filtro |

**Limitações da assinatura:**

- Os destinatários dos e-mails devem pertencer a domínios autorizados para o ambiente do cliente
- A segurança em nível de linha (RLS) não é compatível com assinaturas de e-mail
- Por padrão, apenas os administradores do TBM têm acesso à opção de assinatura por e-mail

**Tópico principal:** [Permissões de relatórios](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
