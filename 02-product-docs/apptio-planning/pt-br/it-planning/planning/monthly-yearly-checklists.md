---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Listas de verificação mensais e anuais para administrar o planejamento"
breadcrumb: []
source_path: "it-planning/planning/monthly-yearly-checklists.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Listas de verificação mensais e anuais para administrar o planejamento

aplica-se a: Planning administração. As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

Use esta lista de verificação como um guia para manter sua solução de planejamento.

Observação: esta lista de verificação não abrange todos os elementos operacionais para cada cenário possível. Seu objetivo é facilitar os procedimentos operacionais de uma solução configurada normalmente. Todos os itens da lista de verificação têm links para instruções detalhadas.

## Lista de verificação mensal

- [Importar e publicar dados reais](import-publish-actuals.html)
- [Criar um plano ou previsão](create-budget-plan.html) e notificar os proprietários de departamentos sobre o período de entrada
- [Integrar com transparência de custos](integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados.")

## Lista de verificação anual

- [Configure as definições de tempo do projeto](../../studio/admin/configure-project-time.html "Aplica-se a: TBM Studio 12.0 e posterior. As opções exibidas na caixa de diálogo Configure Project Time Settings dependem do tipo de calendário selecionado.") em Costing Standard.
- Atualize os dados de referência com as novas informações da organização. As dimensões incorporadas são gerenciadas por administradores ou proprietários de processos orçamentários. Muitas dimensões incorporadas têm dependências de outras dimensões (consulte [Dependências de atributos e dimensões de dados de referência](manage-reference-data.html) para obter informações).
  - Atualizar contas, centros de custo, departamentos, localização e fornecedores (consulte [Gerenciar dados de referência financeira](manage-financial-dimensions.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") ).
  - Atualize os pools de mão de obra externos e internos, as regras de alocação de mão de obra, as taxas de mão de obra e as funções (consulte [Gerenciar dados de referência de mão de obra](manage-labor-configuration.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") ).
  - Atualize os tipos de contrato e as taxas de IVA (consulte [Gerenciar dados de referência do contrato](manage-contract-configuration.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") ).
  - Atualize a classe do ativo (consulte [Gerenciar dados de referência da classe do ativo](manage-asset-configuration.html) ).
  - Atualizar permissões de objetos de custo (consulte [os dados de referência Gerenciar permissões de objetos de custo](manage-cost-object.html "As permissões de objetos de custo determinam quais usuários podem visualizar, editar, enviar ou aprovar planos em nível de departamento (objetos de custo). Cada departamento pode ter um ou mais usuários atribuídos com permissões de nível de edição e, para aprovações multinível, permissões de nível de aprovação.") )
  - Se estiver oferecendo suporte a várias moedas, atualize as taxas de moeda real e planejada (consulte [Gerenciar dados de referência das tabelas de taxas de conversão de moeda](manage-multi-currency.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") ).
  - Se [o site Project Financial Planning estiver ativado](pfp/gs-project-financial.html "◆ Aplica-se a: Planejamento com planejamento financeiro de projetos."), atualize o projeto e o grupo de projetos (consulte [Gerenciar dados de referência do projeto](pfp/manage-project-configuration.html) ).
- [Crie um plano ou previsão](create-budget-plan.html).
- [Insira os detalhes financeiros e ajuste os valores da linha de base](enter-financial-details.html).
- [Abra um plano ou uma previsão](open-plan-forecast.html "Após criar um plano ou previsão orçamentária, opcionalmente ajuste os valores de linha de base, defina as metas e abra o plano para que os proprietários do orçamento possam editar os itens de linha. Os proprietários de orçamento não podem ver um plano quando ele está no estado Novo. Quando você abre um plano, uma notificação por e-mail é enviada aos proprietários do orçamento e a todos os usuários que têm a permissão Edit & Submit associada aos objetos de custo desse plano.").
- Notificar os proprietários de departamento sobre um período de entrada de orçamento (data inicial e final).
- [Crie um plano de trabalho](create-labor-plan.html).
- [Revisar, aprovar ou devolver planos ou objetos de custo](review-approve-return.html).
- [Integrar com a transparência de custos](integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados.").

VEJA TAMBÉM : À medida que você atualiza os dados de referência, os artigos a seguir podem ser úteis:

- [Gerenciar dados de referência para planejamento](manage-itfmf-reference.html "aplica-se a: Planejamento")
- [Forçar um plano para usar dados de referência atualizados](force-plan-use.html)
