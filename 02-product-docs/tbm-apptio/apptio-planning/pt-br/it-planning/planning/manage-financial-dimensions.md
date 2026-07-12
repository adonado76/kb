---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Dados de referência das Dimensões Financeiras"
breadcrumb: []
source_path: "it-planning/planning/manage-financial-dimensions.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Dados de referência das Dimensões Financeiras

As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

As dimensões são as categorias de dados essenciais nos itens de linha do orçamento. Muitas dimensões incorporadas têm dependências de outras dimensões (consulte [Dependências de atributos e dimensões de dados de referência](manage-reference-data.html) para obter mais informações). Você pode importar dados de referência de dimensões de um arquivo.csv ou do site Costing Standard e exportar modelos de dados de referência de dimensões e dados de tabela (consulte [Gerenciar dimensões](manage-reference-data.html) ).

![imagem](../../resources/images/it%20planning_images/icon_video.png)

Assista a estes vídeos do site Apptio Education Services:

- [Configuração de dados de referência: Dimensões financeiras e permissões de objetos de custo](https://community.ibm.com/community/user/viewdocument/configuring-reference-data-financi?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Abre em uma nova guia ou janela)").
- [Compreensão de hierarquias de dados no planejamento](https://community.ibm.com/community/user/viewdocument/understanding-data-hierarchies-in-i?CommunityKey=2e85ed45-9b8a-486c-bd55-019253d466eb&tab=librarydocuments "(Abre em uma nova guia ou janela)").

## Gerenciar dados de referência da conta

Após a importação inicial e a configuração de suas contas, é importante manter o arquivo.csv de dados de contas, incluindo o mapeamento do pool de custos para futuras atualizações de importação.

No menu de navegação do Costing & Planning Plan, selecione **Configuration > Reference Data > Account (Configuração > Dados de referência > Conta** ).

Essa tabela de dados inclui o seguinte:

- **Código** (obrigatório) - O identificador exclusivo de uma conta do razão geral, usado para importar dados reais do razão geral.
- **Nome** (obrigatório) - O nome da conta.
- **Código pai** - Representa a hierarquia de sua conta. Esse é o valor do código de sua conta imediatamente superior ou principal (se houver).
- **Categoria** - Grupos de contas do Razão usados para análise de desvio. Consulte a seção a seguir "[Gerenciar dados de referência da categoria de conta](#FinancialDimensionsreferencedata__ManageAccountCategoryreferencedata) "
- **Pool de custos** - A [categoria ATUM](../../atum/home.html) à qual a conta pertence.
- **Tipo de despesa** (obrigatório) - Define a conta do razão geral como uma conta operacional ( OpEx ) ou de capital ( CapEx ). Se estiver em branco, o valor padrão será OpEx.
- **Grupo** -

Dica:

- Não é possível editar diretamente valores diferentes dos valores do pool de custos na tabela Conta. Mantenha os dados do seu plano de contas em uma pasta de trabalho do Excel com base no modelo.csv, reimporte e republique o arquivo.csv conforme necessário.
- Recomenda-se gerar novos arquivos.csv a partir da pasta de trabalho do Excel em vez de editar diretamente o arquivo.csv. Trate a pasta de trabalho do Excel como editável e o arquivo.csv como somente leitura. Caso contrário, o Excel poderá remover os zeros à esquerda ao abrir um arquivo.csv, o que pode criar problemas com números de contas que incluem zeros à esquerda.
- Você também pode personalizar substancialmente as dimensões dos dados de referência e as tabelas de itens de linha (consulte [Gerenciar dados de referência personalizados (dimensões, listas e tabelas de itens de linha).](manage-custom-reference.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.")

## Gerenciar dados de referência da categoria de conta

Essa dimensão agrupa as contas detalhadas do razão geral em uma lista gerenciável para análise de variação. Consulte [Analisar variação orçamentária](analyze-budget-variance.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor."). recomenda-se de 10 a 15 valores discretos para essa dimensão. Talvez você já tenha algo semelhante implementado como um atributo personalizado em seus dados de referência da conta.

Observação: A dimensão Categoria da conta não suporta atualmente a importação de Costing Standard. No entanto, você pode criar os dados de referência em Costing Standard (consulte [Integrar com transparência de custos](integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados.") ).

1. No menu de navegação do Costing & Planning  Plan, selecione Configuration > Reference Data > Account Category (Configuração > Dados de referência > Categoria de conta).
2. Atualize os valores da tabela de dados conforme necessário:
   - Código (obrigatório) - O identificador exclusivo da categoria ou do agrupamento de sua conta (por exemplo, ADMIN)
   - Nome (obrigatório) - O nome da categoria ou agrupamento de sua conta (por exemplo, Instalações e Administração)

Aqui estão alguns exemplos de valores de dados de referência da categoria de conta:

| Código | Nome |
| --- | --- |
| CAPITAL | Investimentos de capital |
| Consultoria | Consultoria |
| EXT-LABOR | Contrato de trabalho |
| DEPRECIAÇÃO | Depreciação |
| ADMIN | Administração de instalações e escritórios |
| EMP-OTHER | Outros custos com funcionários |
| SERVIÇOS | Serviços externos |
| EMP-SALARY | Salários e benefícios |
| TECNOLOGIA | Tecnologia |
| TELECOM | Telecomunicações |

## Gerenciar os dados de referência do centro de custos

Os centros de custo representam atributos de itens de linha que são mapeados para objetos de custo.

1. No menu de navegação do Costing & Planning  Plan, selecione Configuration > Reference Data > Cost Center.
2. Atualize os valores da tabela de dados conforme necessário:
   - Código (obrigatório) - O identificador exclusivo do centro de custos (geralmente fornecido pelo sistema financeiro corporativo), usado para importar dados reais do razão geral e empregado em planos de integração com sistemas financeiros corporativos.
   - Nome (obrigatório) - O nome do centro de custos.
   - Código pai - Representa a hierarquia do centro de custos. Esse é o valor do código de seu centro de custo pai ou de nível imediatamente superior (se houver). Observe que a hierarquia do centro de custo não está relacionada à hierarquia de aprovação do orçamento ou do plano de previsão nos aplicativos Apptio Planning . Elas são determinadas pelas permissões de objetos de custo de sua organização (consulte os dados de referência Gerenciar permissões de objetos de custo).

## Gerenciar dados de referência do departamento

Essa dimensão representa a estrutura de sua organização. Especificamente, os departamentos representam a estrutura hierárquica da sua organização de TI (ou qualquer estrutura que você preferir) para planejamento e relatórios orçamentários. Os departamentos são um tipo de objeto de custo (os projetos são outro exemplo de objetos de custo). Os dados de referência das permissões de objetos de custo determinam quem pode editar cada departamento e quem pode aprovar os envios de planos orçamentários. Consulte [os dados de referência de Manage Cost Object Permissions (Gerenciar permissões de objetos de custo).](manage-cost-object.html "As permissões de objetos de custo determinam quais usuários podem visualizar, editar, enviar ou aprovar planos em nível de departamento (objetos de custo). Cada departamento pode ter um ou mais usuários atribuídos com permissões de nível de edição e, para aprovações multinível, permissões de nível de aprovação.")

Importe e publique dados de referência para seu departamento usando arquivos no formato.csv mantidos fora de seus aplicativos Apptio Planning .

1. No menu de navegação do Costing & Planning  Plan, selecione Configuration > Reference Data > Department (Configuração > Dados de referência > Departamento).
2. Atualize os valores da tabela de dados conforme necessário:
   - Código (obrigatório) - O identificador exclusivo do departamento.
   - Nome (obrigatório) - O nome do departamento.
   - Código pai - Representa a hierarquia do seu departamento.
   - Código da moeda - A moeda comum do departamento. Necessário quando várias moedas estão ativadas (consulte Suporte para várias moedas). O valor da moeda comum do Departamento deve ser o código ISO de três letras da moeda. Se nenhum código de moeda for inserido, será usada a moeda comum padrão. - Grupo de preços - Determina o grupo de preços do departamento para modelos de preços baseados em região ou em camadas.
   - Default Cost Center Code (Código do centro de custo padrão) - O valor padrão, a menos que seja fornecido um valor de código de centro de custo diferente.
   - Código do centro de custos - O identificador dos centros de custos correspondentes (consulte Gerenciar dados de referência do contrato). Ao importar os dados reais, eles são alocados por centro de custo e, em seguida, mapeados para o objeto de custo (consulte Importar e publicar dados reais). Um departamento pode ser associado a vários centros de custo e pode incluir itens de linha (volumes, mão de obra ou despesas) registrados para mais de um centro de custo. Adicione vários centros de custo à célula da tabela usando uma vírgula para separá-los. OBSERVAÇÃO: um departamento pode ser associado a vários centros de custo, mas um centro de custo só pode ser associado a um departamento.

**VEJA TAMBÉM** : [Atualizar a hierarquia de departamentos](update-department-hierarchy.html)

## Gerenciar dados de referência de localização

Ao definir a Localização, você pode determinar onde os custos serão incorridos. Além disso, a localização ajuda a definir outras dimensões, como o imposto sobre valor agregado (IVA). Consulte [Gerenciar dados de referência do contrato](manage-contract-configuration.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") )

1. No menu de navegação do Costing & Planning  Plan, selecione **Configuration > Reference Data > Location (Configuração > Dados de referência > Localização** ).
2. Atualize os valores da tabela de dados conforme necessário: **Nome**, **Continente** e **País** do Local.

## Gerenciar dados de referência do Variance Driver

Essa dimensão define uma lista configurável de drivers de variação comuns para seus usuários. Essa abordagem estruturada permite a elaboração eficaz de relatórios de roll-up dos fatores de variação. Consulte [Analisar variação orçamentária](analyze-budget-variance.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.").

**OBSERVAÇÃO** : (para usuários do Costing Standard ): Se você criar os dados de referência da **Categoria da conta** em Costing Standard e depois mapear para Conta, a importação de Costing Standard importará esses mapeamentos para o aplicativo Apptio Planning . Consulte [Integrar com transparência de custos](integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados."). No momento, o Variance Driver não suporta a importação de Costing Standard.

1. No menu de navegação Costing & Planning  Plan, selecione Configuration > Reference Data > Variance Driver.
2. Atualize os valores da tabela de dados conforme necessário:
   - Código (obrigatório) - O identificador exclusivo de seu driver de variação (por exemplo, TIMING)
   - Grupo - Determina o grupo para o driver de desvio (em desenvolvimento, deixe em branco)
   - Nome (obrigatório) - O nome do driver de variação (por exemplo, Project Timing)

Exemplo Variance Drivers valores de dados de referência:

| Código | Grupo | Nome |
| --- | --- | --- |
| IMPACTO | Contabilidade | Impacto contábil |
| TEMPO | Contabilidade | Tempo de contabilidade |
| TAXA DE EXECUÇÃO | Operações | Mudança na taxa de execução |
| PIVÔ | Projetos | Mudança no investimento estratégico |
| FOREX | Outros | Impacto do câmbio |
| CRESCIMENTO | Operações | Crescimento |
| SERVIÇOS | Operações | Tempo de impacto dos serviços gerenciados |
| Outro | Outros | Outros (<20%) |
| PROJETO | Projetos | Cronograma do projeto |
| DEMANDA | Operações | Variação da demanda de recursos |
| NÃO PLANEJADO | Outros | Despesas de itens não planejados |

## Gerenciar dados de referência do fornecedor

Ao definir o fornecedor, os proprietários de orçamento podem contabilizar os custos de empresas externas.

1. No menu de navegação do Costing & Planning  Plan, selecione **Configuration > Reference Data > Vendor (Configuração > Dados de referência > Fornecedor** ).
2. Atualize os valores da tabela de dados conforme necessário: **Nome** e **Grupo** associados ao fornecedor.
