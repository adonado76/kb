---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar coleções de relatórios de compilação"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar relatórios"
  - "Personalização de relatórios"
source_path: "studio/new-uc/howtoguides/create-reports/build-rc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar coleções de relatórios de compilação

**Objetivo:** Criar e gerenciar coleções de relatórios que agrupem relatórios relacionados para facilitar a navegação e o controle de acesso.

**Quando usar:** Use coleções de relatórios quando quiser:

- Relatórios relacionados ao grupo (por exemplo, todos os relatórios financeiros mensais)
- Oferecer uma navegação intuitiva entre relatórios sobre temas semelhantes
- Controlar o acesso por função no nível da coleção
- Organizar relatórios por departamento, função ou período

**Pré-requisitos:**

- Função de administrador (somente administradores podem criar ou excluir coleções)
- Relatórios já criados que você deseja agrupar
- Compreensão de quais funções de usuário devem ter acesso a cada coleção

**Tempo estimado:** 10 a 15 minutos para criar uma coleção; 2 a 5 minutos por relatório para adicionar

## Entendendo as coleções de relatórios

Agrupe os relatórios relacionados para que os usuários possam navegar facilmente entre eles. Quando os usuários acessam um relatório em uma coleção, eles veem um navegador de coleção de relatórios na parte superior do relatório — uma barra horizontal que exibe todos os relatórios dessa coleção, permitindo uma navegação fácil com um único clique.

**Pontos principais:**

- Somente administradores podem criar e excluir coleções de relatórios
- Uma vez criadas, as coleções abrangem todo o projeto
- Qualquer usuário com as permissões adequadas pode adicionar ou remover relatórios de coleções existentes
- Um relatório pode pertencer a apenas uma coleção por vez
- Os administradores podem definir permissões baseadas em funções no nível da coleção
- Você pode ocultar relatórios em uma coleção sem excluí-los — o que é útil para relatórios que ainda não estão prontos

**Passo a passo: Criar uma coleção de relatórios**

1. Na guia **Projeto**, no grupo **Dados do projeto**, clique em **Coleções de relatórios**.
2. Na caixa de diálogo “**Gerenciar coleções de relatórios** ”, clique em “**Adicionar coleção** ”.
3. Aparece uma nova entrada chamada "Nova coleção de relatórios", que fica selecionada no campo " **Coleção selecionada** ".
4. Para renomear a coleção, clique na entrada na lista, depois clique no nome no campo “Coleção selecionada” e digite um novo nome (por exemplo, “Pacote Financeiro Mensal” ou “Painéis Executivos”).
5. Clique fora do campo de nome para salvar.

## Passo a passo: adicionar um relatório a uma coleção

1. No **Explorador** de Projetos, navegue até o relatório que deseja adicionar e selecione-o.
2. Na guia **Relatório**, no grupo **Agrupamento**, clique em **Atribuir à coleção**.
3. Na lista suspensa, selecione a coleção à qual deseja adicionar o relatório.

O relatório agora faz parte da coleção. Quando os usuários visualizarem o relatório, verão o navegador de coleções.

**Observação:** *um relatório só pode pertencer a uma coleção. Se você atribuí-lo a uma nova coleção, ele será removido da coleção anterior.*

## Passo a passo: Remover um relatório de uma coleção

**Método 1: A partir do relatório**

1. Acesse o relatório e dê uma olhada nele.
2. Na guia **Relatório**, no grupo **Agrupamento**, clique em **Atribuir à coleção**.
3. No menu, clique no X vermelho ao lado do nome da coleção.

**Método 2: A partir de “Gerenciar coleções de relatórios”**

1. Na guia **Projeto**, clique em **Coleções de relatórios**.
2. Selecione a coleção na lista **de coleções disponíveis**.
3. Encontre o relatório na lista à direita.
4. Clique no X vermelho à direita da linha do relatório.

## Passo a passo: ocultar ou exibir relatórios em uma coleção

Você pode querer ocultar temporariamente um relatório — por exemplo, um relatório padrão que ainda não configurou ou um relatório em desenvolvimento.

**Para ocultar um relatório:**

1. Na guia **Projeto**, no grupo **Dados do projeto**, clique em **Coleções de relatórios**.
2. Selecione a coleção que contém o relatório.
3. Encontre o relatório na lista à direita.
4. Desmarque a caixa de seleção **“Mostrar no navegador”** ao lado do nome do relatório.
5. Clique em **Fechar**.

**Para exibir um relatório oculto:** Siga os mesmos passos, mas marque a caixa de seleção “Mostrar no navegador”.

**Importante:** *Nunca exclua relatórios predefinidos de uma coleção. Em vez disso, oculte-os até que você esteja pronto para ativá-los.*

## Exemplo: Criação de um pacote de relatórios mensais

Um caso de uso comum é agrupar todos os relatórios que as equipes financeiras analisam mensalmente:

1. Crie uma coleção chamada "Pacote Financeiro Mensal".
2. Adicione estes relatórios à coleção: Resumo de custos por unidade de negócios, Análise de gastos com fornecedores, Variação entre orçamento e real, Discriminação de custos da IT Tower, Relatório detalhado de repasse de custos.
3. Organize os relatórios em ordem lógica (os usuários os verão na ordem apresentada na coleção).
4. Se o Relatório de Detalhes de Estornos ainda não estiver pronto, oculte-o desmarcando a opção “**Mostrar no navegador** ”.

Agora, quando os usuários da área financeira abrem qualquer um desses relatórios, eles veem o navegador de coleções e podem alternar facilmente entre todos os relatórios mensais.

## Armadilhas comuns

- **Esquecer os limites da coleção restringe a visibilidade:** se um relatório pertencer a uma coleção, os usuários que não tiverem acesso a essa coleção não verão o relatório — mesmo que tenham permissão para acessar o próprio relatório.
- **Exclusão de relatórios padrão:** nunca exclua relatórios padrão; em vez disso, oculte-os. A exclusão pode causar problemas na atualização.
- **Coleções desorganizadas:** um número excessivo de relatórios em uma coleção dificulta a navegação. Considere dividir coleções grandes por subtemas.

**Tópico principal:** [Personalização de relatórios](../../../../studio/new-uc/howtoguides/create-reports/report-cust.html)
