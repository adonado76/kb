---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Dados de referência de configuração de alocação"
breadcrumb: []
source_path: "it-planning/planning/manage-allocation-configuration.html"
images:
  - "resources/images/icons/3-dots.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Dados de referência de configuração de alocação

◆ Aplica-se a: aplicativos Apptio Planning com Project Financial Planning (consulte [Introdução ao módulo Project Financial Planning](pfp/gs-project-financial.html "◆ Aplica-se a: Planejamento com planejamento financeiro de projetos.")  ) ou Service Demand Planning (consulte [Introdução ao módulo Service Demand Planning](sdp/gs-service-demand.html)  )

As tarefas abaixo exigem que você licencie Project Financial Planning ou Service Demand Planning e, em seguida, edite o Company Profile para ativar Project Financial Planning ou Service Demand Planning. Consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning."). As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

Assista a este vídeo do site Apptio Education Services: [Configuração de dados de referência: Project
Financial Planning Dimensions (Dimensões](https://community.ibm.com/community/user/viewdocument/configuring-reference-data-labor-d?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Abre em uma nova guia ou janela)") ). DICA: Vá para 4:30 para ver informações sobre o tipo de conta de transferência.

As dimensões são as categorias de dados essenciais nos itens de linha do orçamento. Muitas dimensões incorporadas têm dependências de outras dimensões (consulte [Dependências de atributos e dimensões de dados de referência](manage-reference-data.html) para obter mais informações). Você pode importar dados de referência de dimensões de um arquivo.csv ou do site Costing Standard e exportar modelos de dados de referência de dimensões e dados de tabela (consulte [Gerenciar dimensões](manage-reference-data.html) ).

A dimensão Padrão da conta de transferência permite que o proprietário do projeto, o proprietário do serviço, o gerente de relacionamento comercial e o proprietário da unidade de negócios determinem a alocação correta de dinheiro para consumir ou apoiar vários projetos ou serviços. Esse recurso exige que Service Demand Planning ou Project Financial Planning esteja ativado. Consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.").

1. No menu de navegação, selecione Configuration (Configuração) > Reference Data (Dados de referência ) > Transfer Account Default (Transferir padrão de conta).
2. Selecione ![mais…](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) no canto superior direito da tabela, selecione Exportar > Exportar tudo.
3. Abra o arquivo.csv baixado e atualize os valores da tabela de dados conforme necessário:
   - Tipo de consumidor - um objeto de custo que consome os recursos de outro objeto de custo
   - Tipo de provedor - um objeto de custo que fornece os recursos para outro objeto de custo
   - Transferência na conta - A conta que recebe o pagamento (requer o código da conta)
   - Transfer Out Account (Conta de transferência ) - A conta usada para pagar (requer código de conta)
4. Agora, Configuration > Reference Data > Transfer Account Default e, em seguida, importe o arquivo.csv atualizado.

Ao inserir os dados do provedor e do consumidor, consulte esta tabela de combinações permitidas:

| Provedor | Consumidor |
| --- | --- |
| Pool de mão de obra externa | Projeto |
| Pool de mão de obra externa | Serviços |
| Pool de mão de obra interna | Projeto |
| Pool de mão de obra interna | Serviços |
| Serviços | Unidade de negócios |
| Serviços | Serviços |
| Serviços | Projeto |
| Serviços | Departamento |

Dica: você pode integrar essa dimensão com Costing Standard para importar dados de contas de transferência de Costing Standard.
