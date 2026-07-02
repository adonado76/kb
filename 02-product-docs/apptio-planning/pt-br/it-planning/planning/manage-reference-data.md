---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Dimensões padrão"
breadcrumb:
  - "Planning"
  - "Configuração e administração"
  - "Visão geral dos dados de referência"
source_path: "it-planning/planning/manage-reference-data.html"
images:
  - "resources/images/icons/icon-options.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Dimensões padrão

Aplica-se a: Apptio Planning aplicativos com [Project Financial Planning](pfp/gs-project-financial.html "◆ Aplica-se a: Planejamento com planejamento financeiro de projetos."). As tarefas abaixo exigem que você licencie o site Project Financial Planning. Para ativar os recursos do site Project Financial Planning , consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning."). As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

As dimensões são as categorias de dados essenciais nos itens de linha do orçamento. Muitas dimensões incorporadas têm dependências em outras dimensões. Consulte [Dependências de atributos e dimensões de dados de referência](#Referencedatadimensions__Referencedataattributeanddimensionsdependencies). Nos aplicativos Apptio Planning , você pode trabalhar com dados TBM Studio no Excel, trabalhar com conjuntos de dados mestre e atualizar dados de referência. Consulte [Gerenciar dados de referência](manage-itfmf-reference.html "aplica-se a: Planejamento").

Para obter informações detalhadas sobre dados e formatos de todos os dados financeiros e de referência necessários para o planejamento, consulte o [Guia de dados de referência de planejamento](https://community.apptio.com/docs/DOC-8065 "(Abre em uma nova guia ou janela)").

## Exibir dimensões padrão

Navegue até Planning > Configuration > Reference Data. Se você não vir a dimensão ou o grupo que está procurando, talvez seja necessário ativar esses recursos (consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.") ).

A seguir estão as descrições das dimensões padrão. Selecione um título de dimensão para obter descrições e exemplos em nível de campo.

## Dimensões padrão

As dimensões padrão podem incluir as seguintes categorias:

[Dimensões financeiras](manage-financial-dimensions.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") :

- Conta
- Categoria da conta
- Centro de custos
- Departamento
- Local
- Gerador de variação
- Fornecedor

[Trabalho Dimensões da configuração](manage-labor-configuration.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") :

- Regras de alocação de mão de obra
- Taxas trabalhistas
- Funções

[Dimensões da configuração do contrato](manage-contract-configuration.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") :

- Tipo de contrato
- Taxas de IVA

[Dimensões de permissões de objetos de custo](manage-cost-object.html) :

- Permissões de objeto de custo

[Dimensões de configuração de ativos](manage-asset-configuration.html) :

- Classe de ativos

## Project Financial Planning dimensões

A seguir estão as dimensões padrão para usuários licenciados do Project Financial Planning :

[Dimensões de configuração do projeto](pfp/manage-project-configuration.html) :

- Projeto
- Grupo de projetos
- Pontuação

[Dimensões trabalhistas](manage-labor-configuration.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") :

- Pool de mão de obra externa
- Pool de mão de obra interna

[Dimensões de alocação](manage-allocation-configuration.html) :

- Padrão de conta de transferência

## Service Demand Planning dimensões

A seguir estão as dimensões padrão para usuários licenciados do Service Demand Planning .

[Dimensões do serviço](sdp/manage-service-reference.html) :

- Unidade de negócios
- Grupo de preços
- Serviço
- Categorias de serviço
- Ajustes de preços de serviços
- Unidade de medida

[Trabalho Dimensões da configuração](manage-labor-configuration.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") :

- Pool de mão de obra externa
- Pool de mão de obra interna
- Regras de alocação de mão de obra
- Taxas trabalhistas
- Função

[Dimensões de alocação](manage-allocation-configuration.html) :

- Padrão de conta de transferência

## Várias dimensões de moeda

Os seguintes recursos são visíveis somente se o suporte a várias moedas estiver ativado Consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning."). A seguir estão as dimensões padrão para suporte a várias moedas. Consulte [Suporte para várias moedas](support-multiple-currencies.html).

[Dimensões das tabelas de taxas](manage-multi-currency.html "Apptio O Planning suporta configurações em várias moedas que permitem inserir, exibir e reconciliar dados financeiros em diferentes moedas. Isso é especialmente útil para organizações globais que gerenciam orçamentos em várias regiões.") :

- Taxa de câmbio real
- Taxa de câmbio planejada

## Dependências de atributos e dimensões de dados de referência

Muitas dimensões estão relacionadas. As informações de uma dimensão podem ser dependentes de outra dimensão (dependências) no sistema. Isso pode influenciar quais atributos podem ser excluídos.

Veja a seguir as dimensões e os atributos que podem depender de outras dimensões:

| Dimension | Atributo dependente | Dimensão da fonte |
| --- | --- | --- |
| Departamento | Código do centro de custo | Centro de custos |
| Pool de mão de obra externa | Fornecedor | Fornecedor |
| Pool de mão de obra interna | Código do departamento | Departamento |
| Regras de alocação de mão de obra | Código da conta | Conta |
| Função | Função trabalhista |
| Local | Local |
| Fornecedor | Fornecedor |
| Tipos de contrato | Código da conta | Conta |
| Taxas de IVA | Local | Local |
| Classe de ativos | Código da conta de depreciação | Conta |
| Código da conta de compras |
| Padrão de conta de transferência | Código da conta de transferência | Conta |
| Código da conta de transferência |
| Projeto | Código do centro de custo | Centro de custos |
| Código dos pais | Grupo de projetos |
| Unidade de negócios | Código do centro de custo | Centro de custos |
| Serviços | Código do centro de custo | Centro de custos |
| Código dos pais | Categorias de serviço |
| Código da unidade | Unidade de medida |

As dimensões sem dependências incluem as seguintes:

- Unidade de medida
- Local
- Fornecedor
- Função

## Configurar dados de referência

1. Navegue até Planning > Configuration > Reference Data.
2. Clique na dimensão específica do grupo correto.

Os detalhes específicos da dimensão são exibidos em um formato de tabela. Clique em ![img](../../../../../03-media/apptio-planning/resources/images/icons/icon-options.png) no lado direito para ver uma lista de opções. Dependendo do tipo de dimensão, as opções disponíveis e aplicáveis podem variar.

| Opção | Detalhes |
| --- | --- |
| Modelo de identificadores | [Alterar o identificador para objetos de custo e dimensões](change-identifier.html "O recurso Identificadores de alteração permite que os administradores atualizem os identificadores do sistema (códigos) usados pelas dimensões dos dados de referência, como Centros de custo, Contas, Projetos e Departamentos.") |
| Alterar identificadores | [Alterar o identificador para objetos de custo e dimensões](change-identifier.html "O recurso Identificadores de alteração permite que os administradores atualizem os identificadores do sistema (códigos) usados pelas dimensões dos dados de referência, como Centros de custo, Contas, Projetos e Departamentos.") |
| Modelo de exportação | [Editar e publicar tabelas de dados de referência](edit-publish-reference.html) |
| Exportar | [Editar e publicar tabelas de dados de referência](edit-publish-reference.html) |
| Importar | [Editar e publicar tabelas de dados de referência](edit-publish-reference.html) |
| Publicar | [Editar e publicar tabelas de dados de referência](edit-publish-reference.html) |
| Reverter | [Editar e publicar tabelas de dados de referência](edit-publish-reference.html) |
| Importar da transparência de custos | [Integre com transparência de custos](integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados.") [Importar e publicar dados reais](import-publish-actuals.html) |
| Fechar Mostrar/Ocultar colunas | Feche a barra Mostrar/Ocultar Colunas |

VEJA TAMBÉM :

- [Editar e publicar tabelas de dados de referência](edit-publish-reference.html)
- [Gerenciar dados de referência personalizados (dimensões e listas)](manage-custom-reference.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.")
- [Forçar um plano para usar dados de referência atualizados](force-plan-use.html)
- [Diagrama de dependências da tabela de referência](https://community.apptio.com/docs/DOC-9956 "(Abre em uma nova guia ou janela)")

**Tópico principal:** [Visão geral dos dados de referência](../../it-planning/planning/edit-publish-reference.html)
