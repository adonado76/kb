---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Lançamentos recentes"
breadcrumb:
  - "Planning"
  - "Notas sobre a liberação"
source_path: "it-planning/whats-new.html"
images:
  - "resources/images/it_planning_images/5.25itp.png"
  - "resources/images/it_planning_images/5.26-a.png"
  - "resources/images/it_planning_images/5.26b.png"
  - "resources/images/it_planning_images/5.26c.png"
  - "resources/images/it_planning_images/518-rn.png"
  - "resources/images/it_planning_images/append-li.png"
  - "resources/images/it_planning_images/imp-layout-1.png"
  - "resources/images/it_planning_images/imp-layout-2.png"
  - "resources/images/it_planning_images/release-notes/516-io.png"
  - "resources/images/it_planning_images/release-notes/516-other.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Lançamentos recentes

## Lançamento de “ 5.26 ” – Sandbox: 22 a 26 de junho de 2026 | Principal: 29 de junho a 3 de julho de 2026

**API REST para importação assíncrona de dados de despesas**

- O endpoint **POST** inicia uma importação assíncrona de dados de despesas no formato “ CSV ” para um Plano especificado e retorna um identificador único de importação.
- O endpoint **GET** recupera o status atual da operação de importação usando o identificador de importação fornecido.

Essa melhoria permite que as organizações automatizem e dimensionem com eficiência a importação de dados de despesas, especialmente no caso de atualizações frequentes ou de grande volume.

Para saber mais, acesse [Plan APIs](planning/plan-data-api.html#plndataapi__async).

**Suporte a moedas para a API REST de exportação de planos**

A API REST de exportação do Plan foi aprimorada para permitir a seleção da moeda durante a exportação de dados.

Exporte os dados do plano em:

- **Moeda original** (padrão) – Exporta os dados financeiros na mesma moeda especificada para cada item, sem que seja aplicada nenhuma conversão de moeda.
- **Moeda da empresa** – Exporta dados financeiros na moeda padrão da empresa. Todos os valores monetários são convertidos automaticamente utilizando as taxas de câmbio aplicáveis.

Essa melhoria oferece maior flexibilidade para a elaboração de relatórios e análises em planos multimoeda. Para saber mais, acesse [Plan APIs](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=overview-plan-apis#plndataapi__title__3 "(Abre em uma nova guia ou janela)").

**Distribuição de valores com base em dias corridos para outras despesas**

A distribuição mensal dos valores na categoria **Despesas > Outros** agora pode ser baseada no número de dias do calendário de cada mês.

**Ferramentas Importantes**

- Os administradores podem configurar **“Dias do calendário”** como o método padrão de distribuição nas configurações **do Perfil da empresa**.
- Quando ativada, os valores inseridos nas colunas **trimestrais** ou **anuais** são distribuídos automaticamente pelos meses com base no número de dias do calendário de cada mês.
- Os usuários podem substituir o método padrão de distribuição no nível da **tabela “Despesas”** e escolher entre:
  - **Distribuição uniforme**
  - **Diferença em dias corridos**

Isso proporciona maior flexibilidade e melhora a precisão da alocação de despesas ao longo dos períodos de relatório.

![configuração da distribuição de dados no perfil da empresa](../../../../03-media/apptio-planning/resources/images/it_planning_images/5.26-a.png)

![configuração de distribuição de dados na página de despesas](../../../../03-media/apptio-planning/resources/images/it_planning_images/5.26b.png)

![opções de configuração da distribuição de dados](../../../../03-media/apptio-planning/resources/images/it_planning_images/5.26c.png)

**Correções de bugs**

- Corrigimos problemas de visibilidade nas listas suspensas “Versões do Plano” e “Fatores de Variação” para grupos folha de um único departamento, garantindo a exibição correta e o acesso com base em permissões.
- Corrigimos um problema na guia “Resumo” em que, ao detalhar o gráfico “Cascata de gastos” durante a comparação de planos, era exibida uma janela pop-up em branco com o erro “ E10000 ”. Agora, os usuários podem detalhar com sucesso os gráficos em cascata ao comparar planos de previsão com planos orçamentários, e a janela pop-up de comparação exibe os itens de linha corretamente.
- Corrigimos um problema na visualização “Novas despesas” em que a linha “Total” desaparecia ao adicionar uma comparação de planos.
- Corrigimos um problema na visualização “Novas despesas” em que a coluna “Acumulado no ano (YTD)” desaparecia quando o exercício fiscal a que ela se referia era desmarcado em “Grupos de datas”.
- Corrigimos um problema na guia “Mão de obra” em que os campos de lista de seleção dependentes (como o Código do Centro de Custo) não eram preenchidos automaticamente ao adicionar novas linhas, a menos que a página fosse atualizada.
- Corrigimos um problema em que as permissões do usuário não podiam ser salvas nas Configurações do Plano quando o Nome do Departamento não estava definido nos dados de referência do Departamento.

## Lançamento do Sandbox de " 5.25: ": 8 a 12 de junho de 2026 | Lançamento principal: 15 a 19 de junho de 2026

**Regras de alocação de mão de obra com base no tempo no nível do plano**

Agora é possível definir **regras de alocação de mão de obra** **com** base no tempo no nível do plano, permitindo uma modelagem mais flexível dos custos totais de mão de obra em planos plurianuais. Isso permite aplicar diferentes valores de regras ao longo do tempo — como **benefícios, bônus, treinamento e outros componentes de custo** — sem afetar os dados de referência globais.

**Principais recursos**

- Ampliar **as regras globais de alocação de mão de obra** com **prazos de vigência** **específicos para cada plano**
- Defina os valores **de “Válido a partir de”** para controlar quando as alterações nas regras entram em vigor
- Aplicar automaticamente a regra correta durante a geração dos custos de mão de obra com base no período relevante

Essa melhoria permite um planejamento de custos de mão de obra mais preciso e baseado em cenários, com premissas que podem ser ajustadas ao longo do tempo.

Para saber mais, consulte [as Regras de alocação de mão de obra com base no tempo efetivo](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-labor-allocation-rules#laballrul__title__6 "(Abre em uma nova guia ou janela)").

**Permissões de objeto de custo transferidas para dados de referência**

**A página “Permissões do objeto** de custo” está agora disponível como uma guia na seção **“Dados de referência”**, reunindo o gerenciamento de permissões e os elementos de configuração relacionados em um único local unificado.

![imagem das permissões do objeto de custo](../../../../03-media/apptio-planning/resources/images/it_planning_images/5.25itp.png)

**Correções de bugs**

- Corrigimos um problema em que as opções “Inserir linha acima” e “Inserir linha abaixo” não apareciam ao clicar com o botão direito do mouse nas linhas da tabela de permissões do objeto de custo. Essas opções de inserção de linhas agora são exibidas corretamente, permitindo que os usuários adicionem novas linhas de permissão conforme necessário.
- Corrigimos um problema na visualização “Despesas Anteriores” em que a seleção ou desmarcação das colunas de data (Mês, Total do Exercício Fiscal, Acumulado no Ano, Trimestres) através do menu “Mostrar/Ocultar Colunas” não funcionava. Agora, os usuários podem exibir e ocultar essas colunas relacionadas ao período, e o botão “Selecionar tudo” funciona corretamente para adicionar todas as colunas disponíveis ao relatório.
- Foi aprimorada a guia “Dados Reais” da Análise de Variação para que ela seja preenchida automaticamente com o último período que contenha dados reais dentro do intervalo de datas configurado, em vez de ser preenchida automaticamente com o último período de todo o intervalo. Isso garante que os usuários vejam, por padrão, dados reais relevantes ao analisar variações, eliminando a necessidade de selecionar manualmente o período correto.
- Corrigimos um problema em que a existência de várias entradas de dados de referência com nomes idênticos, mas códigos diferentes (como categorias de conta), causava um comportamento incorreto de agrupamento e filtragem nos painéis. Ao agrupar por nome, todos os itens de linha associados agora são exibidos corretamente, e ao expandir as linhas agrupadas, todos os dados relevantes são exibidos, em vez de apenas uma parte deles.
- Corrigimos um problema em que as colunas do menu suspenso afetadas pelos filtros de linha de item exibiam apenas o valor “Nome”, em vez do formato esperado “Código - Nome”. Agora, os menus suspensos exibem de forma consistente a combinação de Nome de código em todas as colunas, independentemente da aplicação de filtros de itens de linha, garantindo uma apresentação uniforme dos dados em toda a aplicação.
- Corrigimos um problema na visualização “Nova Despesa” em que os filtros não eram salvos nos layouts. Agora, os filtros são mantidos corretamente ao salvar layouts, garantindo que as preferências de filtragem dos usuários sejam preservadas entre as sessões.
- Corrigimos um problema em que valores de listas personalizadas contendo espaços à direita faziam com que o agrupamento, a filtragem e a expansão falhassem. O sistema agora lida corretamente com valores que contêm espaços extras, garantindo que as linhas agrupadas possam ser expandidas e filtradas corretamente, sem exibir erros do tipo “Sem resultados”.

## Lançamento de “ 5.24 ” – Sandbox: 25 a 29 de maio de 2026 | Principal: 1 a 5 de junho de 2026

Versão de manutenção

Esta versão contém atualizações de manutenção do sistema e correções de bugs.

Correções de bugs

- Corrigimos um problema em que o campo **“Horas de trabalho por dia”** ficava desativado ao criar ou editar calendários de trabalho, mesmo com **o Planejamento Integrado de Investimentos** ativado. Agora, os usuários podem atualizar o horário de trabalho conforme o esperado, para um planejamento preciso da mão de obra.
- Corrigimos um problema em que o agrupamento de colunas removido na tela **Despesas (Nova Visualização)** era automaticamente reaplicado após uma atualização. As alterações no layout agora são mantidas corretamente, sem reintroduzir os agrupamentos removidos.
- Corrigimos um problema em que os KPIs exibiam a moeda incorreta quando vários objetos de custo eram selecionados na visualização “**Moeda: Original** ”. Agora, as agregações utilizam **a moeda do objeto de custo** quando todos os objetos de custo selecionados compartilham a mesma moeda, e adotam **a moeda da empresa** como padrão apenas quando as moedas são diferentes.
- Corrigimos um problema em que **os dados de comparação não eram incluídos** ao exportar usando a opção “Exportar layout” nas guias **“Contratos”** e “**Ativos** ”. As exportações agora incluem corretamente colunas de comparação, em consonância com outras guias de despesas.
- Corrigimos um problema em que as atualizações na página **"Metas"** não eram refletidas imediatamente e exigiam uma atualização da página. As alterações agora aparecem instantaneamente, garantindo uma visualização consistente e precisa sem a necessidade de atualização manual.
- Corrigimos um problema que fazia com que os usuários encontrassem erros ao importar dados para a guia “**Contratos** ”. As importações agora são concluídas com sucesso após a validação adequada, garantindo um fluxo de trabalho mais tranquilo durante as atualizações de planejamento.
- A ação **“Atualizar dados reais”** passou a se chamar **“Atualizar dados financeiros reais”** em todas as guias da página **Despesas**. Essa atualização na nomenclatura também se reflete na caixa de diálogo e **no Histórico de Alterações**, proporcionando uma terminologia mais clara e consistente.
- Corrigimos um problema em que os usuários recém-criados não apareciam imediatamente nas **permissões do plano** e **nas permissões do objeto de custo**. Os usuários agora aparecem corretamente, permitindo que as permissões sejam atribuídas sem demora.
- Corrigimos um problema na Lista de Projetos do Planejamento Financeiro de Projetos (PFP), em que a seleção de um arquivo na caixa de diálogo “Importar Projetos” não acionava o upload nem ativava a ação de importação. A seleção e a importação de arquivos agora funcionam conforme o esperado, garantindo o envio ininterrupto dos dados do projeto.

## Lançamento de “ 5.23 ” – Sandbox: 11 a 15 de maio de 2026 | Principal: 18 a 22 de maio de 2026

**Identificação de valores reais nos planos de previsão**

- Nos planos de previsão, as linhas que incluem valores reais passam **a** ser automaticamente identificadas com o tipo de linha “Valores reais”, enquanto as linhas de previsão permanecem inalteradas.
- Isso permite a geração de relatórios mais claros e análises mais precisas ao agrupar, filtrar ou comparar dados por **tipo** **de item de linha**.

**Melhoria no tratamento de prorrogações para contratos baseados em prazo**

- As prorrogações de contratos agora são aplicadas com maior precisão para contratos que utilizam os métodos de amortização **“Linha reta por duração”** e “**Calendário personalizado de duração linear** ”.
- Uma nova opção **de “Deslocamento da prorrogação”** permite definir se uma prorrogação terá início no **dia** seguinte ou no **mês seguinte**, evitando datas de renovação desalinhadas e amortizações incorretas — especialmente em contratos com vigência anual e em anos bissextos.
- Isso garante que as prorrogações de contratos se alinhem perfeitamente aos períodos fiscais e às expectativas dos usuários.

**Métodos de alocação de mão de obra por período fixo**

Agora estão disponíveis dois novos métodos de amortização para **as Regras de Alocação de Mão de Obra**, permitindo a distribuição de custos com base em **índices de períodos fixos**.

- **Método linear com base no número de dias do calendário** : distribui os custos com base no número de dias do calendário em cada período fiscal em relação ao ano fiscal completo, sem ratear as datas de início ou término do contrato de trabalho.
- **Método linear com período fixo de dias úteis** : distribui os custos com base nos dias úteis de cada período fiscal, utilizando o calendário de trabalho configurado, sem ratear as datas de início ou término do contrato de trabalho. Volta à distribuição uniforme por período quando os calendários de trabalho são fixos.

**Descrições específicas do plano no cabeçalho do plano**

- Os administradores e os responsáveis pelo processo orçamentário agora podem adicionar uma **descrição** **específica do plano** para fornecer contexto, orientações ou premissas-chave usando o campo **“Descrição”** na caixa de diálogo “**Editar plano** ”.
- A descrição aparece no **cabeçalho** do plano, facilitando o acesso a informações importantes enquanto se trabalha no plano. Os usuários podem mostrar ou ocultar a descrição a qualquer momento usando o **ícone de sino** no cabeçalho do plano.

**Exibir intervalos de datas no período de despesas (nova visualização)**

- Os administradores agora podem ativar a configuração **“Mostrar intervalos de datas do período”** no **Perfil** da empresa para exibir as datas de início e término de cada período na tabela Despesas (Nova visualização).
- Quando ativada, os intervalos de datas dos períodos seguem o calendário fiscal da empresa e respeitam as configurações regionais do usuário para a formatação de datas, proporcionando um contexto temporal mais claro na tabela.

**Correções de bugs**

- Corrigimos um problema que impedia os usuários de editar notas de fatores de variação quando havia alterações não publicadas nos dados de referência da categoria de conta. A edição agora funciona corretamente sem que seja necessário publicar essas alterações.
- Corrigimos um problema na tela **Despesas (Nova Visualização)** em que a expansão das linhas de um plano de comparação causava um erro. Agora, as linhas se expandem corretamente, permitindo que os usuários visualizem dados detalhados sem interrupções.
- Corrigimos um problema em que a configuração **da Análise de Variação** exibia um erro quando **as Resumos de Mão de Obra** estavam desativadas. A configuração agora funciona conforme o esperado, sem a necessidade de ativar essa opção.
- Corrigimos um problema em que a inserção de valores na **coluna** “Exercício Fiscal” enquanto **as colunas dos trimestres estavam ocultas** resultava em uma distribuição incorreta pelos meses e em totais trimestrais imprecisos. Os cálculos de períodos agora são alinhados corretamente entre os totais mensais, trimestrais e anuais.
- Os dados comparativos na **tabela** “Despesas” agora são diferenciados visualmente, com colunas agrupadas e um leve destaque no fundo. Isso facilita a distinção entre os dados comparativos e o plano base.

## Lançamento de “ 5.22 ” – Sandbox: 27 de abril a 1º de maio de 2026 | Principal: 4 a 8 de maio de 2026

**Comparações entre períodos nas despesas (nova visualização)**

Agora você pode comparar períodos dentro do mesmo plano — ano a ano, trimestre a trimestre ou mês a mês — diretamente em **Despesas > Nova Visualização**, facilitando a análise de tendências e mudanças ao longo do tempo.

**Principais recursos**

- Compare **anos, trimestres ou meses** com base no período selecionado
- Visualizar e ordenar por **variação absoluta ou percentual**
- Disponível em todas as guias que suportam comparações entre planos, com o mesmo comportamento padrão de agrupamento

Para saber mais, consulte “[Comparação entre períodos](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=plans-compare-versions#Compareversionsorplans__title__2 "(Abre em uma nova guia ou janela)") ”.

**Restaurar o orçamento do departamento à versão anterior**

**Os responsáveis pelos centros de custo** agora podem restaurar um instantâneo anterior e defini-lo como a versão atual dos dados do plano para seu departamento. Isso facilita a recuperação de alterações indesejadas e permite continuar o planejamento a partir de um ponto no tempo conhecido e confiável.

**Principais recursos**

- Restaurar um instantâneo anterior para um departamento específico, caso o usuário tenha acesso de edição ao departamento
- Disponível quando o plano está no estado “Aberto” e o departamento está no estado “Em andamento”.
- O Tracks registra as ações no Histórico de Alterações para garantir total visibilidade e rastreabilidade

Para saber mais, consulte “[Restaurar instantâneo](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=collaboration-snapshots-versioning#snapshot__title__6 "(Abre em uma nova guia ou janela)") ”.

**Modernização da interface do usuário de permissões de objeto de custo**

A tela **“Permissões de objeto de custo/departamento”** foi modernizada para se alinhar à **experiência de usuário unificada** do Apptio, mantendo o comportamento e os fluxos de trabalho existentes.

**Principais recursos**

- Experiência consistente na gestão de permissões, alinhada com a experiência de usuário unificada do Apptio e com os padrões de grade corporativa
- Suporte completo para **edição direta**, importação e exportação
- As visualizações em lista e hierárquica, a visibilidade das colunas e o acesso baseado em funções funcionam como antes

**Publicar permissões de objeto de custo nos planos**

Com **as permissões de usuário no nível do plano** ativadas, os administradores e os responsáveis pelo processo orçamentário agora podem publicar **permissões globais de objeto de custo** diretamente nos planos selecionados. Isso simplifica o gerenciamento centralizado de permissões e mantém vários planos alinhados sem a necessidade de intervenção manual.

**Principais recursos**

- Aplicar permissões globais a **um, vários ou todos os planos**, incluindo planos arquivados
- Controle como as permissões são aplicadas usando **“Atualizar permissões”** ou **“Substituir todas as permissões”**

Para saber mais, acesse [“Publicar permissões globais para planos”](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=administration-cost-object-permissions#cop__title__6 "(Abre em uma nova guia ou janela)")

**Correções de bugs**

- Corrigimos um problema em que a coluna **“Total”** na guia **“Mão de obra”** exibia valores incorretos durante comparações de planos entre exercícios fiscais. Os totais agora refletem corretamente os valores do plano de comparação, permitindo uma análise precisa.
- Corrigimos um problema em que a coluna **“Acumulado no ano”** na **Atividade de mão de obra (modo Horas)** exibia uma média em vez de uma soma. Os valores acumulados no ano agora são calculados corretamente como **soma,** tanto para linhas agrupadas quanto para linhas não agrupadas.
- Corrigimos um problema em que a **página "Resumo de despesas"** não carregava para usuários sem acesso a colunas confidenciais após a exclusão de um atributo confidencial. A página agora carrega corretamente, sem erros.
- Corrigimos um problema em que usuários sem acesso a **“Todos os Departamentos”** viam seleções padrão incorretas e não conseguiam expandir os projetos no menu suspenso “**Projeto** ”. O menu suspenso agora reflete corretamente as permissões do usuário e permite a navegação normal.

## Lançamento de “ 5.21 ” – Sandbox: 14 a 17 de abril de 2026 | Principal: 20 a 24 de abril de 2026

**API de exportação do histórico de alterações**

**Exportar registros do histórico de alterações:** O endpoint POST permite que os usuários exportem os registros de eventos do histórico de alterações como um arquivo do tipo ` CSV `, com base nos filtros aplicados.

Para saber mais, acesse [a Visão geral das APIs REST de planejamento](planning/plan-api.html "As APIs REST do Planning do Apptio oferecem acesso programático e seguro a planos, dados de planejamento, metadados e artefatos relacionados no Planning d Apptio. Essas APIs foram projetadas para oferecer suporte à automação e às integrações de sistemas em casos de uso relacionados a planejamento, previsão, análise, governança e troca de dados.").

**Importar atividades de mão de obra por código externo de recurso**

Agora você pode planejar e importar atividades de mão de obra usando **o Código Externo de Recurso** (como o ID do funcionário), simplificando as integrações de planejamento de mão de obra com sistemas externos de RH.

- **Planeje as linhas de produção utilizando códigos externos de recursos exclusivos**

  Defina e gerencie os recursos humanos utilizando um identificador externo fixo (por exemplo, o número de identificação do funcionário).
- **Importar alocações de atividades de mão de obra por ID do funcionário**

  As importações de atividades de mão de obra agora determinam os recursos usando **o código externo de recursos**.

Observação: É necessário que o recurso **"Código Externo"** esteja ativado.

Para saber mais, acesse “[Códigos externos](planning/external-unique-identifier.html "Ao importar ou atualizar dados de despesas (por exemplo, mão de obra, atividades de mão de obra, contratos, ativos) de sistemas externos (sistemas de RH, bancos de dados de fornecedores, etc.), Você precisa de um identificador único e consistente para associar as linhas do seu plano aos registros no sistema de origem.") ” e “[Importar atividade de mão de obra por código externo](planning/iip/unique-labor-resource-identification.html) ”

**Melhoria no alinhamento do código externo no resumo de despesas**

- Quando **o Código Externo** é utilizado como um identificador único definido pelo usuário nas linhas de despesas, os dados financeiros gerados a partir dessas linhas (Mão de obra, Contratos, Ativos e Atividade de mão de obra) são resumidos na coluna **Código Externo** na guia **Despesas > Resumo**. Isso facilita o alinhamento das linhas de previsão e real usando o mesmo código externo.
- Anteriormente, **o Código Externo** dos dados financeiros gerados aparecia apenas na coluna “Código Externo de Origem”, o que dificultava a comparação entre as previsões e os resultados reais por Código Externo.

Observação: É necessário que o recurso **"Código Externo"** esteja ativado.

Para saber mais, acesse [Códigos Externos](planning/external-unique-identifier.html "Ao importar ou atualizar dados de despesas (por exemplo, mão de obra, atividades de mão de obra, contratos, ativos) de sistemas externos (sistemas de RH, bancos de dados de fornecedores, etc.), Você precisa de um identificador único e consistente para associar as linhas do seu plano aos registros no sistema de origem.").

**Atualização da navegação pelos dados de referência**

**As regras de alocação de mão de obra** e **os filtros de itens individuais** foram reorganizados em guias separadas na seção **“Dados de referência”** da barra de navegação à esquerda. Isso reúne **os dados de referência** em um único local centralizado, facilitando a localização e o gerenciamento das dimensões relacionadas.

**Correções de bugs**

- Atualizamos a lista suspensa de opções na nova visualização de Despesas para ajustar dinamicamente sua largura de acordo com o comprimento do conteúdo, garantindo que todos os valores fiquem totalmente visíveis, sem serem cortados.
- Corrigimos o menu suspenso de navegação do projeto para que ele exiba corretamente o projeto pai de nível superior quando vários projetos em diferentes níveis hierárquicos estiverem selecionados. Em vez de exibir “Todos os projetos”, o cabeçalho agora mostra o pai de nível mais alto, oferecendo um contexto mais preciso e significativo.
- Corrigimos um problema na página "Metas" em que a seleção de um departamento com um único subdepartamento independente fazia com que o departamento pai fosse ocultado, impedindo a edição de sua meta. O menu suspenso agora exibe corretamente o departamento superior, permitindo que os valores-alvo sejam visualizados e atualizados conforme o esperado.
- Corrigimos um problema na nova visualização de Despesas em que as colunas fixadas voltavam à sua posição original quando reordenadas pela primeira vez. Agora, as colunas fixadas podem ser reordenadas corretamente e mantêm sua nova posição, conforme esperado.
- Corrigimos um problema na nova visualização de despesas em que usuários sem a permissão “ EditExternalLine ” podiam duplicar itens de linha externos. O sistema agora aplica corretamente as permissões, impedindo a duplicação para usuários sem o acesso necessário.
- Corrigimos um problema em que os atributos pai (gerados) eram exibidos incorretamente na tabela “Outros”. Esses atributos estão agora restritos à tabela Resumo, conforme pretendido, e não aparecem mais na tabela Outros.

## Lançamento de “ 5.20 ” – Sandbox: 30 de março a 3 de abril de 2026 | Principal: 6 a 10 de abril de 2026

**APIs REST para gestão de despesas e layout de tabela**

Nesta versão, introduzimos as seguintes novas APIs REST.

- **Exportar dados do Spend Management:** O endpoint POST exporta dados reais do Spend Management
- **Importar dados para o Spend Management:** O endpoint POST importa dados reais para o Spend Management
- **Arquivo de ajuda sobre erros de importação do Spend Management:** O endpoint GET exporta um arquivo de ajuda no formato CSV que contém erros de importação de dados do Spend Management, permitindo que os usuários analisem e resolvam falhas de importação.
- **Layouts de tabelas de exportação:** O endpoint GET exporta todos os layouts de tabelas aos quais o usuário tem acesso.
- **Exportar dados do plano por layout:** O endpoint Post para exportação de dados do plano foi aprimorado para oferecer suporte a um novo parâmetro, **layoutId**, que permite exportar dados do plano em um formato de layout específico.

**Resumo de despesas aprimorado com contexto da linha de origem**

Agora você pode visualizar atributos detalhados de itens de origem, como Contratos, Ativos, Mão de obra e Atividades de mão de obra, diretamente nos relatórios financeiros gerados na guia Resumo de despesas. Essa melhoria oferece maior transparência, contexto e rastreabilidade, ajudando você a analisar e compreender melhor os gastos.

- **Contexto de dados mais rico:** os dados financeiros agora incluem atributos adicionais, como detalhes do contrato, propriedades dos ativos e informações sobre recursos.
- **Rastreabilidade da fonte até o dado financeiro:** rastreie facilmente os dados financeiros gerados até a partida individual de origem usando atributos adicionais na guia “Resumo”.
- **Suporte ao layout:** as colunas de atributos recém-adicionadas ficam ocultas por padrão, mas podem ser ativadas, salvas e exportadas por meio das opções de exportação de dados **“Exportar layout”** ou “**Exportar tudo** ”.

A lista dos atributos de resumo recém-adicionados para os tipos de despesas compatíveis é apresentada a seguir.

**Guia Contratos**

|  |  |
| --- | --- |
| **Nome do atributo na guia Contrato** | **Nome do atributo mapeado na guia Resumo** |
| Quantia | Valor do contrato |
| Data de Início | Data de início do contrato |
| Data de Término | Data de término do contrato |
| Método de amortização do contrato | Método de amortização do contrato |
| Alíquota do IVA | Alíquota de IVA do contrato |
| Valor com IVA | Valor do contrato com IVA |

**Guia "Ativos"**

|  |  |
| --- | --- |
| **Nome do atributo na guia "Ativos"** | **Nome do atributo mapeado na guia Resumo** |
| Classe de ativos | Classe de ativos |
| Vida útil do ativo (meses) | Vida útil do ativo (meses) |
| Valor residual (%) | Valor residual do ativo (%) |
| Taxa de saldo (%) | Taxa de equilíbrio de ativos (%) |
| Método de depreciação de ativos | Método de depreciação de ativos |
| Preço de compra | Preço de compra do ativo |
| Data de entrada em serviço | Data de entrada em serviço do ativo |
| Quantidade | Quantidade de ativos |
| É um ativo existente | É um ativo existente |

**Guia "Trabalho"**

|  |  |
| --- | --- |
| **Nome do atributo na guia "Trabalho"** | **Nome do atributo mapeado na guia Resumo** |
| Nome do funcionário | Recurso |
| Função | Função do recurso |
| Função no projeto | Função do recurso |
| Tipo de funcionário | Tipo de funcionário |
| Quantidade | Quantidade de recursos |
| Data de Início | Data de início do recurso |
| Data de Término | Data de término do recurso |
| É um funcionário atual | É um funcionário atual |

**Guia "Atividade Laboral"**

|  |  |
| --- | --- |
| **Nome do atributo na guia "Trabalho"** | **Nome do atributo mapeado na guia Resumo** |
| Centro de Custos de Recursos | Centro de Custos de Recursos |
| Função do recurso | Função no projeto |
| Tipo de atividade | Tipo de atividade do recurso |

Interpretação das permissões do usuário para comparação de planos

Quando o recurso “Permissões de objeto de custo por nível de plano” está ativado, as permissões são aplicadas da seguinte forma durante a comparação de planos:

- **Dados de despesas** : os dados comparativos são exibidos de acordo com as permissões do usuário no plano de origem.
- **Dados sensíveis relativos à mão de obra** : as colunas e os dados financeiros sensíveis relativos à mão de obra só ficam visíveis se o usuário tiver acesso a todos os planos comparados.
- **Detalhes da análise de variação** : A análise de variação é exibida de acordo com as permissões do usuário no plano de origem.

**Correções de bugs**

- Corrigimos um problema em que os usuários continuavam sendo redirecionados para o último plano acessado, mesmo após ele ter sido excluído por um administrador, o que fazia com que fossem direcionados a um plano com exclusão temporária ao fazer login.
- Foi corrigido um problema que fazia com que a definição da Data de Término do Contrato para além do ano de 2045 resultasse em um erro.
- Corrigimos um problema em que o gráfico em cascata da Análise de Variação era exibido por padrão para o último mês do ano; agora, ele é exibido corretamente por padrão para o último mês do período de comparação selecionado.
- Corrigimos um problema para garantir que usuários sem a permissão *“ ExternalLineEdit ”* não possam excluir linhas externas.
- Corrigimos um problema em que os cálculos das despesas com mão de obra não respeitavam as horas diárias configuradas no calendário. Os cálculos agora utilizam corretamente o horário de trabalho definido, incluindo cenários de início do trabalho no meio do período e regras de alocação baseadas no dia útil.

## Lançamento de “ 5.19 ” – Sandbox: 16 a 20 de março de 2026 | Principal: 23 a 27 de março de 2026

**Previsão inteligente**

Ampliamos **o Intelligent Forecasting** para incluir mão de obra, atividade de mão de obra (horas), contratos e ativos, possibilitando previsões mais abrangentes baseadas em IA em todo o processo de planejamento.

**Trabalho e atividade laboral**

- A previsão preditiva já está disponível nas guias “Mão de obra” e “Atividade de mão de obra (horas)”.
- As visualizações das previsões mostram as unidades corretas: número de funcionários para a mão de obra e horas para a atividade de mão de obra.
- A aplicação das previsões atualiza automaticamente os dados financeiros relativos à mão de obra e às atividades laborais.

**Contratos e ativos**

- A função de previsão agora oferece suporte a contratos de amortização manual e ativos de depreciação manual.
- A previsão para linhas de contrato e ativos não suportadas está desativada.
- A aplicação das previsões gera dados financeiros atualizados tanto para os contratos quanto para os ativos.

Essas melhorias levam as previsões baseadas em IA a mais etapas do fluxo de trabalho de planejamento, ajudando os usuários a criar previsões mais rápidas, precisas e consistentes, com menos trabalho manual no planejamento de mão de obra, atividades, contratos e ativos.

**Exclusão em massa de permissões de usuário**

Ao gerenciar as permissões de usuário no nível do plano, os administradores e os usuários do BPO agora podem remover rapidamente as permissões de um usuário em todos os planos. Uma nova opção **“Excluir permissão de todos os planos”** fica disponível quando uma ou mais linhas de permissão são selecionadas.

Ação de exclusão em massa:

- Remove a permissão selecionada de todos os planos (Novo, Aberto, Final e Arquivado).
- Remove a permissão dos dados de referência de Permissões de objeto de custo.

**KPIs sensíveis a filtros em gráficos de resumo**

- Os KPIs na página Resumo (Finanças e Quadro de Funcionários) agora são atualizados automaticamente com base nos filtros aplicados.
- Essa melhoria garante que os valores dos KPIs reflitam sempre o mesmo conjunto de dados filtrado dos gráficos subjacentes, proporcionando informações consistentes e precisas em toda a visualização de resumo.

**Resumir as informações financeiras relativas à mão de obra por nome do funcionário**

- Agora você pode resumir os dados financeiros relativos à mão de obra por nome do funcionário na visualização Despesas > Resumo.
- Esta atualização ajuda você a analisar melhor o custo total de mão de obra por recurso. Isso pode ser ativado nas configurações de Resumo de mão de obra.

**APIs REST para permissões de usuário**

Implementamos APIs REST que permitem a importação e exportação programática de dados de permissão do usuário no Apptio Planning.

As principais funcionalidades incluem

- **Importar dados de permissão:** O endpoint POST importa dados do plano relativos às permissões de usuário ou às permissões globais de objeto de custo.
- **Arquivo de ajuda sobre erros de importação de permissões de exportação:** O endpoint GET exporta um arquivo de ajuda no formato CSV que contém erros de importação de dados de permissão, permitindo que os usuários analisem e resolvam falhas de importação.
- **Dados de permissão de exportação:** O endpoint POST exporta permissões de usuário ou permissões globais de objeto de custo.

**Correções de bugs**

- Corrigimos um problema em que os campos personalizados de mão de obra renomeados não apareciam na lista de atributos da síntese de mão de obra. Os campos renomeados agora são exibidos corretamente no Perfil da Empresa e no Resumo.
- Melhoramos o menu suspenso “Projeto” para que ele reflita com precisão os projetos selecionados — exibindo o nome do projeto em seleções únicas e o grupo de projetos apropriado com a contagem de seleções em seleções múltiplas ou hierárquicas —, agora de forma consistente com o menu suspenso “Departamento”.
- Corrigimos um problema em que a opção “Enviar todas as alterações e finalizar” apresentava um erro inesperado. A finalização agora é concluída sem interrupções.
- Corrigimos um problema que impedia a criação de um novo atributo de hiperlink após a exclusão de um atributo anterior.
- Foi resolvido um problema que ocorria durante a criação de planos e a atualização de dados reais, em que podiam surgir dados reais duplicados quando a compactação era feita por atributos não suportados.
- Corrigimos um problema que impedia a atualização dos dados reais nos planos de previsão com mais de um ano de dados históricos.
- Melhoramos a filtragem por departamento nas Permissões do Usuário para que as pesquisas por código, nome ou ambos retornem resultados corretos.
- Corrigimos um problema em que os planos orçamentários não podiam ser excluídos após a remoção do plano de previsão relacionado na Análise de Variação.
- Corrigimos um problema em que salvar e atualizar um layout fazia com que um layout duplicado fosse exibido.
- Corrigimos um problema na seção Despesas → Nova visualização, em que layouts excluídos permaneciam visíveis até que a página fosse atualizada.
- Corrigimos um problema em que a integração de cálculo de custos publicava nomes de colunas incorretos devido a metadados desatualizados.

## Lançamento 5.18 Sandbox: 2 a 6 de março de 2026 | Principal: 9 a 13 de março de 2026

**Controle configurável para permissões no nível do plano**

Agora você pode ativar ou desativar **as Permissões de Usuário no Nível do Plano** em **Perfil da Empresa → Configuração Geral**, o que lhe dá flexibilidade para gerenciar o acesso da maneira que melhor se adapta à sua organização.

- Use **permissões globais de objeto de custo** para controle centralizado
- Ou habilite **permissões no nível do plano** para um gerenciamento de acesso mais granular

Para ativar ou desativar as permissões de usuário no nível do plano:

1. Navegue até **Configurações** **(ícone de engrenagem)** → **Perfil da empresa**.
2. Selecione **Configuração Geral → Acesso e Permissões**
3. Use a configuração da caixa de seleção **Ativar permissões de objeto de custo no nível do plano** para ativar ou desativar o recurso.

**Suporte ampliado ao calendário fiscal para integração com o Cloudability Financial Planning**

Apptio O planejamento agora oferece suporte à integração com o CFP ( Cloudability Financial Planning, **ou ano fiscal de início** flexível) para organizações que utilizam calendários gregorianos com meses de início do ano fiscal diferentes de janeiro.

**Importação aprimorada de itens de linha filtrados**

Esta atualização melhora a forma como você substitui seletivamente os dados ao importar itens de linha, proporcionando um controle mais preciso ao usar **a opção Substituir todos os dados com filtro de dimensão**.

1. **As dimensões personalizadas** e **as listas personalizadas** agora são compatíveis com a filtragem por dimensão
2. Os filtros de dimensão e valor agora são exibidos em um formato claro **<código> – <nome>** para facilitar a seleção

**Exibição personalizável da coluna Período**

Esta melhoria oferece maior flexibilidade na forma como as colunas de período são exibidas na **Nova Visualização** de Despesas

- Ative ou desative colunas **mensais** e **trimestrais** independentemente para cada ano
- Salve as configurações como **layouts de tabela reutilizáveis**

![imagem de colunas de período personalizáveis](../../../../03-media/apptio-planning/resources/images/it_planning_images/518-rn.png)

**API aprimorada para exportação de dados do plano**

A API de exportação do plano agora oferece opções adicionais de exportação para se adequar melhor aos seus fluxos de trabalho de planejamento.

- Exporte dados de atividade laboral como FTE ou horas usando o novo parâmetro **laborDisplayType.**
- Use o novo parâmetro **isForReimport** para exportar dados em um formato pronto para reimportação.

**Correções de bugs**

- Corrigido um problema na Nova Visualização de Despesas que impedia a definição automática do valor do Objeto de Custo ao definir o Centro de Custo.
- Corrigimos o comportamento do menu suspenso da página Metas para exibir consistentemente o objeto pai selecionado e seus descendentes de nível mais baixo, independentemente do número de objetos filhos ou da atualização da página, garantindo uma resolução hierárquica estável e precisa.
- Corrigido um problema na guia Contratos que impedia a expansão do grupo de itens finais ao usar um agrupamento de colunas de quatro níveis.
- Corrigido um problema que permitia que centros de custo inválidos fossem aplicados às linhas de Atividade de Mão de Obra ao copiar e colar itens de linha.
- Corrigimos um problema na opção Exportar para reimportar na guia Trabalho, para que as colunas Código e Nome sejam exportadas para dimensões personalizadas adicionadas à guia Trabalho.
- Configurações de exportação atualizadas na integração de custos para publicar dados planejados com precisão total (8 casas decimais) e na moeda original definida no planejamento.

## Lançamento 5.17 Sandbox: 16 a 20 de fevereiro de 2026 | Principal: 23 a 27 de fevereiro de 2026

Integração do planejamento financeiro na nuvem

Esta versão apresenta a integração entre **o** Apptio Planning e **o** IBM Cloudability ’s Cloud Financial Planning (CFP), permitindo que os clientes incorporem os gastos com nuvem nos fluxos de trabalho de orçamento e previsão.

**Guia Nuvem**

- Os clientes podem ativar uma nova **guia Nuvem** na Nova Visualização de Despesas para gerenciar os custos da nuvem diretamente nos Orçamentos e Previsões d Apptio.
- A guia Nuvem pode ser ativada independentemente e não requer integração com o CFP.

**Integração CFP**

- Os clientes podem conectar o Planejamento Financeiro na Nuvem ( Apptio ) ao Planejamento Financeiro na Nuvem (CFP) para importar orçamentos e previsões da nuvem do CFP em uma única ação.
- As despesas com nuvem importadas são automaticamente mapeadas para a estrutura financeira do Planning.

**Detalhes adicionais** - O uso da guia Nuvem e a integração com o CFP requerem uma **licença do** Apptio Planning Standard.

Para saber mais, acesse [Connect em Cloudability Financial Planning](planning/connect-cfp.html).

Layouts aprimorados na nova visualização

Os layouts na Nova Visualização foram redesenhados para melhorar a clareza e o gerenciamento do layout:

- O menu suspenso Layouts agora exibe sempre o layout aplicado atualmente.
- Os layouts criados na Visualização Antiga ou na Nova Visualização são sincronizados automaticamente entre as duas visualizações, eliminando a necessidade de sincronização manual.
- O gerenciamento de layouts foi simplificado com a nova experiência Gerenciar layouts, permitindo que os usuários:
  - Ver todos os layouts públicos e privados
  - Pesquisar layouts por nome
  - Renomear layouts
  - Alterar a visibilidade do layout entre Público e Privado
  - Excluir layouts

  ![tela com layout aprimorado](../../../../03-media/apptio-planning/resources/images/it_planning_images/imp-layout-1.png)

  ![layout da página melhorado](../../../../03-media/apptio-planning/resources/images/it_planning_images/imp-layout-2.png)

Importação de itens de linha anexados e filtrados

Temos o prazer de anunciar o lançamento do recurso Importação de itens de linha filtrados e acrescentados, projetado para oferecer aos usuários mais controle e flexibilidade ao importar dados para o Planning.

**Agora você pode:**

- Adicione novos itens aos planos existentes sem sobrescrever todos os dados atuais.
- Filtre as importações por dimensões específicas, como Projeto, Conta, etc., para atualizar e substituir seletivamente subconjuntos de itens de linha.

![acrescentar item de linha](../../../../03-media/apptio-planning/resources/images/it_planning_images/append-li.png)

Para obter mais detalhes, consulte a documentação de ajuda [“Upload em massa de linhas”.](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=plans-bulk-upload-line-item-values "(Abre em uma nova guia ou janela)")

Atualização do nome da entidade de planejamento no ADM ( Data Management ) automatizado

- Os nomes das entidades de planejamento no ADM ( Data Management ) foram atualizados para rótulos mais claros e orientados para a ação — Importar e Publicar —, a fim de tornar a nomenclatura clara e intuitiva.
- Essas atualizações se aplicam apenas aos nomes exibidos; todas as funcionalidades do ADM permanecem inalteradas.

Para obter mais detalhes, consulte a documentação de ajuda [“Conectar-se ao Cálculo de Custos d Apptio](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=integrations-connect-apptio-costing "(Abre em uma nova guia ou janela)") ”.

Status de aprovação do plano API de exportação

- Apptio O planejamento agora oferece suporte à exportação programática de dados de status de aprovação do plano por meio da API de exportação.
- O endpoint POST permite exportar detalhes do status de aprovação em formato CSV para processamento externo.

Para obter mais detalhes, consulte a documentação de ajuda [“Plan APIs](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=apis-plan-api "(Abre em uma nova guia ou janela)") ”.

Outras melhorias

- O esquema da tabela de despesas em todos os tipos de despesas (Outras finanças, Mão de obra, Contrato, Ativos e Atividade de mão de obra) foi atualizado para incluir **o Status do plano** como um atributo padrão, exibindo o status atual (Em andamento, Enviado, Aprovado ou Devolvido) para cada linha de despesa.
- A Gestão de Despesas agora inclui **Cobrança** como um Tipo de Custo padrão, juntamente com os tipos de custo existentes **Construir** e **Executar**. Esta melhoria permite que os dados reais da Atividade de Trabalho do Projeto sejam categorizados como Encargo.
- A Gestão de Despesas agora suporta o upload de valores reais por **código externo**. Quando ativado, os usuários podem importar e resumir dados financeiros reais por **código externo.**
- Agora você pode filtrar colunas numéricas padrão e personalizadas em Despesas > Nova visualização usando operadores como **igual** **a**, diferente de, **maior que**, **maior ou igual a**, **menor que**, **menor ou igual a** e **entre**. Esta atualização facilita a localização rápida dos valores necessários. Os campos numéricos suportados incluem
  - **Colunas do período:** meses, trimestres, totais do ano fiscal, total do plano, total restante da previsão, total acumulado no ano
  - **Mão de obra:** remuneração base, quantidade de mão de obra, taxa de mão de obra do projeto
  - **Atividade de mão de obra:** Taxa de mão de obra do projeto, capacidade mensal
  - **Contratos:** Valor do contrato
  - **Ativos:** Preço de compra e quantidade de ativos.

Correções de bugs

- Corrigimos um problema que impedia a exibição das comparações de planos, mesmo que os usuários tivessem as permissões adequadas nos planos selecionados.
- Corrigimos um problema em que os títulos dos gráficos não eram atualizados ao alternar entre as guias **Financeiro** e **Quadro de funcionários** no Resumo de um plano. Os títulos agora mudam conforme o esperado, sem precisar atualizar a página.
- Corrigimos um problema em **Despesas > Nova Visualização,** onde não era possível adicionar comparações de planos quando a visualização estava desagrupada. Em contraste com a visualização antiga — que agrupava automaticamente os dados por **conta** e **objeto de custo** —, a nova visualização agora lida com esse cenário corretamente, aplicando automaticamente o agrupamento necessário quando uma comparação de planos é ativada.
- Melhoria no desempenho do instantâneo de objetos de custo. O tempo de captura de imagens melhorou em quase 50%.
- Corrigimos um problema em que os contratos que utilizavam o método de amortização Linear por Duração (Calendário Fiscal Personalizado) não eram prorrogados ao criar um novo plano utilizando o plano de referência. Os contratos com datas de término anteriores à data de início do novo plano não estavam sendo prorrogados conforme o esperado; agora, eles são prorrogados corretamente durante a criação do plano.
- Corrigido um problema na API de exportação de planos que impedia a exportação de dados devido à falta de um parâmetro.

## Lançamento 5.16 - Sandbox: 2 a 6 de fevereiro de 2026 | Principal: 9 a 13 de fevereiro de 2026

Previsão inteligente

A Previsão Inteligente introduz previsões baseadas em IA para gerar automaticamente previsões mais precisas com menos esforço manual. O sistema avalia os padrões históricos de gastos no nível do item de linha e aplica o modelo de previsão mais adequado a cada item.

Nesta versão, a Previsão Inteligente está disponível apenas para itens de despesas diversas. O suporte para tipos adicionais de itens de linha está previsto para 2026.

**Os principais benefícios incluem:**

- Seleção automatizada de modelos com base em tendências históricas
- Detecção de valores atípicos para melhorar a precisão das previsões
- Previsões mais precisas e consistentes
- Maior transparência e controle, com a capacidade de revisar e refinar os resultados

Essa capacidade ajuda as equipes a dedicarem menos tempo ao gerenciamento de previsões e mais tempo à análise e à ação com base em insights.

Para obter mais detalhes, consulte a documentação de ajuda [“Visão geral da Previsão Inteligente”](planning/intelligent-forecasting.html "A Previsão Inteligente introduz técnicas avançadas de previsão de séries temporais no Planejamento do Apptio, capacitando as equipes a produzir previsões mais precisas e consistentes com menos esforço manual. O recurso analisa padrões históricos de gastos e aplica automaticamente o modelo mais adequado para cada item.")

![previsão inteligente](../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/516-io.png)

API de exportação de análise de variação

- Apptio O planejamento agora oferece suporte à exportação programática de dados de análise de variação no nível do plano por meio da **API de exportação de análise de variação**.
- O endpoint POST permite exportar dados de análise de variação no nível do plano em formato CSV para processamento externo.

Para obter mais detalhes, consulte a documentação de ajuda “[Plan APIs](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=apis-plan-api "(Abre em uma nova guia ou janela)") ”.

Outras melhorias

- O **Painel** agora permite **selecionar intervalos de datas personalizados**, possibilitando a análise de relatórios e gráficos em qualquer período desejado.

  ![outras melhorias](../../../../03-media/apptio-planning/resources/images/it_planning_images/release-notes/516-other.png)
- **A API de importação de** planos foi ampliada para oferecer suporte **a linhas externas** por meio de um novo parâmetro, **externalItems**. Quando definido como **verdadeiro**, todos os itens marcados como externos são importados; quando definido como **falso**, eles são excluídos. Para obter mais detalhes, consulte a documentação de ajuda “[Plan APIs](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=apis-plan-api "(Abre em uma nova guia ou janela)") ”.

Correções de bugs

- Corrigimos um problema com a comparação de instantâneos na nova visualização de despesas.
- Corrigido um problema que afetava os layouts de exportação para usuários não administradores quando a comparação de planos estava ativada.
- Corrigido um problema em que as colunas de período (meses, trimestres, anos) não eram mantidas no layout salvo na nova visualização de despesas.
- Resolvido um problema com a configuração de exportação de dados do plano Exportar tudo ao compartilhar dados do Plano de ativos usando a integração automatizada Data Management ou a integração de custos legada.
- Cálculos de depreciação de ativos fixos quando se utiliza o método de depreciação de ativos por saldo decrescente em períodos iguais.

## Lançamento 5.15 - Sandbox: 19 a 23 de janeiro de 2026 | Principal: 26 a 30 de janeiro de 2026

Suporte externo para mão de obra e atividades laborais

O suporte à linha externa foi ampliado para incluir Trabalho e Atividade de Trabalho. Os administradores e responsáveis pelo processo orçamentário agora podem importar linhas externas para ambos os tipos de itens de linha.

A edição e exclusão de linhas externas na interface do usuário estão disponíveis para administradores, proprietários do processo orçamentário e qualquer usuário com a permissão “ **ExternalLineEdit** ” (Exibir e editar linhas externas).

Para obter mais detalhes, consulte a documentação de ajuda [“Linhas externas”](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=plans-external-line-items "(Abre em uma nova guia ou janela)")

Configurações de exportação para integração de custos

Uma nova configuração de “Export Settings” (Configurações de exportação) está agora disponível na página “Costing Integration” (Integração de custos) em Apptio quando a integração de transparência de custos ou o “ Data Management ” (Relatório de custos) automatizado está ativado. Essa configuração permite definir o comportamento padrão de exportação para todos os conjuntos de dados do plano em um único local centralizado.

**As principais capacidades incluem:**

- **Opções de formato de exportação:** escolha publicar o esquema completo (Exportar tudo) ou um formato reimportável (comportamento atual).
- **Configurações de moeda:** publique usando a moeda padrão da organização ou na moeda original.
- **Formato da data e precisão decimal:** configure o formato da data usado ao publicar no Cálculo de custos. A precisão decimal é definida por padrão nas configurações da organização definidas no Perfil da Empresa.
- **Filtros de dados confidenciais:** ative ou desative a filtragem de detalhes confidenciais sobre trabalho e finanças durante a publicação.
- **Estrutura de exportação:** a opção de publicar meses como linhas ou colunas foi movida da seção Configurar para esta nova configuração de Definições de exportação.

Para obter mais detalhes, consulte a documentação de ajuda [“Conectar-se ao Cálculo de Custos d Apptio ”.](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=integrations-connect-apptio-costing "(Abre em uma nova guia ou janela)")

Outras melhorias

- Notificações por e-mail aprimoradas para o fluxo de trabalho de aprovação multinível, a fim de garantir que os usuários recebam notificações apenas quando relevantes para seu nível de edição e posição na cadeia de aprovação. Apenas o aprovador do próximo nível recebe um e-mail quando uma solicitação de aprovação é enviada. Os usuários com nível de edição: Proprietário, Editar e Enviar ou Editar recebem notificações quando os departamentos enviados são aprovados ou devolvidos.
- Os atributos de memorando recém-criados agora suportam até 1.024 caracteres.
- Os usuários com a função de administrador ou proprietário do processo orçamentário podem publicar a lista de projetos em nível de planejamento do planejamento Apptio para o cálculo de custos Apptio por meio do Data Management automatizado.

Para obter mais detalhes, consulte a documentação de ajuda, “[Gerenciar notificações por e-mail](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=administration-manage-email-notifications "(Abre em uma nova guia ou janela)") ”, “[Publicar lista de projetos no Cálculo de Custos d Apptio](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-publish-projects-list-apptio "(Abre em uma nova guia ou janela)") ”.

**Correções de bugs**

- Corrigimos a caixa de diálogo de pré-visualização Atualizar dados de referência para classificar corretamente as atualizações do departamento, em vez de mostrá-las como atualizações do projeto.
- Corrigimos um problema na criação de planos e no processo de atualização de valores reais que poderia resultar em valores reais duplicados quando os valores reais eram resumidos por atributos não presentes no Gerenciamento de Gastos.
- Atualizamos o link da Central de Ajuda para levar os usuários diretamente à documentação do Apptio Planning no site de documentação IBM.
- Corrigido um problema na lista suspensa Departamentos, onde a pesquisa por departamentos podia resultar em erros.
- Corrigimos um problema em que os filtros de coluna não filtravam corretamente os atributos do projeto de acordo com as permissões do usuário.
