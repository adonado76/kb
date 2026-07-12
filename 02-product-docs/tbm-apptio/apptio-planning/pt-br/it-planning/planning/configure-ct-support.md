---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Configure Apptio Costing Integration Datasets"
breadcrumb: []
source_path: "it-planning/planning/configure-ct-support.html"
images:
  - "resources/planning_images/studio_cost-source-master-data_append-actuals.png"
  - "resources/planning_images/studio_cost-source-master-data_append.png"
  - "resources/planning_images/studio_itpf-budget-transform_date-partition.png"
  - "resources/planning_images/studio_itpf-labor-budget.png"
  - "resources/planning_images/studio_model_configure.png"
  - "resources/planning_images/studio_model_cost-source-to-labor.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configure Apptio Costing Integration Datasets

Conclua as tarefas a seguir para configurar o Costing Standard para oferecer suporte ao Planning. As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

1. Edite seus dados de referência conforme necessário. Consulte [Gerenciar dados de referência](manage-reference-data.html).
2. Importar dados de referência do site Costing Standard. Consulte [Integrar com transparência de custos](integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados.").
3. Configure Costing Standard. Para saber mais, consulte [Costing Standard Configuração do Foundation Module](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=costing-standard-foundation-module-configuration "(Abre em uma nova guia ou janela)"). Você precisará criar um projeto Costing
   Standard , configurar o tempo para o projeto e fazer upload e mapear os dados do Costing Standard .
4. Instale os componentes Apptio ITPF Integration e CTF-Labor em Costing Standard.
5. Certifique-se de configurar a integração de dados com Costing Standard. Consulte [Integrar com transparência de custos](integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados."). Apptio recomenda que você considere cuidadosamente a cadência das atualizações e as convenções de nomenclatura ao fazer a integração com o site Costing Standard.
6. Use as instruções a seguir para configurar seus conjuntos de dados, dados mestre e modelos.

A tabela a seguir descreve todos os dados de referência necessários para dar suporte ao site Planning. Cada conjunto de dados inclui um modelo exclusivo usado para mapear dados de seus arquivos de origem brutos para o mestre.

| Conjunto de dados | Descrição |
| --- | --- |
| Mestre de contas | Normalmente derivados de dados de referência de contas, esses dados incluem mapeamento de pool de custos para futuras atualizações de importação. |
| Mestre do centro de custos | Normalmente derivado da estrutura hierárquica de sua empresa. Pode ser o mesmo que a lista de departamentos. |
| Mestre de Departamento | Normalmente derivado da estrutura hierárquica de sua empresa. |
| Mestre de localização | (Opcional) Lista dos locais de operação da empresa usados para alavancar os recursos de planejamento de mão de obra. Podem ser locais de escritórios, regiões geográficas, etc. |
| Mestre do fornecedor | (Opcional) Liste os fornecedores com os quais sua empresa contrata para fornecer os serviços ou suprimentos necessários para aprimorar os recursos de planejamento de mão de obra e contratos. |
| Mestre da classe de ativos | Usado para planejamento de ativos. Contém as informações necessárias para determinar os tipos de depreciação, os métodos de cálculo e os mapeamentos entre a classe do ativo e as contas OpEx ou CapEx. Se você precisar carregar o mestre da classe de ativos, crie e carregue-o separadamente. |
| Tipo de contrato Mestre | Usado para planejamento de contratos. Contém as informações necessárias para determinar os mapeamentos entre os tipos de contrato e as contas OpEx ou CapEx. Se você precisar carregar o mestre do tipo de contrato, crie e carregue-o separadamente. |
| Mestre da função trabalhista | Usado para planejamento de mão de obra. Contém informações para cada função trabalhista exclusiva. |
| Mestre de taxas de trabalho | Usado para planejamento de mão de obra. Contém as informações necessárias para determinar o mapeamento entre as funções de trabalho e as taxas de remuneração. |
| Mestre de regras de alocação de mão de obra | Identifica as regras de alocação para funcionários internos e externos usadas para determinar seu custo para a empresa (por exemplo, impostos e bônus). Esses dados são atualizados em seu aplicativo Apptio Planning . |
| Realidades Mestre | Usado para elaboração de orçamentos e previsões. Traduz os dados reais do registro geral para o modelo Planning . |
| Tipo de conta de transferência Mestre | Usado para determinar a alocação correta de dinheiro para consumir ou apoiar vários departamentos ou grupos de trabalho. |
| Mestre de permissões de objetos de custo | Usado para determinar quais usuários podem visualizar, editar ou aprovar um objeto de custo. |

Um novo campo "Código" foi adicionado às tabelas de dados Mestre de Função de Trabalho, Mestre de Fornecedor e Mestre de Local. Esse campo é equivalente ao ID nos projetos de cálculo de custos.  
Por exemplo, ID de mão de obra = código no mestre de funções de mão de obra, ID de fornecedor = código no mestre de fornecedores e local = código no mestre de locais.

## Configurar conjuntos de dados

## Dados reais

Anexar dados reais do razão geral ao mestre de origem de custos com os mapeamentos apropriados.

![msd](../../../../../03-media/apptio-planning/resources/planning_images/studio_cost-source-master-data_append-actuals.png)

## Dados planejados

Ao instalar o componente de integração Planning , uma série de transformações é instalada.

Se ocorrer um problema durante a etapa Date Partition (Partição de data), modifique o formato dos dados do plano (linhas ou colunas).

![dados de plano](../../../../../03-media/apptio-planning/resources/planning_images/studio_itpf-budget-transform_date-partition.png)

A tabela a seguir fornece os mapeamentos e as fórmulas necessárias como parte da anexação ao mestre de origem de custos. Essas etapas abordam o seguinte, mas podem ser necessários mapeamentos adicionais:

- Orçamento de Trabalho da ITPF
- Previsão de mão de obra da ITPF

Há várias diferenças taxonômicas entre Planning e Costing Standard, incluindo a tradução entre um centro de custo e um objeto de custo. Por exemplo, um objeto de custo é usado para definir um departamento, projeto, serviço ou unidade de negócios. A conversão de objetos de custo para centro de custo deve ser concluída para que o site Planning funcione corretamente.

Você deve adicionar várias fórmulas para traduzir os dados entre os dois sistemas. Complete o mapeamento a seguir:

1. Na tabela ITPF Labor Budget, adicione uma etapa entre as etapas Date Partition e Table :

   ![orçamento trabalhista](../../../../../03-media/apptio-planning/resources/planning_images/studio_itpf-labor-budget.png)
2. Atualize a tabela Orçamento de mão de obra com as seguintes colunas de fórmula:

   | Campo de dados mestre | Valor |
   | --- | --- |
   | Centro de custo | =Objeto de custo |
   | Nome do centro de custos | =Nome do objeto de custo |
   | Proprietário do centro de custo | =lookup(Cost Object, Department Master, Code, Cost Center Owner) |
   | Proprietário | =lookup(Cost Object, Department Master, Code, Owner) |
3. Repita as etapas anteriores para os dados da Previsão de Trabalho ITPF.

## Configurar conjuntos de dados mestre

## Conjunto de dados de dados mestre de origem de custos

Um orçamento ou previsão é considerado um plano financeiro. Cada tipo de plano deve ser anexado aos dados mestre da fonte de custos para que o site Planning funcione corretamente.

![configurar o conjunto de dados mestre](../../../../../03-media/apptio-planning/resources/planning_images/studio_cost-source-master-data_append.png)

## Dados planejados

A tabela a seguir fornece os mapeamentos e fórmulas necessários como parte da anexação aos dados mestre da origem de custos. Essas etapas abordam o seguinte, mas podem ser necessários mapeamentos adicionais:

- Transformação orçamentária da ITPF
- Transformação da previsão de ITPF

Mapeamentos de dados necessários:

| Campo de dados mestre | Valor |
| --- | --- |
| Conta | =Conta |
| Descrição da conta | =Descrição da conta |
| Grupo de contas | =lookup(Account, Account Master, Code, Account Group) |
| Subgrupo de contas | =lookup(Account, Account Master, Code, Account Subgroup) |
| Quantia | =Montante |
| Centro de custo | =Centro de custo |
| Nome do centro de custos | =Descrição do centro de custo |
| Proprietário do centro de custo | =Lookup(Centro de custo, Mestre de departamento, Código, Proprietário do centro de custo) |
| Pool de custos | =Lookup(Account, Account Master, Code, Cost Pool) |
| Subgrupo de custos | =Lookup(Account, Account Master, Code, {Cost Sub-Pool} ) |
| Discricionário/não discricionário | =Lookup(Account, Account Master, Code, {Discretionary/Non-Discretionary} ) |
| Tipo de Despesas | =Tipo de despesa |
| Fixo Variável | =Lookup(Account, Account Master, Code, {Fixed/Variable} ) |
| É trabalho | =IF(Pool de custos IN ("Trabalho interno", "Trabalho externo"), "Sim", "Não") |
| É projeto | =IF(ID do projeto="", "Não", "Sim") |
| É fornecedor | =IF(ID do fornecedor="", "Não", "Sim") |
| ID do periódico | =ID do periódico |
| Linha do jornal | =Descrição da linha |
| ID da linha do diário | =ID do periódico |
| Proprietário | =Lookup(Cost Center, Department Master, Code, IT Owner) |
| ID de Projeto | =ID do projeto |
| Nome do Projeto | =Nome do projeto |
| ID do Fornecedor | =ID do fornecedor |
| Nome do fornecedor | =Nome do fornecedor |

## Dados mestre de mão de obra

A tabela a seguir fornece os mapeamentos e fórmulas necessários como parte da anexação aos dados mestre da origem de custos. Essas etapas abordam o seguinte, mas podem ser necessários mapeamentos adicionais:

- Orçamento de mão de obra ITPF para dados mestre de mão de obra
- Previsão de mão de obra ITPF para dados mestre de mão de obra

Mapeamentos de dados necessários:

| Campo de dados mestre | Valor |
| --- | --- |
| Centro de custo | =Centro de custo |
| Nome do centro de custos | =Nome do centro de custo |
| Proprietário do centro de custo | =Proprietário do centro de custo |
| Pool de custos | =IF(Tipo de funcionário="Interno", "Trabalho interno", "Trabalho externo") |
| Nome do centro de custos | =Descrição do centro de custo |
| Proprietário do centro de custo | =Lookup(Centro de custo, Mestre de departamento, Código, Proprietário do centro de custo) |
| Pool de custos | =Lookup(Account, Account Master, Code, Cost Pool) |
| Subgrupo de custos | ="Despesa" |
| Tipo de funcionário | =Employee Type |
| Tipo de Despesas | =Tipo de despesa |
| Horas | =720 |
| Número de funcionários | =1 |
| Identificação do trabalho | Código |
| Nome do trabalhador | =Nome do funcionário |
| Local | =Localização |
| Proprietário | =Lookup(Cost Center, Department Master, Code, IT Owner) |
| Número de funcionários planejados | =Valor |
| Posição | =Função |
| Região | =Lookup(Location, Location Master, Location, Region) |
| Tipo de função | =Função |
| Título | =Função |
| Fornecedor | =Fornecedor |
| Fator de ponderação | =1 |

## Configurar modelos

Configure os modelos de custo, orçamento e previsão de mão de obra para que o plano de mão de obra e as despesas sejam alocados da origem de custos para a mão de obra, ponderados pelo número de funcionários.

![configurar modelos](../../../../../03-media/apptio-planning/resources/planning_images/studio_model_configure.png)

Os valores financeiros da mão de obra (como dólares) devem ser alocados 100% da fonte de custos para a mão de obra.

![origem de custo](../../../../../03-media/apptio-planning/resources/planning_images/studio_model_cost-source-to-labor.png)

**Tópico principal:** [Conectar-se a Apptio Costing](../../it-planning/planning/adm/adm_capabilities.html)
