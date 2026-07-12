---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Principais conceitos e terminologia"
breadcrumb:
  - "Planning"
  - "Introdução"
source_path: "it-planning/planning/key-concept-term.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Principais conceitos e terminologia

A compreensão dos conceitos básicos do Apptio Planning o ajudará a navegar pelo aplicativo. Abaixo estão as definições dos principais termos usados com frequência no Planejamento.

**Objeto de custo (departamentos)**

Um **objeto de custo é** uma estrutura financeira usada no Apptio Planning para organizar e alocar custos. Ele fornece a base para a atribuição de despesas, o estabelecimento da propriedade dos custos e o acompanhamento do desempenho financeiro.

No Apptio Planning, os Objetos de custo são sinônimos de **Departamentos** e podem ser estruturados em uma **hierarquia**, permitindo que os custos sejam transferidos de departamentos de nível de folha para grupos de nível superior. Essa hierarquia permite que as organizações visualizem e analisem os custos em vários níveis de detalhes, desde departamentos individuais até roll-ups consolidados.

**[Plano](create-plan.html)**

Um **Plano** é um modelo financeiro estruturado no Apptio Planning em que os usuários inserem, ajustam e analisam dados em um horizonte de tempo definido. Os planos podem representar orçamentos, previsões ou perspectivas plurianuais.

**Plano orçamentário**

Um **plano orçamentário** é um tipo de plano que não inclui dados reais. Todos os períodos são totalmente editáveis, permitindo que os planejadores definam projeções a partir do zero ou redefinam as expectativas sem serem limitados pelo desempenho histórico.

**Plano de previsão**

Um **Plano de Previsão** inclui dados reais de períodos históricos. Somente os períodos futuros são editáveis, permitindo que os planejadores ajustem as projeções com base no desempenho passado, mantendo os resultados reais fixos.

**[Snapshot](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=workflows-submit-review-approve-return-plans#subrevappret__snapshot__title__1 "(Abre em uma nova guia ou janela)") (versão)**

**Snapshots** são versões salvas do plano de um departamento que capturam seus dados em um momento específico. Eles fornecem um registro histórico da aparência do plano de um departamento quando ele foi enviado ou salvo manualmente.

- Os instantâneos só podem ser criados para **departamentos folha** (o nível mais baixo na hierarquia de departamentos).
- Um instantâneo é gerado automaticamente sempre que um departamento envia seu plano.
- Os usuários também podem criar snapshots sob demanda para preservar o estado do plano de um departamento a qualquer momento.
- Ao comparar planos, você pode selecionar um instantâneo anterior para comparar, facilitando o rastreamento de alterações, a validação de suposições e a medição do progresso em relação a versões anteriores.

**[Metas](set-financial-targets.html "Você pode definir metas financeiras no Apptio Planning para definir metas ou limites de gastos para OpEx, CapEx, e Headcount no nível do departamento. As metas estabelecem expectativas financeiras de cima para baixo que podem ser comparadas com os dados do plano de baixo para cima ao longo dos ciclos de planejamento e previsão.")**

**As metas** representam objetivos financeiros ou de número de funcionários definidos pelos administradores ou pela liderança. Eles servem como referência para comparar os valores do plano e garantir o alinhamento com os objetivos organizacionais.

No Apptio Planning, as metas podem ser definidas para **OpEx**, **CapEx** e **número de funcionários**, e são aplicadas no **nível do departamento**. Essas metas fornecem orientação aos planejadores, ajudando a garantir que os planos departamentais sejam implementados para atender às metas organizacionais gerais.

**[Gerenciamento de despesas](spend-management.html "O Spend Management permite que você gerencie dados reais importando transações mensais para o Apptio Planning. Ao integrar os dados reais, você pode alinhar seus modelos de planejamento e previsão com o desempenho real, permitindo melhor visibilidade, rastreamento de variações e tomada de decisões.")**

O **Spend Management** é o processo de importação e gerenciamento de dados reais (dados financeiros históricos) no Apptio Planning. Isso garante que os planos sejam baseados em um desempenho financeiro preciso e atualizado.

**[Dados de referência](edit-publish-reference.html)**

**Os dados de referência** fornecem valores padronizados, como departamentos, centros de custo ou contas, que podem ser reutilizados em todos os planos. Ele garante consistência, precisão e alinhamento em todas as atividades de planejamento.

Quando um novo plano é criado, ele usa automaticamente a última **versão publicada** dos dados de referência. Se os dados de referência forem atualizados posteriormente, você poderá atualizar manualmente um plano para usar a versão mais recente publicada.

Importante: a atualização dos dados de referência pode, às vezes, resultar em perda de dados. Por exemplo, se um centro de custo ou conta for removido, todas as partidas individuais relacionadas no plano também serão excluídas.

Para ajudar a evitar atualizações destrutivas, você pode ajustar a configuração **Disable Update Reference Data Restrictions (Desativar restrições de atualização de dados de referência** ) no Company Profile (Perfil da empresa). Quando as restrições são desativadas, o sistema cria automaticamente uma cópia do plano antes de aplicar as atualizações de dados de referência, oferecendo uma opção de fallback se você precisar reverter.

**[Dimensão padrão](manage-reference-data.html)**

**As dimensões padrão** são as dimensões predefinidas e prontas para uso fornecidas pelo Apptio Planning. Eles representam as principais estruturas financeiras e organizacionais normalmente necessárias para o planejamento, como departamentos, contas, fornecedores e taxas de mão de obra. Essas dimensões estão sempre disponíveis e não podem ser removidas.

**[Dimensões personalizadas](manage-custom-reference.html "As tarefas abaixo só podem ser executadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.")**

As dimensões personalizadas são **dimensões criadas pelo usuário** que ampliam o modelo de dados padrão. Eles permitem que as organizações capturem níveis adicionais de análise ou categorização além da estrutura pronta para uso.

- Você pode criar até **40 dimensões personalizadas**.
- As dimensões personalizadas podem ser adicionadas a esquemas e referenciadas em itens de linha para dar suporte a relatórios, filtragem e análise adaptados às suas necessidades comerciais.

**Atributos**

Atributos são **campos adicionais (colunas)** que podem ser adicionados a uma Dimensão ou Esquema. Eles fornecem mais detalhes descritivos ou operacionais sem exigir uma nova dimensão. Por exemplo:

- Em uma dimensão de **Departamento**, você pode adicionar atributos como *Proprietário do departamento* ou *Região*.
- Em um esquema de **projeto**, você pode adicionar atributos como *Prioridade do projeto* ou *Fonte de financiamento*.

Os atributos são especialmente úteis para armazenar metadados que ajudam a gerar relatórios ou filtros, mas não exigem uma estrutura de dimensão completa.

**Tipos de atributos compatíveis** :

|  |  |
| --- | --- |
| **Tipo** | **Descrição** |
| Sequência | Armazena valores de texto, como nomes, descrições ou códigos. Suporta um máximo de 256 caracteres. |
| Data | Captura uma data de calendário específica (por exemplo, data de início do contrato ou data de contratação). |
| Número Inteiro | Armazena números inteiros sem decimais (por exemplo, número de funcionários, número de licenças). |
| Numérico | Armazena valores numéricos, inclusive decimais, para dados financeiros ou quantitativos (por exemplo, custo, taxa). |
| Percentual | Representa valores numéricos como porcentagens (por exemplo, taxa de alocação, utilização). |
| Memorando | Usado para texto longo ou notas, como comentários ou descrições detalhadas. Suporta um máximo de 1024 caracteres. |
| Lista | Fornece um conjunto predefinido de valores selecionáveis (por exemplo, região, tipo de departamento). |
| Usuário | Faz referência a um usuário no Apptio Planning, permitindo a atribuição de propriedade ou responsabilidade. |
| Booleano | Armazena valores verdadeiro/falso, usados para alternâncias ou indicadores binários (por exemplo, ativo/inativo, sim/não). |
| Link | Armazena URLs clicáveis que abrem em uma nova guia do navegador. Útil para referenciar recursos externos, como tickets do Jira, documentação ou painéis. |

**[Esquema](manage_schema.html "Os esquemas definem a estrutura dos dados no Apptio Planning. Eles especificam as tabelas, os campos e os relacionamentos que determinam como as informações são armazenadas, vinculadas e exibidas nas guias Despesas, como Trabalho, Contratos, Ativos e Finanças.")**

Um **Schema** define a estrutura de dados no Apptio Planning, incluindo tabelas, campos e relacionamentos. Ele determina como as informações são armazenadas, vinculadas e exibidas em tabelas de itens de linha.

Quando uma dimensão corresponder aos tipos de esquema (Trabalho, Contratos, Ativos, Atividade de trabalho, Dados reais e o esquema Financeiro), esse campo será automaticamente acumulado e exibido na guia Resumo.

**Tipos de itens de linha**

**Os tipos de itens** definem o tipo de dados que estão sendo planejados, rastreados ou relatados no Apptio Planning. Cada tipo está alinhado a um módulo ou função específica:

- **Itens financeiros** - Capturam despesas operacionais ( OpEx ) ou de capital ( CapEx ); aparecem nas guias Resumo e Outros.
- **Itens de linha de mão** de obra - Representam o número de funcionários e os custos de mão de obra; gerenciados na guia Mão de obra.
- **Itens de contrato** - Acompanhe os acordos com fornecedores e os custos associados; gerenciados na guia Contrato.
- **Itens de linha de ativos** - Registram as compras e a depreciação de ativos; gerenciados na guia Ativo.
- **Itens de linha de atividade de mão** de obra - Capturam o esforço de mão de obra do projeto (horas) e cobranças cruzadas; gerenciados na guia Atividade de mão de obra.
- **Reais** - Representam transações financeiras reais; são usados no Gerenciamento de despesas e orientam as regras de compactação reais.

**[Regras de alocação de mão de obra](manage-labor-allocation-rules.html)**

**As regras de alocação** de mão de obra definem como os custos de mão de obra são distribuídos entre diferentes contas financeiras. Eles são usados para gerar custos de mão de obra para várias contas do Razão, garantindo que o custo total de cada funcionário (incluindo salário, benefícios e custos indiretos) seja representado com precisão no planejamento e nos relatórios financeiros.
