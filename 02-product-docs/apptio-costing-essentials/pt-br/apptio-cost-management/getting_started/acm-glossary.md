---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "pt-br"
doc_type: "apptio-cost-management"
title: "Conceitos e terminologias fundamentais"
breadcrumb:
  - "Costing Essentials"
  - "Introdução"
source_path: "apptio-cost-management/getting_started/acm-glossary.html"
images: []
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Conceitos e terminologias fundamentais

| Campos | Descrição |
| --- | --- |
| Ponderação de alocação | Porcentagem das despesas no objeto de origem que é alocada para os objetos de destino  Talvez uma alocação de 100% (insira "1") ou dividida em vários tipos/categorias de solução |
| Conta | A conta do registro geral que é usada para coletar e armazenar valores. Conta é o código de identificação usado no GL. |
| Descrição da conta | O nome da conta do registro geral. |
| Grupo de contas | O agrupamento hierárquico de primeiro nível de contas no livro-razão Classificação/agrupamento de contas a ser usado em relatórios. Isso precisa ser adicionado manualmente ao ITP para que os relatórios de CT sejam preenchidos |
| Subgrupo de contas | O segundo nível, agrupamento hierárquico de contas no livro-razão. Imediatamente, o site Apptio suporta três níveis: Grupo de contas, subgrupo de contas, conta |
| Métodos de alocação | O método de alocações inclui  Alocação direta  Para alocação entre uma Fonte e um alvo  A ponderação deve ser padronizada como 1 e deve ter apenas uma linha.  Divisão percentual  Para alocações baseadas em porcentagem ponderada  deve ter 2 ou mais linhas com atribuição de peso relativo.  Divisão de volume  Para alocações baseadas em atributos de volume/quantidade (por exemplo, contagem de licenças de aplicativos)  Deve ter 2 ou mais linhas com volumes atribuídos.  Uso estimado ponderado  habilita as colunas % Headcount Usage e User Weighting  deve ter 2 ou mais linhas. |
| ID da transação AP | Um identificador exclusivo para um item de linha individual no conjunto de dados de Contas a pagar. |
| Descrição da transação AP | A descrição dessa entrada de linha de ID de contas a pagar. |
| Preenchimento | O número de funcionários em aberto é para substituir um funcionário ou prestador de serviços existente? |
| Relacionamento comercial  Gerenciador | O principal gerente de contas de TI responsável por uma unidade de negócios específica. |
| Unidade de negócios | Um elemento ou segmento lógico de uma empresa (como contabilidade, produção, marketing) que representa uma função comercial específica e um lugar definido no organograma, sob o domínio de um gerente.  Na definição do site Apptio, a Unidade de Negócios é o Nível 1 na hierarquia da organização e o Departamento é o Nível 2 na hierarquia da organização. |
| Tipo de unidade de negócios | Uma categorização que indica se a UN (ou departamento) está gerando receita ou não.  Apptio Os valores recomendados incluem: "Geração de receita", "Não geração de receita". |
| Compensação | A remuneração total do funcionário.  Por exemplo: Pode incluir Superannuation + Bônus, além do salário base |
| Valor do contrato | O valor acordado a ser pago pelos serviços prestados no contrato. |
| Descrição do contrato | Uma breve descrição do contrato. |
| Dias de notificação do contrato | O tempo de espera (em dias) que a notificação deve ser fornecida a um fornecedor sobre solicitações de não renovação ou alteração de contrato. |
| Renovação automática do contrato | Designa se um contrato é renovado automaticamente. |
| Número do contrato | O número atribuído ao contrato pela empresa. |
| Proprietário do contrato | O nome da pessoa responsável pelo contrato. |
| Planos de renovação de contratos | Designa o plano para o futuro do contrato. Valores válidos: RFP competitiva, Estender como está, Mudar internamente, Mudar para outro fornecedor, Não é mais necessário, Renegociar termos |
| Título do contrato | O título do contrato. |
| Prazo do contrato | A duração em dias entre a data de início e de término do contrato. |
| Centro de custo/código do centro de custo | Um centro de custos é o departamento ou "subunidade" de uma empresa que é responsável por seus custos. Centro de custo é o código de identificação usado no GL e nos subcontroladores.  O centro de custos se refere ao departamento que incorreu na despesa original (por exemplo, centro de custos de TI) e àqueles que serão cobrados pelos serviços de TI do consumidor (centro de custos de negócios) |
| Nome do centro de custos | O nome do centro de custo associado ao código do centro de custo. |
| Pool de custos e sub-bolsa de custos | ATUM fornece uma taxonomia padrão do setor para categorizar as despesas, que identifica prontamente a finalidade das despesas e auxilia na análise comparativa com os benchmarks do setor.  Consulte a TBM Framework & Taxonomy e a folha Cost Pool Taxonomy na planilha ATUM V4.0 para obter a definição completa de ATUM Cost Pools e Cost Sub pools |
| Valor da depreciação | O valor que o ativo é depreciado a cada período. |
| Entrega | Sourcing da oferta de serviço/solução do fornecedor; normalmente: "On Prem"; "Private Cloud" ou "Public Cloud" |
| Tipo de funcionário | Categoriza os recursos do trabalho como  **Internos** : Recursos assalariados considerados parte dos PDIs Número de funcionários/FTE  **Externo** : Aumento da equipe, incluindo contratados individuais (proprietários) e empresas de recrutamento |
| Tipo de Despesas | Designa uma das despesas como OpEx ou Capex |
| ID do ledger de ativos fixos | Um identificador exclusivo definido pelo usuário para o Ledger de ativos fixos |
| Número do ativo fixo | O número do ativo ou a ID do ativo |
| Órgão governamental | O proprietário do órgão de governança representa uma estrutura organizacional de nível mais alto do que a unidade de negócios. Isso pode ser usado para distinguir entre diferentes entidades operacionais ou talvez diferentes estruturas internacionais dentro da empresa. |
| Objetivo do investimento | estratégia de investimento prospectiva para o aplicativo/serviço Usado para priorizar recursos e investimentos em aplicativos/serviços novos e existentes que estejam alinhados com  imperativos e objetivos da empresa. |
| A CSP é | (Trata-se de um provedor de serviços em nuvem)  Designa o fornecedor que fornece serviços de nuvem IaaS ou PaaS (por exemplo, computação em nuvem, armazenamento em nuvem) ao IDP  Os principais fornecedores de CSP compatíveis com OOTB são Amazon/ AWS, Microsoft/ Azure, Google /GCP, Oracle /OCI  O ACM pode ingerir automaticamente os dados de faturamento dos fornecedores de CSPs, mapear e alocar automaticamente os recursos faturados para as ofertas de serviços no ACM |
| ID do periódico | O código de identificação do diário para a transação ou o lançamento do diário. O lançamento contábil manual contém a data, o nome da conta e o valor a ser debitado ou creditado no Razão. |
| Identificação do trabalho | Um identificador exclusivo definido pelo usuário para o conjunto de dados do Labor |
| Função trabalhista | A principal função do funcionário na organização de tecnologia. |
| Estágio do ciclo de vida | O estado atual do aplicativo/serviço comercial.  Apptio os valores recomendados incluem: Em desenvolvimento, Em serviço, Aposentado. |
| ID da organização | Identificador exclusivo para cada consumidor (unidade de negócios)  Selecione em uma lista de Consumidores, ingerida no ACM a partir da fonte de dados mestre Organizacional do IDP e enriquecida no ACM por meio do workbench de Mapeamento Organizacional |
| Contrato dos pais | O contrato principal do contrato atual usado para acumular as despesas do contrato para contratos maiores com subcontratos. |
| Número de OC | Um número que identifica um pedido de compra associado a essa entrada de linha de Contas a pagar. |
| Taxa de OP | A taxa do pedido de compra para a função de contratante externo. |
| Projeto Orçamento aprovado | O valor das despesas operacionais e de capital aprovadas para um projeto específico. Esse número reflete o último orçamento total aprovado do projeto para o ano e pode ser diferente do orçamento original/base do projeto. |
| Projeto Iniciativa Empresarial | A iniciativa comercial específica, conforme definida pela empresa, à qual o projeto está alinhado. Isso é usado para determinar o número de projetos e investimentos em TI que estão sendo feitos em relação às várias iniciativas comerciais para determinar se os investimentos estão alinhados com a estratégia e as principais iniciativas da empresa. |
| Patrocinador de negócios do projeto | A principal pessoa da empresa que está patrocinando ou solicitando o projeto específico. |
| Unidade patrocinadora do negócio do projeto | O nome da unidade de negócios que é o principal patrocinador do projeto. Pode ser de TI ou LOB, dependendo do tipo de projeto (por exemplo, projeto de infraestrutura vs. projeto LOB). |
| ID do Projeto | O identificador exclusivo do projeto ou investimento, conforme definido pelo portfólio de projetos ou pelo sistema de gerenciamento de investimentos.    Selecione a partir da lista de projetos, ingerida no ACM a partir do sistema de registro de Gerenciamento de Portfólio de Projetos (PPM) do IDP e enriquecida no ACM por meio do banco de trabalho de Mapeamento de Projetos |
| Gerentes de projeto | O principal gerente de projeto responsável pelo planejamento e execução do projeto a partir de uma perspectiva de discípulo de gerenciamento de projetos. |
| Nome do Projeto | O nome exclusivo do projeto ou investimento. |
| Número do pedido de compra | O número que identifica um pedido de compra associado a essa entrada de linha de Contas a pagar. |
| Programa do projeto | Programa refere-se a um grupo de projetos ou investimentos relacionados. |
| Portfólio de projetos | O agrupamento de investimentos relacionados em um "portfólio". Refere-se a  o portfólio específico ao qual o projeto ou investimento pertence. |
| Tipo de despesa do projeto | A categorização de investimento das despesas ou do orçamento de TI. Os valores válidos normalmente são Executar/Modificar o negócio (RTB, CTB) ou Executar/Crescer/Transformar o negócio (RTB, GTB, TTB). |
| Motivo planejado | O motivo do número de funcionários em aberto. |
| Número da solicitação | O número da requisição para o cargo de headcount aprovado. |
| Faixa salarial | A faixa salarial usada para alocações de custos ponderados no modelo de custos. |
| ID da oferta de solução | O identificador exclusivo para o nome da Oferta.    Selecione a partir de valores no Catálogo de Serviços do IDP ingeridos no ACM e enriquecidos no ACM por meio do Solution Mapping workbench |
| Categoria de solução | Meta dados que categorizam e organizam as ofertas de serviços em seu catálogo de serviços  Nível um da taxonomia da camada de solução TBM.  Selecione a partir de valores no Catálogo de Serviços do IDP ingeridos no ACM e enriquecidos no ACM por meio do Solution Mapping workbench |
| Proprietário da solução de TI | A principal pessoa de TI responsável pelo desenvolvimento e suporte da oferta específica. |
| Tipo de oferta de solução | Identifica se a oferta é chamada de aplicativo, produto ou serviço, dependendo do modelo operacional de TI. |
| Tipo de solução | Meta dados que categorizam e organizam as ofertas de serviços em seu catálogo de serviços  Nível dois da taxonomia da camada de solução TBM.  Selecione a partir de valores no Catálogo de Serviços do IDP ingeridos no ACM e enriquecidos no ACM por meio do Solution Mapping workbench |
| Interação com o usuário | Uma categorização do consumidor primário do produto e serviço no que se refere à entrega direta e à interação com o fornecedor. Os valores recomendados incluem: Voltado para o negócio (por exemplo, usuários comerciais da empresa), voltado para o cliente (por exemplo, clientes da empresa), voltado para o interior (por exemplo, interno na empresa de TI)  organização) |
| Categoria do fornecedor | Uma categorização de alto nível da função que o fornecedor oferece.  Pode permitir uma análise mais detalhada das despesas do fornecedor. Por exemplo: Comparar despesas de fornecedores da mesma categoria |
| ID do Fornecedor | O sistema de ID do fornecedor usado para rastrear a empresa que fornece o produto ou serviço    Identificador exclusivo para cada fornecedor  Selecionado de uma lista de fornecedores, ingerido no ACM a partir do sistema de registro de fornecedores do IDP e enriquecido no ACM por meio do banco de trabalho de mapeamento de fornecedores  A lista de fornecedores não inclui todos os fornecedores, mas aqueles que representam a maior parte de seus gastos anuais (por exemplo, 80%).  A lista de fornecedores não incluirá os fornecedores que prestam serviços de aumento de equipe, pois essas despesas são consideradas  despesas trabalhistas (externas) |
| Gerente de fornecedores | O nome da pessoa que é a principal responsável pelo gerenciamento do relacionamento com o fornecedor. Pode ser um gerente formal de compras/fornecedor ou o gerente de TI que contratou os produtos ou serviços do fornecedor. |
| Serviço principal do fornecedor | Uma classificação do tipo principal de produto ou serviço que o fornecedor fornece.    Pode permitir uma análise mais detalhada das despesas do fornecedor. Por exemplo: Comparar despesas de fornecedores que prestam os mesmos serviços/executam a mesma função |
| Tipo de fornecedor | Uma classificação de fornecedores para fornecer gerenciamento e supervisão adequados para otimizar preços e riscos. As categorias recomendadas são: Estratégico, Preferencial e Transacional    As categorias recomendadas são: Estratégico, Preferencial, Transacional e Legado. |
| Ponderação | Consulte Ponderação de alocação |
