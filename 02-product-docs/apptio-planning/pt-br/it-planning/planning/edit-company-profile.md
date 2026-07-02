---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Configurações do perfil da empresa"
breadcrumb:
  - "Planning"
  - "Configuração e administração"
source_path: "it-planning/planning/edit-company-profile.html"
images:
  - "resources/images/studio_images/studioimages/icons/setting-icon.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurações do perfil da empresa

O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.

Observação: as funções de administrador ou responsável pelo processo orçamentário são necessárias para gerenciar as configurações do perfil da empresa.

## Como acessar o perfil da empresa

1. Selecione o botão **Configurações** (![img](../../../../../03-media/apptio-planning/resources/images/studio_images/studioimages/icons/setting-icon.jpg)) no canto superior direito e escolha **Perfil da empresa**.
2. Insira ou edite as informações conforme necessário.
3. Selecione **Save and Exit (Salvar e sair) para** aplicar as alterações.

## Configuração Geral

|  |  |  |
| --- | --- | --- |
| **Seção** | **Funcionalidade** | **Descrição** |
| Moeda | Moeda padrão | Define a moeda principal utilizada em todos os planos. Todos os valores monetários são padronizados para essa moeda, a menos que a opção de múltiplas moedas esteja ativada. |
| Moeda | Habilitar várias moedas | Permite que os usuários planejem em várias moedas. As regras de conversão de moeda aplicam-se quando ativadas. |
| Moeda | Exibir códigos ISO de moedas em vez de símbolos de moedas. | Substitui símbolos monetários (por exemplo, $, £) por códigos ISO (por exemplo, USD, GBP). |
| Formato numérico | Ativar precisão numérica decimal | Controle o número de casas decimais exibidas nos campos numéricos dos planos. |
| Formato numérico | Casas decimais | Especifica o número de casas decimais (por exemplo, 1–8) que serão utilizadas quando a precisão decimal estiver ativada. |
| Acesso e permissões | Ativar permissão de visualização | Restringe a visibilidade do Departamento com base nas permissões do usuário. Os usuários só veem os objetos de custo aos quais têm autorização de acesso. |
| Acesso e permissões | Ativar a nova experiência da página Despesas (Beta) | Ativa a página Despesas redesenhada, oferecendo melhor desempenho, filtragem e navegação. |
| Acesso e permissões | Habilitar permissões de objeto de custo no nível do plano | Ativa a página Permissões do usuário no nível do plano individual para gerenciar permissões por plano. |
| Fluxos de trabalho de aprovação e notificações | Fluxo de trabalho de aprovação | Define como as submissões de planos passam pelo processo de aprovação.    Escolha entre aprovação multinível (aprovedores sequenciais) ou aprovação hierárquica (estrutura organizacional de relatórios).    Para aprovações hierárquicas, opcionalmente, escolha desativar os envios do departamento do grupo. |
| Fluxos de trabalho de aprovação e notificações | Enviar notificações por e-mail para eventos do processo de planejamento | Envia alertas por e-mail quando os planos são enviados, aprovados ou devolvidos. |
| Análise de variação | Ativar análise de variação | Ativa a Análise de Variação, permitindo que os usuários identifiquem os fatores de variação e adicionem comentários. |
| Previsão | Resumir dados reais | Seleciona os atributos usados para acumular e resumir os dados reais das transações para previsão. |
| Data Management | Habilitar código externo | Permite armazenar identificadores de sistema externos para itens de linha do plano. |
| Data Management | Desativar restrições de atualização de dados de referência | Permite atualizar os valores dos dados de referência, mesmo quando as alterações podem excluir dados do plano existentes. O sistema gera um backup antes de aplicar a atualização. |
| Data Management | Habilitar integração Data Management automatizada | Permite a importação e sincronização de dados através do ADM. |
| Atualizações e manutenção | Dia da Atualização | Especifica o dia em que seu ambiente recebe atualizações do produto. |
| Mostrar intervalos de datas | Exibir intervalo de datas para colunas de período | Exibe a data de início e a data de término das colunas de período na tabela Despesas. As datas são formatadas de acordo com a configuração regional do usuário. Observação – Disponível apenas em Despesas > Nova visualização |
| Configurações de distribuição de dados para outras despesas | Definir o intervalo de dias do calendário como padrão | Quando ativada, os valores inseridos nas colunas **trimestrais** ou **anuais** são distribuídos automaticamente pelos meses com base no número de dias do calendário de cada mês.  Os usuários podem alterar essa configuração padrão no nível da tabela “Despesas” e selecionar a opção **“Distribuição uniforme” ou** **“Distribuição por dias do calendário”** |

## Planejamento de mão de obra

|  |  |  |
| --- | --- | --- |
| **Seção** | **Funcionalidade** | **Descrição** |
| Planejamento da força de trabalho | Número de funcionários | Permite o planejamento do quadro de funcionários, possibilitando aos usuários planejar os níveis de pessoal, cargos e custos associados na guia “Trabalho”. |
| Planejamento da força de trabalho | Método de resumo do número de funcionários | Determina como vários registros de mão de obra são consolidados (por exemplo, calculando a média ou selecionando o valor do período inicial ou final). |
| Planejamento da força de trabalho | Data padrão de início do trabalho | Define uma data de início padrão para novas entradas de mão de obra. |
| Planejamento da força de trabalho | Desativar aviso de compensação base | Desativa os avisos do sistema acionados quando os valores de compensação base estão em branco. |
| Ajuste de remuneração | Ajuste da remuneração variável | Permite modelar ajustes de remuneração variável. |
| Ajuste de remuneração | Ciclos de ajuste | Define a frequência e o tempo padrão para ajustes de compensação. Essas configurações podem ser substituídas no nível do plano. |
| Resumo do trabalho | Resumo do trabalho | Selecione as dimensões utilizadas para agregar itens financeiros gerados a partir da guia Trabalho quando exibidos na guia Resumo. |

## Planejamento de contratos

|  |  |  |
| --- | --- | --- |
| **Seção** | **Funcionalidade** | **Descrição** |
| Planejamento de contratos | Contratos | Permite o planejamento em nível de contrato, possibilitando aos usuários modelar contratos novos e existentes na guia Contratos. |
| Planejamento de contratos | Contrato de atualização automática total | Recalcula automaticamente o total do contrato quando os valores periódicos são alterados, garantindo que o valor do contrato reflita sempre a soma dos pagamentos programados. |
| Planejamento de contratos | Incluir Imposto sobre o Valor Agregado (IVA) | Permite que o IVA seja aplicado aos pagamentos do contrato. Quando ativado, o IVA é calculado com base na taxa de imposto definida. |

## Planejamento de ativos

|  |  |  |
| --- | --- | --- |
| **Seção** | **Funcionalidade** | **Descrição** |
| Planejamento de ativos | Habilitar o planejamento de ativos | Habilita o nível de ativos, permitindo que os usuários modelem ativos de capital e calculem a depreciação e as despesas de capital na guia Ativos. |

## Planejamento de Investimentos

|  |  |  |
| --- | --- | --- |
| **Seção** | **Funcionalidade** | **Descrição** |
| Planejamento do projeto | Habilite o planejamento integrado de investimentos | Permite o planejamento baseado em projetos, possibilitando aos usuários definir investimentos e vincular despesas a projetos. |
| Planejamento das atividades laborais | Habilitar atividade de trabalho | Permite que os usuários aloquem esforço de mão de obra (horas ou FTE) para projetos e gerem finanças de cobrança cruzada com base nos tipos de atividade na guia Atividade de mão de obra. |
| Planejamento das atividades laborais | Alocação de mão de obra | Permite a configuração de regras de sobrealocação e subalocação de recursos de mão de obra. Quando ativado, defina limites para quando um recurso é alocado acima ou abaixo de sua capacidade disponível. |
