---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurar permissões de relatórios"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar relatórios"
  - "Personalização de relatórios"
source_path: "studio/new-uc/howtoguides/create-reports/config-rep-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar permissões de relatórios

**Objetivo:** Controlar quais funções de usuário podem visualizar relatórios e componentes de relatórios específicos, garantindo o acesso adequado a dados confidenciais.

**Quando usar:** Use as permissões de relatório quando quiser:

- Restringir relatórios a departamentos ou funções específicos
- Exibir diferentes componentes do relatório para diferentes funções de usuário
- Criar visualizações de dados confidenciais exclusivas para executivos
- Garantir o cumprimento das políticas de acesso aos dados

**Pré-requisitos:**

- Função de administrador (para permissões no nível do relatório e permissões de coleta)
- Função de usuário avançado (para visibilidade no nível do componente)
- Compreensão das funções e dos requisitos de acesso da sua organização
- Conhecimento sobre gerenciamento de funções de usuário (consulte a Seção 3.4.2 )

**Tempo estimado:** 5 a 10 minutos por relatório; pode variar em caso de configurações complexas de visibilidade de componentes

## Entendendo as permissões dos relatórios

O TBM Studio oferece vários níveis de controle de acesso para relatórios:

1. **Permissões no nível do relatório:** controle quais funções podem acessar um relatório inteiro
2. **Permissões no nível da coleção:** controle quais funções podem acessar todos os relatórios de uma coleção
3. **Visibilidade por componente:** mostrar ou ocultar componentes específicos com base na função do usuário
4. **Segurança no nível da linha (RLS):** Controle quais linhas de dados os usuários visualizam (abordado na Seção 3.4.2 )

Essas camadas funcionam em conjunto — o usuário precisa ter permissão em cada camada aplicável para visualizar o conteúdo.

## Opções de permissão no nível do relatório

Ao criar ou editar um relatório, você define quem pode visualizá-lo:

|  |  |
| --- | --- |
| **Opção** | **Descrição** |
| Todos | Todos os usuários com acesso ao projeto podem visualizar o relatório |
| Funções selecionadas | Somente usuários com funções específicas podem visualizar o relatório |
| Pessoal (visível apenas pelo criador) | Só você pode ver o relatório — útil para rascunhos e análises pessoais |

Observação: a permissão “Editar relatórios pessoais” (atribuída por padrão à função de Analista) permite que os usuários criem relatórios que somente eles podem visualizar.

## Passo a passo: definir permissões ao criar um relatório

1. Na guia **Início**, clique em **Novo > Relatório**.
2. Insira o nome e a descrição do relatório.
3. Na seção **“Visível por”**, selecione a opção de permissão: **Todos** (deixe como padrão) ou **Funções selecionadas** (marque as funções que devem ter acesso a este relatório).
4. Preencha as opções restantes e gere o relatório.

**Passo a passo: alterar permissões em um relatório existente**

1. Selecione o relatório que você deseja modificar.
2. Na guia **Relatório** (ou guia **Projeto** ), no grupo **Avançado**, clique em **Permissões**.
3. Na caixa de diálogo de permissões, selecione **“Todos”** para disponibilizar o relatório a todos os usuários ou selecione **“Funções selecionadas”** e marque as funções específicas para restringir o acesso.
4. Clique em **OK** para salvar.
5. Salve o relatório para que as alterações entrem em vigor.

## Passo a passo: definir a visibilidade dos componentes por função

Você pode mostrar ou ocultar componentes individuais do relatório com base na função do usuário — o que é útil para criar um único relatório com diferentes visualizações para públicos distintos:

1. Dê uma olhada no relatório.
2. Selecione o componente (tabela, gráfico, caixa de grupo, etc.) que você deseja controlar.
3. Na guia **Relatório**, no grupo **Avançado**, clique em **Visibilidade**.
4. Na caixa de diálogo **Visibilidade do componente do relatório**, configure as opções de visibilidade:
   - **O componente contém dados:** ocultar se o componente não tiver dados
   - **A função atual do usuário é:** Marque as funções específicas que devem ter acesso a este componente
   - **O texto dinâmico resulta em "oculto":** use texto dinâmico para controlar a visibilidade programaticamente
5. Clique em **OK**.
6. Repita o procedimento para os demais componentes, conforme necessário, e verifique no relatório.

## Estratégias de permissão para relatórios

**Estratégia 1: Permissões baseadas em coleções**

- Crie coleções por público-alvo (Executivos, Finanças, Operações de TI)
- Definir permissões no nível da coleção
- Adicionar relatórios às coleções correspondentes

**Estratégia 2: Permissões baseadas em relatórios**

- Organize os relatórios por função em coleções
- Defina permissões específicas para cada relatório
- Útil quando a composição da coleção não corresponde às necessidades de acesso

**Estratégia 3: Visibilidade baseada em componentes**

- Crie relatórios completos com todo o conteúdo relevante
- Use as configurações de visibilidade para exibir os componentes adequados à função
- Reduz o número de relatórios a serem mantidos

## Armadilhas comuns

- **Esquecendo as permissões de coleção:** um usuário pode ter permissão para acessar relatórios, mas ainda assim ser impedido por restrições de coleção.
- **Regras de visibilidade excessivamente complexas:** um número excessivo de regras de visibilidade baseadas em funções torna-se difícil de manter. Considere elaborar relatórios distintos para públicos significativamente diferentes.
- **Não testar com usuários reais:** verifique sempre as permissões visualizando os relatórios na perspectiva de usuários com funções diferentes.
- **Ignorando a segurança no nível da linha:** as permissões de relatório controlam o acesso aos relatórios; a RLS controla o acesso aos dados dentro dos relatórios. Pode ser que ambos sejam necessários.

**Tópico principal:** [Personalização de relatórios](../../../../studio/new-uc/howtoguides/create-reports/report-cust.html)
