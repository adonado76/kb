---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Glossário e siglas"
breadcrumb:
  - "Billing"
  - "Introdução"
source_path: "boit/billing/getting-started/key-concepts-terms.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Glossário e siglas

Este apêndice define termos e siglas comuns usados em toda a Ajuda de Faturamento. Use-o como referência rápida ao ler outras seções ou ao trabalhar com o produto.

## Como usar este apêndice

- Os termos estão agrupados por tema:
  - Conceitos fundamentais
  - Dados e modelagem
  - Relatórios e processo
  - Acrônimos
- Os termos específicos da edição estão identificados:
  - “Apenas o essencial sobre faturamento”
  - “Apenas padrão de faturamento”

## Conceitos básicos de faturamento

**Faturamento**

O conjunto de modelos, tabelas e relatórios que calculam, apresentam e, opcionalmente, registram os encargos de tecnologia aos consumidores. Construído com base em um projeto de cálculo de custos.

**Fundamentos de faturamento**

Edição básica do Billing, focada em showback e chargeback simples ( PxQ ). Entregue como componentes dentro de um projeto Costing Essentials e apresentado como uma coleção de relatórios de “Faturamento”.

**Padrão de faturamento**

Edição completa do Billing, com componentes adicionais específicos do domínio (nuvem, aplicativos, infraestrutura, projetos, variação, preços de transferência) e um endpoint dedicado ao Billing. Construído com base em um projeto de padrão de custos.

**Cálculo de custos**

A camada de modelagem de custos que aloca os gastos com tecnologia a serviços, aplicativos e consumidores. O faturamento depende do cálculo de custos para estruturas de custos e, muitas vezes, para informações sobre custos unitários.

**PxQ (Preço vezes Quantidade)**

O padrão básico de cálculo da faturação:

Custo = Unidades × Taxa

As unidades representam o consumo, a taxa representa o preço ou a recuperação por unidade.

**Consumidor**

Qualquer entidade que receba encargos tecnológicos. Exemplos: unidade de negócios, departamento, centro de custos, produto, projeto, programa, região ou entidade jurídica.

**Serviço / Oferta / Produto**

O “o quê” que está sendo cobrado. Pode ser um serviço, plataforma, produto ou pacote de tecnologia que aparece nas contas e nos relatórios de faturamento.

**Showback**

Relatar encargos ou preços “como se fossem” aos consumidores sem lançar diários no livro razão. Utilizado para garantir transparência e mudança de comportamento sem receita interna formal.

**Estorno**

Usar o faturamento para gerar cobranças prontas para registro no diário que são lançadas no razão geral como receita e despesa internas.

**Edição**

O nível de capacidade de faturamento subscrito. Para faturamento, as edições são Essentials e Standard. Um projeto de cálculo de custos executa apenas uma edição de faturamento por vez.

## Termos relacionados a dados e modelagem

**Cálculo de custos do projeto**

O projeto TBM Studio, onde residem modelos de custos, tabelas e muitos componentes compartilhados de faturamento. Contém ambientes de desenvolvimento, teste e produção.

**No ambiente de desenvolvimento**

O ambiente onde as alterações de configuração são feitas e testadas pela primeira vez. Os itens são verificados, editados e registrados aqui. As compilações criadas aqui são espelhadas no Staging.

**Ambiente de teste**

O ambiente utilizado para controle de qualidade e ensaios gerais. As compilações em Staging são candidatas à promoção para Produção após validação e aprovação.

**Ambiente de produção**

O ambiente ativo onde são executados os relatórios do usuário final, os modelos de faturamento e as exportações de diários para períodos oficiais.

**Componente**

Um conjunto empacotado de modelos, tabelas, métricas e relatórios que podem ser instalados em um projeto de Custeio. Exemplos: Faturamento – Cobrança, Faturamento – Relatórios de cobrança, BoIT – Servidores, BoIT – Nuvem.

**Terminal**

O ponto de entrada front-end que exibe relatórios para um determinado projeto e escopo.

- Para o Billing Essentials, os relatórios aparecem no endpoint do Costing Essentials como uma coleção “Billing”.
- Para o padrão de faturamento, existe um endpoint de faturamento separado.

**Dados principais**

Dados de referência relativamente estáveis, como consumidores, serviços, aplicações, entidades jurídicas e unidades. Usadas como chaves e dimensões em modelos e relatórios.

**Dados de consumo**

Registros que representam “quanto” de um serviço foi utilizado, por qual consumidor e em qual período. Normalmente contém: consumidor, serviço, unidades, período e atributos opcionais.

**Taxa/preço**

O valor por unidade utilizado nos cálculos de PxQ. As tabelas de tarifas definem qual preço se aplica a cada serviço e período e, às vezes, por tipo de consumidor, região ou outras dimensões.

**Unidade**

A medição para consumo e preços. Exemplos: usuário por mês, GB por mês, VM por mês, ticket por mês, dispositivo por mês.

**Custo unitário**

Custo por unidade de um serviço, geralmente derivado do cálculo de custos, dividindo o custo total pelo total de unidades. Usado para comparar custo versus preço.

**Tabela de mapeamento**

Uma tabela que vincula valores de um domínio ou sistema a outro. Exemplos: centro de custos externo para consumidor interno, tags de nuvem para serviços e consumidores, IDs de projeto para aplicativos.

**Pessoa jurídica**

Uma empresa ou entidade que existe para fins legais e fiscais. Utilizado para preços de transferência e visualizações entre empresas no Padrão de Faturamento.

**Preço de transferência**

O preço utilizado para encargos internos entre entidades ou países. Normalmente derivados ou relacionados com os preços de faturação padrão, mas limitados por regras fiscais e regulamentares.

## Termos de relatórios e processos

**Relatório no formato de fatura**

Um relatório que mostra os encargos para um determinado consumidor e período em um layout semelhante a uma fatura, normalmente com colunas de serviço, unidades, tarifa e encargos, além dos totais.

**Relatório detalhado**

Um relatório mais detalhado que mostra os fatores por linha por trás de uma conta. Frequentemente inclui campos adicionais, como ambiente, região, projeto ou segmentos baseados em tags.

**Relatório do diário / Exportação do diário**

Um relatório de faturamento elaborado para atender aos requisitos de lançamento financeiro. Inclui segmentos de contas contábeis, segmentos de consumidores, valores e referências, e é usado para lançamento de estornos.

**Relatório de controle de qualidade / Relatório de exceções**

Relatórios elaborados para destacar possíveis problemas. Exemplos: mapeamentos ausentes, volumes zero ou negativos, picos incomuns, registros órfãos.

**Variância**

A diferença entre dois valores, geralmente:

- Real vs planejado
- Custo versus preço
- Período atual vs. período anterior

**Análise da taxa unitária**

A análise concentrou-se no custo por unidade de um serviço ao longo do tempo, frequentemente utilizado para explicar e otimizar a economia da tecnologia.

**Ensaio geral**

Execução completa do ciclo de faturamento no ambiente de teste antes da primeira entrada em operação no ambiente de produção. Utiliza dados reais ou realistas e valida modelos, relatórios e exportações.

**Hipercuidado**

O período imediatamente após o lançamento (geralmente de um a três ciclos de faturamento) em que o tratamento de incidentes, o controle de qualidade e o suporte são intencionalmente mais intensivos.

**Runbook**

Uma descrição documentada e passo a passo do ciclo operacional de faturamento. Inclui prazos, responsabilidades e dependências para carregamento de dados, execução de modelos, controle de qualidade e exportações.

**Período apenas para showback**

Um período em que o faturamento é usado para relatar cobranças, mas os diários ainda não foram lançados, geralmente durante a fase piloto ou adoção inicial.

## Acrônimos

**Unidade de Negócios**

Unidade de Negócios. Um segmento organizacional de alto nível que frequentemente atua como consumidor de serviços de tecnologia.

**Diretor de Informática / Diretor Técnico / Diretor Financeiro / Diretor de Operações**

Diretor de Informação, Diretor de Tecnologia, Diretor Financeiro, Diretor Operacional. Patrocinadores executivos ou partes interessadas de Faturamento e Custeio.

**GL**

Contabilidade geral. O sistema financeiro de registro de lançamentos contábeis, incluindo diários de estorno, quando utilizados.

**ITFM / ITFM(A)**

Gestão financeira de TI. ITFMA refere-se a um analista responsável pelos processos, análises e ferramentas de ITFM.

**PMO**

Escritório de Gerenciamento de Projetos. Frequentemente consumido com visualizações de projetos de resultados de faturamento.

**PPM**

Gestão de projetos e portfólio. As ferramentas e os processos utilizados para gerenciar projetos e portfólios que podem ser mapeados para o faturamento.

**PxQ**

Preço vezes Quantidade, o padrão central de cálculo de faturamento que gera cobranças.

**QA**

Garantia de qualidade. Atividades e verificações que garantem que os dados e resultados de faturamento estão aptos para uso antes da publicação.

**RACI**

Responsável, prestando contas, consultado, informado. Uma estrutura por vezes utilizada para descrever funções e responsabilidades nos processos de faturação e cálculo de custos.

**TBM**

Gestão de Negócios Tecnológicos. A disciplina e a taxonomia mais amplas para gerenciar o custo, o desempenho e o valor da tecnologia. O faturamento utiliza conceitos alinhados com o TBM, mas pode ser utilizado por organizações que não classificam suas práticas como TBM.

**TBMA**

Analista TBM. Analista responsável por trabalhar com dados, modelos e ferramentas alinhados com o TBM, tais como Custos e Faturamento.

**UOM**

Unidade de medida. A unidade utilizada para quantificar o consumo do serviço e definir tarifas, como usuário por mês ou GB por mês.

## Onde as definições aparecem no produto

Algumas implementações expõem definições curtas diretamente nas descrições dos relatórios ou nas dicas de ferramentas.

Exemplos:

- Campos de descrição do relatório que explicam o que um relatório mostra e para quem é destinado.
- Descrições das colunas para campos críticos, como Unidade, Taxa, Consumidor e Serviço.
- Links de ajuda nos relatórios de faturamento que direcionam para este apêndice.

Manter a terminologia consistente neste apêndice, nos modelos e nos relatórios reduz a confusão e torna mais fácil para novos usuários confiarem e adotarem o Billing.
