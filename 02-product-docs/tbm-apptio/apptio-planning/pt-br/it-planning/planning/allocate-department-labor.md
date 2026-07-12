---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Alocar mão de obra do departamento"
breadcrumb: []
source_path: "it-planning/planning/allocate-department-labor.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Alocar mão de obra do departamento

## Antes de começar

Antes de começar, certifique-se de ativar os recursos de planejamento de mão de obra. Consulte [Editar o perfil da empresa](edit-company-profile.dita).

## Sobre esta tarefa

As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

Depois que os dados de referência de mão de obra forem configurados, você poderá disponibilizar mão de obra para o trabalho por meio de pools e alocações de recursos de mão de obra. Para obter mais informações, consulte [Gerenciar dados de referência de configuração de mão de obra](manage-labor-configuration.dita). Os proprietários de departamentos podem alocar para um projeto, serviço ou pool de mão de obra. Essas alocações departamentais também aparecem nas tabelas de alocação de mão de obra de seus projetos e serviços. As alocações de mão de obra também aparecem como cobranças na página Ledger do departamento para usuários licenciados de Project Financial Planning ou Service Demand Planning.

## Procedimento

- **Inserir dados de alocação de mão de obra**

  Trabalhe com detalhes de trabalho planejado na guia Trabalho, página Planejado.

  1. Nos menus Plano, no canto superior direito, selecione um Plano, uma categoria de Objeto de custo e um objeto de custo ou grupo de objetos de custo.

     [Saiba mais sobre como navegar no Planning](navigate-apptio-planning.html#Toolbar).

     Observação: os proprietários de centros de custo só podem editar os centros de custo atribuídos a eles. Para obter mais informações, consulte [os dados de referência Gerenciar permissões de objetos de custo](manage-cost-object.html).
  2. Navegue até Planning >Expenses (Despesas).
  3. Selecione a guia Trabalho.
  4. Selecione Existente para planejar ajustes de remuneração de mão de obra para a mão de obra atual.
  5. Selecione Planejado para planejar ajustes de remuneração do trabalho para o trabalho planejado.
  6. Selecione Editar alocações na coluna Alocações. A tabela de alocação de recursos é exibida e inclui as seguintes colunas:
     - Tipo de objeto de custo - O grupo de objetos de custo a ser atribuído ao recurso.
     - Para objeto de custo - O objeto de custo específico a ser atribuído ao recurso.
     - Para a conta - A conta que recebe o dinheiro pelo serviço.
     - Da conta - A conta que está retirando o dinheiro para pagar pelo serviço.
     - Quantidade - Os períodos (meses, trimestres e anos) de tempo em que uma porcentagem do recurso é alocada ao objeto de custo.
- **Visualizar dados de alocação de mão de obra**

  Quando as alocações são inseridas, uma opção de Alocações aparece ao lado dos links Planejado e Existente na guia Trabalho. Clique em Allocations (Alocações ) para visualizar os detalhes em uma tabela somente de leitura.

  Você pode visualizar as alocações das seguintes maneiras:

  - Um valor percentual.
  - Um valor equivalente a tempo integral (FTE).
  - Uma unidade prefigurada de medida de mão de obra, conforme definido no Perfil da Empresa. Para obter mais informações, consulte [Editar o perfil da empresa](edit-company-profile.html).
