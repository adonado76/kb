---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Conceitos-Chave"
breadcrumb:
  - "TBM Studio"
  - "Introdução"
source_path: "studio/new-uc/getting-started/core-concepts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conceitos-Chave

|  |  |
| --- | --- |
| **Tipo de Conteúdo** | Conceitual |
| **Público-alvo** | Novos usuários |
| **Tempo de leitura** | 5 minutos |
| **Pré-requisitos** | Nenhum |

Antes de começar a usar o TBM Studio, compreender seis conceitos fundamentais irá ajudá-lo a trabalhar com mais eficácia. Esses componentes atuam em conjunto para transformar dados brutos sobre custos de TI em insights úteis para a sua organização.

## Projetos

Um **projeto** é o seu espaço de trabalho exclusivo no TBM Studio, onde você organiza todo o seu trabalho no TBM. Pense nisso como uma área de cálculo independente dentro do domínio da sua organização, que reúne tudo o que você precisa para a modelagem de custos e a geração de relatórios.

Dentro de um projeto, você encontrará:

- Tabelas de dados com as informações importadas e transformadas
- Modelos de custos que mostram como o dinheiro circula pela sua organização
- Métricas que calculam valores como custo, orçamento e previsão
- Relatórios que apresentam informações relevantes para as partes interessadas

Sua organização pode ter vários projetos — talvez um para a transparência dos custos de TI, outro para o cálculo de custos de aplicativos ou projetos distintos para diferentes unidades de negócios. Cada projeto mantém seus dados, modelos e relatórios interligados e interdependentes.

## Tabelas e dados

**As tabelas** são onde seus dados ficam armazenados no TBM Studio. Elas contêm as informações brutas sobre suas operações de TI e finanças que serão utilizadas em seus modelos de custos.

As tabelas provêm de duas fontes:

**As tabelas de origem** são criadas através do upload de arquivos (como o CSV ou o Excel) que contêm dados dos seus sistemas — lançamentos contábeis, faturas de serviços em nuvem, inventários de ativos ou dados sobre o quadro de funcionários.

**As tabelas de transformação** são criadas a partir de tabelas existentes por meio da aplicação de operações como filtragem, junção, mapeamento ou cálculos. Essas transformações permitem que você limpe, enriqueça e reestruture seus dados para que se adaptem à estrutura exigida pelos seus modelos.

As tabelas estão organizadas por período, permitindo que você acompanhe as mudanças mês a mês. Cada tabela é composta por colunas (dimensões como “Departamento” ou “Aplicação”) e pode incluir valores numéricos que serão utilizados nos cálculos.

## Modelos

Um **modelo** mostra como os custos e outros indicadores se distribuem pela sua organização. É o mecanismo que calcula o custo real dos serviços de TI, distribuindo as despesas desde a sua origem até aos elementos que as consomem.

No centro de um modelo estão **os objetos do modelo** — cada um representando uma camada distinta da sua estrutura de custos, tais como:

- Fonte de custo (de onde provém o dinheiro, como o seu razão geral)
- Fornecedores (prestadores de serviços externos)
- Serviços de tecnologia (componentes de infraestrutura)
- Aplicativos (os sistemas que sua empresa utiliza)
- Unidades de Negócio (que, em última instância, utilizam os serviços de TI)

Os modelos funcionam criando **alocações** que definem como os custos são transferidos de um objeto para outro. Por exemplo, você pode alocar os custos do data center aos servidores com base no espaço ocupado no rack, depois alocar os custos dos servidores às aplicações com base no consumo de CPU e, por fim, alocar os custos das aplicações às unidades de negócios com base no número de usuários.

**Os drivers** determinam a lógica dessas alocações. Um fator determinante pode ser um simples valor de coluna (como o número de funcionários), outra métrica (como o custo do mês anterior) ou uma fórmula. O modelo calcula automaticamente como os custos se distribuem por cada camada com base nessas regras.

## Métricas

**As métricas** são as medidas que importam para a sua organização. Eles definem o que é calculado e monitorado por meio dos seus modelos.

Existem dois tipos de métricas:

1. **As métricas do modelo** representam valores que circulam pelas alocações. Os mais comuns são:
   - **Custo** : Despesas efetivamente incorridas
   - **Orçamento** : Gastos previstos
   - **Previsão** : Custos futuros estimados

   Você pode criar várias métricas de modelo para acompanhar diferentes aspectos simultaneamente. Por exemplo, você pode alocar tanto os custos reais quanto os valores orçados por meio da mesma estrutura de modelo, o que permite a análise de variações.
2. **Métricas calculadas** são fórmulas que derivam novos valores a partir de métricas do modelo ou tabelas de dados. Exemplos comuns incluem variação (orçamento menos custo), totais acumulados no ano, custos unitários (custo total dividido pelo número de transações) e taxas de crescimento.

As métricas respeitam as regras de formatação (símbolos monetários, casas decimais) e determinam se podem ser somadas entre períodos de tempo ou dimensões organizacionais.

## Relatórios

**Os relatórios** apresentam seus dados modelados e métricas calculadas às partes interessadas de maneira significativa. Eles são a principal interface para acessar as informações do TBM.

Os relatórios podem apresentar os dados da seguinte forma:

- Tabelas com linhas, colunas e valores calculados
- Gráficos e visualizações
- Diagramas de fluxo modelo (diagramas de Sankey) que mostram os caminhos de alocação de custos
- Painéis personalizados que combinam várias visualizações

Os relatórios são interativos — os usuários podem filtrar dados, aprofundar-se nos detalhes, alterar os períodos e exportar os resultados. Você controla quem vê o quê por meio de permissões no nível do relatório e filtros de segurança no nível da linha.

Os relatórios podem extrair dados tanto de tabelas de transformação (dados brutos ou processados) quanto de objetos de modelo (custos alocados), permitindo que você exiba tanto os dados de origem quanto os resultados totalmente alocados na mesma visualização.

## Ambientes

A TBM Studio utiliza três **ambientes** para gerenciar o ciclo de vida do desenvolvimento e garantir a qualidade antes que as alterações cheguem aos usuários finais:

**O Development** é o seu espaço de trabalho pessoal. Quando você retira um documento para editá-lo — seja uma tabela de dados, um modelo ou um relatório —, você está trabalhando no seu ambiente de desenvolvimento. As alterações que você fizer serão aplicadas apenas ao seu espaço de trabalho e não afetarão outras pessoas até que você esteja pronto para compartilhá-las.

**A fase de integração** é onde todas as alterações feitas pelos membros da equipe são reunidas. Quando você registra um documento, ele é movido para a área de preparação e aciona um cálculo. É aqui que você testa e valida as alterações antes de disponibilizá-las aos usuários dos relatórios. Todos os membros da equipe podem acessar o Staging para revisar o trabalho em andamento.

**A produção** é o ambiente de produção que os usuários finais veem. Somente administradores podem promover projetos do ambiente de teste para o de produção. Este ambiente deve conter apenas alterações validadas e testadas. A produção é normalmente atualizada de acordo com um cronograma controlado — diariamente, semanalmente ou mensalmente, dependendo das necessidades da sua organização.

Essa abordagem em três níveis evita que os erros cheguem aos usuários e oferece um ambiente seguro para experimentação e desenvolvimento.

## Como esses conceitos funcionam em conjunto

Aqui está o fluxo de trabalho típico que mostra como esses conceitos se relacionam:

1. **Carregar dados** → Criar tabelas de origem no seu projeto
2. **Transformar dados** → Criar tabelas de transformação para limpar e estruturar os dados
3. **Construir o modelo** → Criar objetos do modelo e definir alocações usando drivers
4. **Definir métricas** → Configurar custo, orçamento e métricas calculadas
5. **Gerar relatórios** → Apresentar custos alocados e métricas às partes interessadas
6. **Gerenciar alterações** → Trabalhar no ambiente de desenvolvimento, validar no ambiente de teste, lançar no ambiente de produção

Cada etapa se baseia na anterior, criando um sistema de total transparência de custos.

## O que vem a seguir

Agora que você já entendeu os conceitos básicos, está pronto para:

- Experimente o [Guia de Início Rápido](qsg.html) para praticar na criação do seu primeiro modelo de custos
- Explore a [visão geral da interface do usuário](tbm-navigation.html) para se familiarizar com a localização de cada elemento
- Aprofunde-se em conceitos específicos na Seção 4 (Conceitos e Arquitetura):
  - **4.2 Arquitetura de dados** para obter detalhes sobre tabelas e transformações
  - **4.3 Arquitetura de modelo** para orientação abrangente sobre modelagem
  - **4.5 Ciclo de vida de compilação e implantação** para as melhores práticas de gerenciamento de ambientes
