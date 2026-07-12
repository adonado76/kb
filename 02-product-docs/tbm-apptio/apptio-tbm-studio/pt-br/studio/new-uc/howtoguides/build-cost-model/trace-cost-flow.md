---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Acompanhar os fluxos de custos ao longo do modelo"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar modelos de custos"
  - "Modelagem avançada"
source_path: "studio/new-uc/howtoguides/build-cost-model/trace-cost-flow.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Acompanhar os fluxos de custos ao longo do modelo

## Objetivo

Use o diagrama do modelo e os recursos de detalhamento para rastrear os fluxos de custos e responder à pergunta: "De onde veio esse custo?"

## Quando utilizar este procedimento

Utilize o rastreamento de custos quando:

- Uma parte interessada pergunta por que uma unidade de negócios ou um serviço recebeu um determinado valor de custo
- Você observa resultados inesperados na alocação e precisa identificar a causa
- Você precisa verificar se os custos estão sendo alocados da maneira correta
- Você está analisando custos não alocados
- É necessário auditar o caminho de alocação para fins de conformidade ou revisão financeira

**Pré-requisitos**

- O modelo foi construído e calculado (custos distribuídos por meio de alocações)
- Você sabe qual objeto de modelo ou valor de custo deseja rastrear

## Tempo estimado

5 a 15 minutos (dependendo da complexidade do modelo)

## Entendendo as visualizações do modelo

O TBM Studio oferece três visões complementares para acompanhar os fluxos de custos:

- Modelador de Objeto Único: Exibe os controladores e as alocações de uma tabela por vez. Ideal para configuração detalhada e visibilidade imediata das redes a montante e a jusante.
- Visualização do diagrama: exibe todos os objetos do modelo e suas conexões em um layout visual. Ideal para compreender a estrutura completa do modelo e a navegação.
- Relatório do modelo (visualização de Sankey): Apresenta os fluxos de custos em uma visualização em camadas de fácil compreensão. Ideal para a comunicação com as partes interessadas e o rastreamento de ponta a ponta.

## Método 1: Usando a visualização do diagrama

A visualização em diagrama oferece uma visão geral de todo o modelo de custos, semelhante a um diagrama do Visio.

1. No Project Explorer, expanda o modelo e clique no diagrama do modelo (ou acesse-o pelo menu Exibir).
2. O diagrama exibe todos os objetos do modelo como retângulos, interligados por linhas de alocação. A largura de cada linha é proporcional ao valor que passa por ela.
3. Use os controles de zoom e panorâmica para navegar por modelos grandes.
4. Clique em qualquer objeto modelo (retângulo) para abrir o Modelador de Objeto Único dessa tabela, exibindo suas entradas e saídas.
5. Para rastrear um caminho de alocação específico, clique na sequência: Origem de custo → Fornecedores → Serviços de tecnologia → Soluções → Unidades de negócios.

## Método 2: Usando o Modelador de Objeto Único

O Modelador de Objeto Único oferece um rastreamento detalhado das entradas e saídas de uma tabela específica.

1. No Project Explorer, clique no objeto do modelo que deseja rastrear e clique na etapa Modelo.
2. A tela exibe: a coluna da esquerda mostra os drivers de entrada e as alocações; a parte central mostra o objeto atual; e a coluna da direita mostra as alocações de saída.
3. Clique em qualquer alocação recebida (lado esquerdo) para ver qual fonte está contribuindo com o custo e quais critérios de correspondência/ponderação são aplicados.
4. Clique em qualquer alocação de saída (lado direito) para ver para onde os custos são direcionados e qual método de distribuição é utilizado.
5. Clique em um objeto de destino para acessar a visualização do modelador desse objeto, permitindo que você continue a rastrear os elementos a jusante.

## Método 3: Aprofundando-se nos detalhes

Para um rastreamento detalhado, use o recurso de detalhamento para visualizar os detalhes da alocação no nível da linha.

1. Na visualização da etapa do modelo, clique no ícone de menu (≡) na tabela que você deseja explorar.
2. Clique em “Drill Down” e selecione uma coluna (por exemplo, Data Center, Nome do fornecedor, Pool de custos).
3. A visualização agora mostra cada valor único nessa coluna com os custos associados.
4. Clique em um valor específico (por exemplo, um determinado data center) para ver apenas as alocações de/para esse valor.
5. Para voltar à visualização em tabela, clique no ícone da seta de retorno no canto superior esquerdo do nível.

## Exemplo: Identificação de um custo inesperado

**Cenário** : O responsável por uma unidade de negócios pergunta por que recebeu uma conta de US$ 50.000 em custos de rede, quando esperava um valor menor.

1. Abra o objeto do modelo “Unidades de Negócio” e localize a unidade de negócio em questão.
2. Analise as alocações recebidas para verificar quais objetos a montante contribuíram para os custos de rede.
3. Clique na alocação dos Serviços de Tecnologia para ver os critérios de seleção e a ponderação.
4. Navegue para cima até o objeto “Serviços de Tecnologia” e volte até “Fornecedores”.
5. Continue rastreando até identificar a fonte de custo original e compreender o caminho de alocação.

## Boas Práticas

- Use a visualização do diagrama para integrar novos membros da equipe e ministrar treinamentos
- Use os recursos de rastreabilidade para identificar alocações inesperadas antes de modificar o modelo
- Verifique os custos não alocados após alterar a lógica de correspondência — eles costumam indicar problemas de configuração
- Registre os caminhos de alocação de documentos para fins de auditoria utilizando relatórios modelo

## Tarefas relacionadas

- [Criar modelos de relatórios](create-model-rep.html)
- [Tratar custos não alocados](handle-unallocated-costs.html)
- [Veja o diagrama do modelo](view-model-diagram.html)

**Tópico principal:** [Modelagem avançada](../../../../studio/new-uc/howtoguides/build-cost-model/adv-model.html)
