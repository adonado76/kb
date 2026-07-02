---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Perguntas Frequentes"
breadcrumb:
  - "Benchmarking"
  - "Relatórios de benchmarking"
  - "Solução de problemas e perguntas frequentes"
source_path: "it-benchmarking/troubleshooting/faq.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Perguntas Frequentes

## P. Quão exatas são essas referências?

R. Eles são estatisticamente sólidos, mas não precisos ao centavo. Os benchmarks nos dizem se estamos abaixo, dentro da média ou acima em comparação com nossos pares e onde devemos concentrar nossas perguntas. Ainda dependemos de nossos próprios dados detalhados para tomar decisões finais.

## P. Podemos ver quem são os pares?

R. Nº Os participantes são anônimos por padrão. Vemos apenas distribuições agregadas (medianas, quartis, bandas), não organizações nomeadas.

## P. Estar acima da mediana significa que somos ineficientes?

R. Não automaticamente. Isso significa que gastamos mais do que o típico colega nessa métrica. Isso pode ser ineficiência ou pode refletir escolhas deliberadas, como maior resiliência, regulamentação mais rígida ou um modelo de fornecimento diferente. A referência nos indica onde investigar, não que algo esteja automaticamente errado.

## P. Por que esse número é diferente do número da minha equipe?

R. Porque provavelmente estamos usando um escopo ou definição diferente. As métricas de referência utilizam definições padrão alinhadas com o TBM, para que sejam comparáveis entre as organizações. Quando observamos diferenças nos números internos, primeiro reconciliamos o escopo e, em seguida, decidimos qual métrica usar para cada finalidade.

## P. Podemos alterar a forma como o índice de referência é calculado?

R. Nº As definições de referência são fixas para que todos comparem a mesma coisa. Podemos criar métricas internas personalizadas no Cálculo de Custos se precisarmos analisar os dados de forma diferente, mas isso é separado do benchmark externo.

## P. Tenho um problema que não consigo resolver sozinho. Como posso solicitar ajuda?

R. Os tickets de suporte podem ser enviados e analisados na [Central de Ajuda d IBM](https://www.ibm.com/mysupport/ "(Abre em uma nova guia ou janela)"). Além disso, os clientes são bem-vindos a visitar [a Comunidade,](https://community.ibm.com/community/user/groups/community-home?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b "(Abre em uma nova guia ou janela)") onde outros clientes do IBM Apptio e funcionários da IBM colaboram e compartilham conhecimento.

## P. Tenho uma ideia para melhorar o Benchmarking Interativo. Como posso enviar a ideia para IBM?

R. Os clientes podem enviar suas ideias através [do portal de ideias](https://ideas.ibm.com/products/7428698806022729746 "(Abre em uma nova guia ou janela)") IBM.

## P. Posso acessar detalhes de benchmarks de anos anteriores?

R. Não com o Benchmarking Interativo. No entanto, os relatórios de benchmark habilitados para cálculo de custos podem fornecer as informações (se integrados ao cálculo de custos).

## P. Se integrado ao Cálculo de Custos, de qual ambiente do projeto de Cálculo de Custos são recuperados os dados de gastos com TI?

A. Apenas no ambiente de produção.

## P. Devo incluir despesas fora do controle da organização de TI?

R. Nº Não inclua nenhum gasto, incluindo “Shadow IT” controlado por outras áreas da sua empresa maior.

## P. Quais grupos de custos devo excluir da análise comparativa da infraestrutura?

R. Exclua o seguinte:

- Instalações e energia
- Telecomunicações
- Serviços internos
- Outros

## P. Onde devo incluir as despesas pertencentes ao pool de custos de telecomunicações?

R. Atribua as despesas do pool de custos de telecomunicações à subtorre “Transporte”.

## P. Existem métricas de referência de infraestrutura para os grupos de custos “Instalações e energia”, “Serviços internos” ou “Outros”?

R. Nº

## P. Como os custos da nuvem pública são contabilizados nas métricas de benchmarking de infraestrutura e de um OpEx?

A. Em uma análise comparativ OpEx, os custos da nuvem pública são incluídos no pool de custos de serviços externos. Na análise comparativa do setor, os custos da nuvem pública são incluídos nos gastos com TI.

## P. Devo incluir os prestadores de serviços?

R. Sim.

## P. Onde posso alocar assinaturas de dados ou informações comerciais?

R. Atribua-os ao pool de custos Outros.

## P. O que posso fazer se quiser ver diferentes KPIs para uma área específica, por exemplo, dividir por dispositivos em vez de usuários?

R. Todos os KPIs disponíveis são exibidos no produto.

## P. Que despesas devo excluir dos gastos gerais com TI?

R. Você precisa excluir dois tipos de cobranças para o Benchmarking:

1. Hardware ou software específico do setor, por exemplo, equipamentos de fabricação robótica:
   - Equipamentos construídos ou adquiridos para fins não relacionados ao processamento de dados, mas que possuem componentes computadorizados, tais como máquinas robóticas de fabricação, dispositivos especializados para usuários finais de negociação de ações, como fones de ouvido para operadores, caixas eletrônicos, dispositivos especializados para pontos de venda, scanners e monitores e sensores de pressão arterial em um sistema de controle de supervisão e aquisição de dados (SCADA).
   - Equipamento de processamento de dados semelhante a um eletrodoméstico ou proprietário que tem uma única finalidade (normalmente vertical na indústria) e não pode ser utilizado para outros fins gerais, como um computador que só pode controlar o fluxo de eletricidade através da rede elétrica. Como não pode ser reutilizado, não está incluído em nosso modelo. Observe que outros sistemas que coletam dados desse tipo de computador que podem ser usados para outros fins não são considerados tecnologia operacional e, portanto, estão dentro do escopo do nosso modelo.
2. Gastos que estão fora do controle da TI (por exemplo, “Shadow IT”).
   - Custos com tecnologia ou serviços que são revendidos, como salários de desenvolvedores envolvidos na criação de software comercialmente empacotado ou funcionários com habilidades em TI que prestam serviços para clientes externos da organização.
   - “Encargos cruzados” internos e alocações corporativas relacionadas a despesas únicas grandes, significativas ou incomuns, tais como reduções na força de trabalho, demissões, realocações, aposentadorias, recursos humanos e salário do presidente.
   - Assinaturas e serviços de dados comerciais, como a Bloomberg, mesmo que sejam gerenciados pela organização de TI.
   - Serviços de terceirização de processos de negócios (BPO), nos quais as organizações terceirizam funções comerciais inteiras, como folha de pagamento ou gestão de benefícios. Isso inclui casos em que o fornecedor de BPO oferece acesso a software e também garante que os resultados de seus serviços atenderão aos requisitos comerciais, como regulamentos fiscais e de retenção na fonte. O software fornecido pelo fornecedor como serviço ( SaaS ), que apenas garante que o software funcionará conforme especificado, está dentro do escopo dos gastos com TI. A terceirização tradicional de funções de TI, como servidores e e-mail, também está dentro do escopo.
   - Shadow IT, que são gastos padrão com TI que estão fora do controle e do suporte do departamento de TI.

## P. Que despesas devo excluir dos benchmarks de infraestrutura?

R. Os dados em nosso Benchmark de Infraestrutura são provenientes da ISG. Para garantir uma comparação equitativa, não inclua nenhuma das quatro despesas de pool de custos abaixo em nenhum dos seus custos ao comparar seu desempenho com as métricas de referência de infraestrutura:

- Instalações e energia
- Serviços internos
- Outros
- Telecomunicações

Observação: Mapeie todas as despesas do pool de custos de telecomunicações para Rede – Transporte, pois é onde o ISG as analisa.

![Despesas com custos de telecomunicações para a rede](../../resources/images/it%20benchmarking_images/cost-pool-expenses.jpg)

## P. A rede – transporte inclui todas as despesas do pool de custos de telecomunicações nos benchmarks de infraestrutura da ISG?

R. Sim. O ISG mapeia todas as despesas relacionadas ao pool de custos Telecom para Rede – Transporte. Não inclua despesas com custos de telecomunicações para quaisquer outros benchmarks de infraestrutura.

## P. Como contabilizo a depreciação e amortização (D&A)?

Referências do setor: As métricas de desempenho (obtidas da Rubin) incluem apenas despesas em dinheiro. A métrica de gastos deve incluir todas as despesas de capital e despesas operacionais do ano fiscal atual. Não inclua D&A nos benchmarks do setor.

OpEx de TI Benchmarks: As métricas de desempenho (obtidas a partir de dados da Apptio ) incluem apenas despesas operacionais. Inclua despesas com D&A, mas não inclua despesas capitalizadas nos benchmarks de TI OpEx

Referências de infraestrutura: As métricas de desempenho (obtidas da ISG) incluem despesas em dinheiro, bem como depreciação. Inclua as despesas com D&A, bem como as despesas capitalizadas, nos benchmarks de infraestrutura.

Observação: se você configurou o Benchmarking em Transparência de Custos, sua programação de despesas de D&A será importada automaticamente. Se você estiver usando o Benchmarking Interativo, suas despesas com D&A serão estimadas usando um cronograma de depreciação linear de três anos de suas despesas de capital.

## P. Como os custos da nuvem pública são contabilizados no Opex e na infra BM?

A. Referências do setor: todas as despesas com nuvem pública estão incluídas nos gastos com TI.

OpEx Referências: Todas as despesas com nuvem pública são incluídas no pool de custos Serviços Externos e, posteriormente, mapeadas para a Torre de TI e Aplicações.

Referências de infraestrutura: as referências de infraestrutura são apenas para despesas locais. Todas as despesas com nuvem pública devem ser excluídas. Isso é tratado automaticamente no modelo de custos Apptio, atribuindo todos os custos de nuvem à Entrega = “Nuvem Pública” e excluindo esses custos dos custos de infraestrutura de nível de torre que são comparados com os Benchmarks de Infraestrutura.

## P. Posso comparar unidades de negócios ou regiões específicas separadamente?

A melhor maneira de comparar unidades de negócios (BUs) ou regiões individuais é preencher as informações financeiras específicas da BU/região e os volumes unitários na comparação interativa. O software oferece a opção de ajustar arquétipos ou comparar diferentes setores, conforme você achar melhor.

Observação: não há funcionalidade para manter os dados para diferentes unidades de negócios/regiões. Você terá que atualizar os dados à medida que analisar diferentes unidades de negócios/regiões. Os clientes podem modificar os relatórios de referência padrão de custos para mostrar e comparar diferentes referências com base na unidade de negócios/região. Isso requer relatórios personalizados para criar essas visualizações e não é fornecido de fábrica.

## P. Devo incluir os gastos com empreiteiros?

R. Sim. A única razão para não incluir os gastos com prestadores de serviços é se eles fizerem parte dos serviços de terceirização de processos de negócios (BPO).

## P. Onde devo alocar os gastos com TI específicos do setor, como máquinas de ressonância magnética, robôs de linha de montagem e seus softwares, bombas de infusão e dispositivos POS no varejo?

R. Os gastos com TI específicos do setor não estão incluídos nos benchmarks de custos de TI e precisam ser excluídos.

## P. Como devo proceder quando os dados dos meus custos subjacentes estão em moedas diferentes?

A.You primeiro, você desejará consolidar as várias moedas dos dados de custo em uma única visualização de moeda. Em seguida, você pode mapear seus dados de custo em moeda única para os benchmarks, conforme detalhado no guia de configuração. Por padrão, o modelo de custos do Apptio exige que uma “moeda base” seja configurada para padronizar todos os custos nos modelos de custos. Diferentes moedas podem ser exibidas na interface do usuário através das configurações preferenciais de múltiplas moedas.

Observação: todas as principais moedas são aceitas.

## P. Onde posso alocar assinaturas de dados e informações comerciais?

R. As assinaturas de dados e informações comerciais devem ser alocadas ao pool de custos Outros. No entanto, a comparação de custos de TI não inclui assinaturas de dados e informações comerciais, e você precisa excluir essas despesas para fazer comparações semelhantes.

## P. Posso alterar as métricas nas quais os benchmarks são medidos, por exemplo, dividir por dispositivos em vez de usuários?

R. Nº Todos os KPIs disponíveis são exibidos no produto. Estamos sempre buscando expandir os KPIs que apresentamos, portanto, entre em contato com seu gerente de sucesso do cliente ou gerente de conta e compartilhe as visualizações e métricas nas quais você está interessado.

## P. Devo incluir as despesas de TI relacionadas com a mudança/crescimento e transformação na análise comparativa?

R. Sim. Todas as despesas operacionais estão incluídas nos três indicadores de desempenho: Indústria, OpEx de TI e Infraestrutura. As despesas de capital não estão incluídas nos benchmarks de TI OpEx.

## P. Se você alterar os volumes/quantidades na tela Benchmarks de infraestrutura, isso substituirá os volumes/quantidades extraídos do CT?

R. Não, as alterações de custo e volume feitas diretamente no aplicativo Infrastructure Benchmark são exclusivas do Interactive Benchmarking. Eles não são enviados para o modelo de custos padrão y. No entanto, os custos da torre/subtorre e os volumes unitários associados no objeto Torres de recursos de TI no Padrão de cálculo de custos podem ser integrados com Benchmarks interativos.

## P. Ao selecionar o período para extrair os dados do CT para a análise comparativa, ele usa os valores acumulados no ano e depois anualiza, ou anualiza com base apenas no mês selecionado?

A. Os dados de referência da Norma de Custeio utilizam um total acumulado de 12 meses para os custos anuais e para os custos unitários.

## P. O que deve ser incluído na subtorre Banco de Dados?

R. Inclua seus sistemas de gerenciamento de banco de dados (DBMS) baseados em servidor, como Oracle e MS SQL.

Não inclua despesas com hardware no gerenciamento de dados, pois elas são mapeadas para computação e armazenamento.

Inclua despesas com pessoal para suporte operacional e de segundo nível, incluindo administração, configuração e atualizações.

Inclua também qualquer software de banco de dados, bem como serviços gerenciados para bancos de dados de servidores

## P. De onde vêm os dados de benchmarking?

R. Os três diferentes segmentos da análise comparativa baseiam-se em três fontes de dados diferentes:

- Os benchmarks do setor são fornecidos pela Rubin Worldwide
- OpEx Os benchmarks de TI são obtidos em Apptio
- Os benchmarks de infraestrutura são fornecidos pela ISG

## P. Como posso garantir comparações equivalentes?

Existem várias maneiras de garantir a comparabilidade:

Os benchmarks do setor  
 ajustam-se para:

- Indústria
- Região
- Tamanho

OpEx es de TI Benchmarks

Ajuste os arquétipos do modelo operacional para ambos:

- Aplicativos (desenvolver ou adquirir)
- Grupos de custos (pessoas, hardware, software, fornecedores)

Referências de infraestrutura

Ajustar para:

- Volume
- Região
- Indústria

Observação: para benchmarks de infraestrutura, o volume é o principal fator devido às economias de escala; a região e o setor têm um impacto menor.

## P. Como o produto funciona com o CT e como posso configurá-lo adequadamente, por exemplo, alterando volumes em feeds IBX para o CT?

R. Consulte a seção sobre configuração para saber como configurar o benchmarking. Quaisquer escolhas que você fizer no Benchmarking Interativo não substituirão os dados de volume ou custo no CT
