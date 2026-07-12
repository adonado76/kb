---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Melhores práticas: Taxas de remuneração do trabalho"
breadcrumb: []
source_path: "it-planning/planning/bp-handling-labor-compensation.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Melhores práticas: Taxas de remuneração do trabalho

As informações abaixo abordam considerações comuns para lidar com taxas de remuneração de mão de obra em aplicativos Apptio Planning . Essas informações são especialmente relevantes para os patrocinadores executivos e partes interessadas relacionadas antes que os detalhes da taxa de remuneração do trabalho sejam registrados nos aplicativos Apptio Planning .

## Estratégias para valores de taxas de remuneração de mão de obra

As taxas de remuneração do trabalho são registradas na tabela de dados de referência do trabalho. Para obter detalhes de implementação, consulte [Gerenciar dados de referência de trabalho](manage-labor-configuration.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor."). Antes de registrar as taxas de remuneração do trabalho, o site Apptio recomenda que sua organização adote uma abordagem padrão. Veja a seguir as estratégias comuns de taxa de remuneração de mão de obra a serem consideradas.

## Valores de ponto médio

Essa estratégia usa o meio da faixa salarial estabelecida ao vincular os salários à mão de obra. Por exemplo, se a faixa salarial fosse de US$ 56.000 a US$ 94.000, o ponto médio seria de US$ 75.000.

- Vantagem - Oculta as informações salariais da visualização e fornece um nível de dados para maior clareza.
- Desvantagem - O nível de informações nos relatórios não pode ser 100% preciso. Haveria um aumento nas variações, pois não haveria vínculo com os dados reais.

## Média

Os planos usam a média de todos os salários ao serem incluídos em um orçamento maior ou em um plano de previsão. Por exemplo, se você tiver 10 analistas, você usaria o salário médio desses 10 analistas.

- Advantage (Vantagem ) - Permite ocultar informações salariais, além de fornecer uma visão estratégica dos dados salariais.
- Desvantagem - Não permite uma abordagem mais granular para a visualização dos dados salariais. Haveria um aumento nas variações, pois não haveria vínculo com os dados reais.

## Taxa única

Uma taxa para todos os funcionários e salários reais são inseridos na guia Despesas pelos gerentes. Os gerentes são os únicos que podem vê-los se você ocultar a guia Trabalho dos administradores com uma função personalizada. Consulte [Restringir acesso a detalhes de salários trabalhistas](restrict-access-labor.html "As tarefas abaixo só podem ser executadas por usuários atribuídos à função Admin. Consulte Permissões e funções do Frontdoor."). Essa é a abordagem recomendada, pois fornece o máximo de precisão nos dados salariais e ainda oferece algum nível de proteção.

- Vantagem - Permite um planejamento preciso ao fazer orçamentos ou previsões com relação a informações salariais. Também permite a capacidade de detalhar os relatórios para obter uma visão mais granular dos dados salariais.
- Desvantagem - Os gerentes podem ver todas as informações salariais de seus departamentos. Além disso, esses dados são visíveis para o administrador do TBMA ou Apptio. Haveria um aumento nas variações, pois não haveria vínculo com os dados reais.

## Melhores práticas: Inserção de informações salariais por função, região/localização e tipo de funcionário (externo vs. interno)

- Vantagem - Abordagem mais precisa, menor variação e vinculação aos dados reais.
- Desvantagem - Todos os administradores podem ver as informações salariais. Além disso, qualquer pessoa com acesso a um centro de custo específico pode ver todos os salários desse centro de custo.

## Opções de segurança do trabalho

Esta seção descreve estratégias para proteger as informações de trabalho nos ambientes Apptio.

## Gerenciar permissões de objetos de custo

Muitas empresas definem permissões detalhadas de objetos de custo. Essas empresas fazem um esforço considerável para garantir que as permissões de cada usuário final sejam configuradas adequadamente de acordo com o nível de suas respectivas funções. Para saber mais, consulte [Acesso restrito a detalhes de salários trabalhistas](restrict-access-labor.html "As tarefas abaixo só podem ser executadas por usuários atribuídos à função Admin. Consulte Permissões e funções do Frontdoor.").

## Ocultar informações trabalhistas

Em seus respectivos ambientes Apptio, na guia Roles (Funções ), existe a opção de remover completamente a opção Labor (Trabalho) de usuários individuais.

## Rastreamento de mão de obra fora de Apptio

Algumas empresas optam por não rastrear informações trabalhistas em seus respectivos ambientes Apptio. Essas empresas utilizam outros sistemas para rastrear informações trabalhistas específicas e usam esses sistemas em conjunto com o site Apptio.

## Restringir o acesso de trabalho aos administradores

As informações sobre mão de obra podem ser ocultadas de todos, exceto dos administradores, que teriam que orçar toda a mão de obra. Consulte [Restringir acesso a detalhes de salários trabalhistas](restrict-access-labor.html "As tarefas abaixo só podem ser executadas por usuários atribuídos à função Admin. Consulte Permissões e funções do Frontdoor.").

## Permissões de Usuário

|  |  |  |
| --- | --- | --- |
| **Nome da permissão** | **Descrição** | **Funções padrão** |
| ITPPlanSettingsEdit | Permite que os usuários editem as configurações do plano. | Adicionado às funções de **Administrador** e **Proprietário do processo de orçamento** por padrão. |
| ITPPlanSettingsView | Permite que os usuários visualizem as Plan Settings (Configurações do plano). | Nenhum |
| ITPCompensationAdjustmentEdit | Permite que os usuários substituam os ajustes de remuneração padrão nas linhas de mão de obra para ciclos de remuneração definidos. | Adicionado às funções **Administrador**, **Proprietário do processo orçamentário** e **Proprietário do centro de custos** por padrão. |
| ITPCompensationAdjustmentAllPeriodsEdit | Permite que os usuários editem ajustes de remuneração em linhas de mão de obra para todos os períodos do plano, incluindo períodos fora dos ciclos de remuneração definidos. | Adicionado à função de administrador e proprietário do processo orçamentário por padrão. |

Para saber mais, consulte [Configuração de ajustes de remuneração de mão de obra](plan-labor-compensation.html "Os proprietários do processo orçamentário ou os usuários com permissões de proprietário de um objeto de custo podem contabilizar os ajustes planejados nas taxas de remuneração de mão de obra. Isso pode ser feito para mão de obra atual ou planejada. Você pode especificar uma alteração percentual na remuneração base por recurso de mão de obra e a data em que a alteração entrará em vigor.").
