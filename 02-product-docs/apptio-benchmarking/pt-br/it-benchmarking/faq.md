---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "pt-br"
doc_type: "it-benchmarking"
title: "Perguntas frequentes sobre benchmarking"
breadcrumb: []
source_path: "it-benchmarking/faq.html"
images:
  - "resources/images/it_benchmarking_images/itb_faq.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Perguntas frequentes sobre benchmarking

**P. Quais despesas eu excluo dos gastos gerais de TI?**

Você precisa excluir dois tipos de cobranças para o Benchmarking:

1. Hardware ou software específico do setor, por exemplo, equipamento robótico de fabricação:

- Equipamentos construídos ou comprados para fins que não sejam de processamento de dados, mas que tenham componentes computadorizados, como máquinas robóticas de fabricação, dispositivos especializados de negociação de ações para o usuário final, como fones de ouvido para traders, caixas automáticos, dispositivos especializados de ponto de venda, scanners e monitores e sensores de pressão arterial em um sistema de controle de supervisão e aquisição de dados (SCADA).
- Equipamento de processamento de dados proprietário ou semelhante a um aparelho que tem uma única finalidade (normalmente vertical no setor) que não pode ser usada para outras finalidades gerais, como um computador que só pode controlar o fluxo de eletricidade através da rede elétrica. Como não pode ser reaproveitado, ele não está incluído em nosso modelo. Observe que outros sistemas que coletam dados desse tipo de computador que podem ser usados para outros fins não são considerados tecnologia operacional e, portanto, estão dentro do escopo de nosso modelo.

2. Gastos que estão fora do controle da TI, por exemplo, TI invisível

- Custos de tecnologia ou serviços que são revendidos, como salários de desenvolvedores envolvidos na criação de software comercialmente empacotado ou de funcionários especializados em TI que prestam serviços para os clientes externos da organização.
- "Encargos cruzados" internos e alocações corporativas relacionadas a despesas únicas grandes, significativas ou incomuns, como reduções na força de trabalho, redundância, realocação, aposentadoria, recursos humanos e salário do presidente.
- Assinaturas e serviços de dados comerciais, como a Bloomberg, mesmo que sejam gerenciados pela organização de TI.
- Serviços de terceirização de processos de negócios (BPO), em que as organizações terceirizam funções de negócios inteiras, como folha de pagamento ou gerenciamento de benefícios. Isso inclui casos em que o fornecedor de BPO fornece acesso a software e também garante que os resultados de seus serviços atenderão aos requisitos de negócios, como regulamentações fiscais e de retenção. O software como serviço fornecido pelo fornecedor ( SaaS ), que garante apenas que o software funcionará conforme especificado, está dentro do escopo das despesas de TI. A terceirização tradicional de funções de TI, como servidores e e-mail, também está dentro do escopo.
- Shadow IT, que é o gasto padrão de TI que está fora do controle e do suporte do departamento de TI.

**P. Quais despesas devo excluir para os Benchmarks de infraestrutura?**

Os dados em nosso Benchmark de Infraestrutura são provenientes do ISG. Para garantir uma comparação igualitária, não inclua nenhuma das quatro despesas do pool de custos abaixo em nenhum de seus custos ao comparar seu desempenho com as métricas da referência de infraestrutura:

- Instalações e energia
- Serviços internos
- Outros
- Telecomunicações

Observação: mapeie todas as despesas do pool de custos de Telecom para Rede - Transporte, pois é nesse local que o ISG as analisa.

![Imagem](../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/itb_faq.jpg)

**P. A rede - transporte inclui todas as despesas do pool de custos de telecomunicações nos benchmarks de infraestrutura do ISG?**

Sim. O ISG mapeia todas as despesas relacionadas ao pool de custos de Telecom para Rede - Transporte. Não inclua as despesas do pool de custos de telecomunicações para quaisquer outros benchmarks de infraestrutura.

**P. Como contabilizo a depreciação e a amortização (D&A)?**

Benchmarks do setor: As métricas de desempenho (obtidas de Rubin) incluem apenas desembolsos de caixa. A métrica de despesas deve incluir todas as despesas de capital e despesas operacionais do ano fiscal atual. Não inclua D&A nos Benchmarks do setor.

TI OpEx Benchmarks: As métricas de desempenho (obtidas dos dados do site Apptio ) incluem apenas despesas operacionais. Incluir despesas de D&A, mas não incluir despesas capitalizadas em TI OpEx Benchmarks

Benchmarks de infraestrutura: As métricas de desempenho (obtidas do ISG) incluem desembolsos de caixa e depreciação. Inclua as despesas D&A e as despesas capitalizadas nos indicadores de infraestrutura.

Observação: se você tiver configurado o Benchmarking em Transparência de custos, sua programação de despesas D&A será puxada automaticamente. Se você estiver usando o Benchmarking interativo, suas despesas de D&A serão estimadas usando um cronograma de depreciação linear de três anos de suas despesas de capital.

**P. Como os custos da nuvem pública são contabilizados em Opex e infra BM?**

Benchmarks do setor: Todas as despesas com nuvem pública estão incluídas nos gastos com TI.

OpEx Referências: Todas as despesas com a nuvem pública estão incluídas no pool de custos de Serviços externos e são mapeadas para a Torre de TI e Aplicativos posteriormente.

Benchmarks de infraestrutura: os benchmarks de infraestrutura são apenas para despesas no local. Todas as despesas com a nuvem pública precisam ser excluídas. Isso é tratado automaticamente no modelo de custo Apptio, atribuindo todos os custos de nuvem a Delivery = "Public Cloud" e excluindo esses custos dos custos de infraestrutura em nível de torre que são comparados com os benchmarks de infraestrutura.

**P. Posso fazer o benchmark de BUs ou regiões específicas separadamente?**

A melhor maneira de fazer benchmarking de BUs ou regiões individuais é preencher os volumes financeiros e unitários específicos da BU/Região no Interactive Benchmarking. O software lhe dá a opção de ajustar os arquétipos ou comparar com diferentes setores, conforme sua conveniência.

Observação: não há funcionalidade para que os dados persistam em diferentes BUs/Regiões. Você terá que atualizar os dados à medida que analisar diferentes BUs/Regiões. Os clientes podem modificar os relatórios de benchmark do site Costing Standard para mostrar e comparar diferentes benchmarks com base na unidade de negócios/região. Isso requer relatórios personalizados para criar essas exibições e não é fornecido imediatamente.

**P. Incluo os gastos com empreiteiros?**

Sim. O único motivo para não incluir as despesas com terceirizados é se elas fizerem parte dos serviços de terceirização de processos de negócios (BPO).

**P. Onde devo alocar os gastos de TI específicos do setor, como máquinas de ressonância magnética, robôs de linha de montagem e seu software, bombas de infusão e dispositivos andPOS no varejo?**

Os gastos com TI específicos do setor não estão incluídos nos benchmarks de custos de TI e precisam ser excluídos.

**P. Como faço para lidar com o caso em que meus dados de custo subjacentes são fornecidos em moedas diferentes?**

Primeiro, você deve consolidar as várias moedas dos dados de custo em uma única exibição de moeda. Em seguida, você pode mapear seus dados de custo em moeda única para os benchmarks, conforme detalhado no guia de configuração. Por padrão, o modelo de custo Apptio exige que uma "moeda base" seja configurada para padronizar todos os custos nos modelos de custo. Diferentes moedas podem ser exibidas na interface do usuário por meio das configurações preferenciais de várias moedas.

Observação: Todas as principais moedas são aceitas.

**P. Onde devo alocar dados comerciais e assinaturas de informações?**

As assinaturas de dados e informações comerciais precisam ser alocadas ao pool de custos Outros. No entanto, o benchmarking de custos de TI não inclui dados comerciais e assinaturas de informações, e você precisa excluir essas despesas para fazer comparações semelhantes.

**P. Posso alterar as métricas em que os benchmarks são medidos, por exemplo, dividir por dispositivos em vez de usuários?**

Nº Todos os KPIs disponíveis são exibidos no produto. Estamos sempre buscando expandir os KPIs que estamos divulgando, portanto, entre em contato com o gerente de contas ou de sucesso do cliente e compartilhe as visualizações e métricas de seu interesse.

**P. Devo incluir as despesas de TI relacionadas à mudança/crescimento e transformação no benchmarking?**

Sim. Todas as despesas operacionais estão incluídas em todos os três benchmarks do setor, de TI OpEx e de infraestrutura. As despesas de capital não estão incluídas nos benchmarks de TI OpEx.

**P. Se você alterar os volumes/quantidades na tela Infrastructure Benchmarks, isso deverá substituir os volumes/quantidades extraídos do CT?**

Não, as alterações de custo e volume feitas diretamente no aplicativo Infrastructure Benchmark são exclusivas do Interactive Benchmarking. Eles não são enviados para o modelo de custo Costing Standard y. No entanto, os custos de torre/subtorre e os volumes unitários associados no objeto IT Resource Towers em Costing Standard podem ser integrados aos Interactive Benchmarks.

**P. Ao selecionar o período para extrair os dados do CT para o benchmarking, ele usa os valores acumulados no ano e depois anualiza, ou anualiza com base apenas no mês selecionado?**

Os dados de Benchmarking do site Costing Standard usam um total de 12 meses para os custos anuais e para os custos unitários.

**P. O que deve ser incluído na subtorre do banco de dados?** 

- Inclua seus sistemas de gerenciamento de banco de dados (DBMS) baseados em servidor, como Oracle e MS SQL.
- Não inclua despesas de hardware no gerenciamento de dados, pois elas são mapeadas para computação e armazenamento.
- Inclua despesas com pessoal para suporte operacional e de segundo nível, incluindo administração, configuração e atualizações.
- Inclua também qualquer software de banco de dados, bem como serviços gerenciados para bancos de dados de servidores

**P. De onde vêm os dados de benchmarking?**

Os três segmentos diferentes de benchmarking dependem de três fontes de dados diferentes:

- As referências do setor são obtidas da Rubin Worldwide
- TI OpEx Os benchmarks são obtidos de Apptio
- As referências de infraestrutura são obtidas do ISG

**P. Como posso garantir comparações de igual para igual?**

Há várias maneiras de garantir a comparabilidade:

Referências do setor: Ajuste para

- Indústria
- Região
- Tamanho

TI OpEx Benchmarks: Ajuste para arquétipos de modelos operacionais para ambos

- Aplicativos (construir versus comprar)
- Conjuntos de custos (pessoal, hardware, software, fornecedor)

Benchmarks de infraestrutura: Ajuste para

- Volume
- Região
- Indústria

Observação: para benchmarks de infraestrutura, o volume é o maior impulsionador devido às economias de escala; a região e o setor têm um impacto menor.

**P. Como o produto funciona com o CT e como configurá-lo adequadamente, por exemplo, alterando os volumes nos feeds do IBX para o CT?**

[Consulte a seção sobre configuração](configuration/config-guide.html) para saber como configurar o benchmarking

As escolhas feitas no Benchmarking interativo não substituem os dados de volume ou custo no CT
