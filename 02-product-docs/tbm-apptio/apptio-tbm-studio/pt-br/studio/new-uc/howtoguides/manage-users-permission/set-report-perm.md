---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Definir permissões de relatórios por função"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Gerenciar usuários e permissões"
  - "Controle de acesso"
source_path: "studio/new-uc/howtoguides/manage-users-permission/set-report-perm.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Definir permissões de relatórios por função

|  |  |
| --- | --- |
| **Objetivo** | Controle quais funções de usuário podem visualizar e interagir com relatórios específicos |
| **Tempo estimado** | 10 a 15 minutos por relatório |
| **Pré-requisitos** | Função de administrador ou função personalizada com as permissões adequadas; funções configuradas no projeto |

## Quando utilizar este procedimento

Use as permissões de relatórios quando precisar restringir o acesso a relatórios inteiros ou coleções de relatórios a funções de usuário específicas. Essa é a primeira linha de controle de acesso: se um usuário não consegue visualizar um relatório, ele não consegue acessar nenhum dos dados nele contidos.

**Passos**

**Opção A: Definir permissões ao criar um relatório**

1. Acesse o **TBM Studio** e clique na guia **Início**.
2. Clique em **Novo** e, em seguida, selecione **Relatório**.
3. Digite um nome e uma descrição para o relatório.
4. Na seção “**Visível por** ”, selecione quais funções podem visualizar este relatório. As opções dependem das permissões da sua função.
5. Conclua a configuração restante do relatório e clique em **OK**.

**Opção B: Modificar permissões em um relatório existente**

1. No **Explorador** de Projetos, acesse **Relatórios** e localize o relatório.
2. Dê uma olhada no relatório.
3. Na guia **Projetos**, no grupo **Avançado**, clique em **Permissões**.
4. Na caixa de diálogo de permissões, marque ou desmarque funções para controlar a visibilidade do relatório.
5. Clique em **Aplicar** para salvar suas alterações.
6. Envie o relatório para aplicar as alterações no ambiente de teste.

**Opção C: Configurar a visibilidade dos componentes por função**

Em casos em que diferentes funções devem visualizar componentes diferentes dentro do mesmo relatório, utilize a visibilidade de componentes baseada em funções em vez de criar relatórios separados:

1. Confira o relatório e abra-o no designer de relatórios.
2. Crie um contêiner **de grupo** para os componentes que devem ser específicos de cada função.
3. Adicione ao grupo os componentes (tabelas, gráficos) que devem ficar visíveis para uma função específica.
4. Configure o grupo para que seja visível apenas para a função de destino.
5. Repita os passos 2 a 4 para cada função que precise de uma visualização diferente.
6. Sobreponha os grupos uns sobre os outros na área de relatórios.
7. Confira o relatório.

Observação: Se um usuário tiver várias funções com configurações de visibilidade de grupo diferentes, ele verá os componentes da função que estiver no topo da pilha de grupos.

## Resultados esperados

- Os usuários com funções autorizadas visualizam o relatório no Report Finder e podem acessá-lo
- Os usuários sem funções autorizadas não visualizam o relatório na lista
- A visibilidade dos componentes (se configurada) exibe conteúdo adequado à função em relatórios compartilhados

## Armadilhas comuns

- **Permissões antigas ( pre-12.7 ):** Em configurações mais antigas, a ativação de permissões baseadas em funções criava cópias separadas dos relatórios para cada função. O TBM Studio 12.7 + adota uma abordagem unificada. Se você tiver cópias de relatórios antigos, consulte “Migrar o controle de acesso aos relatórios” na seção 6.3.
- **Relatórios predefinidos:** não é possível excluir relatórios predefinidos. Em vez disso, use permissões para restringir o acesso.
- **Esquecer de fazer o check-in:** as alterações de permissão só entram em vigor depois que o relatório for submetido e o cálculo for concluído.

## Tarefas relacionadas

- [Criar e gerenciar coleções de relatórios](../create-reports/build-rc.html)
- [Configurar funções personalizadas](config-custom-roles.html)
- Desativar relatórios (Seção 6.3 )

**Tópico principal:** [Controle de acesso](../../../../studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html)
