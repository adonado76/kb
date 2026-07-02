---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Objetos e relações do modelo"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura do modelo"
source_path: "studio/new-uc/concepts-architecture/model-architecture/model-object-relationship.html"
images:
  - "resources/images/studio_images/full-tbm-flow.png"
  - "resources/images/studio_images/infrastructure-flow.png"
  - "resources/images/studio_images/labor-cost-flow.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Objetos e relações do modelo

## O que é um objeto modelo?

Um objeto de modelo é o elemento fundamental de um modelo de custos. Pense nisso como um recipiente que armazena dados de custos em um determinado nível da estrutura de custos da sua organização.

Cada objeto de modelo é associado a uma tabela de transformação no arquivo ` Data Studio `. A tabela de transformação fornece os dados brutos (linhas de registros de custos, informações de fornecedores, detalhes da solicitação, etc.), e o objeto modelo define como esses dados participam do mecanismo de alocação. Adicionar uma etapa de modelo a um pipeline de transformação de tabela é o que o torna um objeto de modelo.

Nota:

**Conceito-chave: Objetos como contêineres**

Um objeto modelo não armazena custos de forma independente. Ele faz referência a uma tabela de transformação e adiciona um comportamento de alocação a ela. A tabela de transformação é o “alimentador” — o objeto modelo é o “papel” que os dados desempenham no fluxo de custos.

**Principais propriedades de um objeto modelo:**

- **Nome:** Um rótulo descritivo (por exemplo, “Fonte de custo”, “Fornecedores”, “Unidades de negócios”)
- **Fonte dos dados:** a tabela de transformação que fornece os dados subjacentes
- **Métricas:** As métricas modeladas nas quais participa (Custo, Orçamento, Previsão, etc.)
- **Fatores determinantes:** fatores de unidade ou de alocação que contribuem para o objeto
- **Alocações:** Regras que distribuem custos para outros objetos a jusante
- **Descrição:** Documentação sobre a finalidade e o uso pretendido do objeto

## Tipos de objetos por função

Embora o TBM Studio não imponha rótulos rígidos de “tipo” aos objetos do modelo, esses objetos se enquadram naturalmente em três categorias com base em sua posição no fluxo de custos:

|  |  |  |
| --- | --- | --- |
| **Função do objeto** | **Descrição** | **Exemplo** |
| Objetos de origem | De onde vêm os custos. Essas tabelas ficam na base do modelo e recebem dados diretamente do razão geral, do faturamento ou de outras fontes financeiras. | Fonte de custo, Valores reais do Razão |
| Objetos intermediários | Pontos de referência ou percursos para alocação de custos. Os custos passam por esses objetos em seu caminho até os destinos finais. Elas acrescentam uma camada de categorização ou agrupamento. | Fornecedores, Mão de obra, Centros de TI, Serviços de tecnologia |
| Objetos-alvo | Destinos de custo final. Essas entidades são as que, em última instância, “assumem” os custos para fins de relatórios e estornos. | Unidades de Negócios, Aplicativos, Soluções |

O mesmo objeto pode ser tanto um destino (recebendo custos de etapas anteriores) quanto uma fonte (alocando custos para etapas posteriores). Por exemplo, o objeto Fornecedores recebe os custos da Fonte de Custos e, em seguida, os aloca aos Serviços de Tecnologia. É essa dupla função que possibilita as cadeias de alocação em múltiplos níveis.

## Relações entre objetos

Os objetos do modelo são conectados por meio de alocações. Ao criar uma alocação do Objeto A para o Objeto B, você estabelece uma relação que diz: “Parte ou a totalidade dos custos do A deve ser transferida para o B, distribuída de acordo com regras específicas.”

**Características do relacionamento:**

- **Direção:** Os custos fluem sempre da origem para o destino — do objeto “De” para o objeto “Para”. O gráfico do modelo não deve conter ciclos (dependências circulares).
- **Um-para-muitos:** Um único objeto de origem pode ser atribuído a vários objetos de destino. Por exemplo, uma fonte de custo pode ser alocada simultaneamente às categorias “Mão de obra”, “Fornecedores” e “Instalações”.
- **Muitos para um:** vários objetos de origem podem ser mapeados para o mesmo destino. Tanto os fornecedores quanto a mão de obra podem alocar custos aos serviços de tecnologia.
- **Navegabilidade:** No Modelador de Objeto Único, clicar em um objeto de destino leva você à configuração desse objeto, permitindo que você acompanhe a cadeia de alocação de forma interativa.

## Hierarquia de modelos

Um modelo bem elaborado organiza os objetos em uma hierarquia que reflete a estrutura de custos da sua organização. O mecanismo de alocação do TBM Studio processa essa hierarquia de baixo para cima, distribuindo os custos dos objetos de origem através das camadas intermediárias até os destinos finais.

**Padrões típicos de hierarquia**

**Padrão 1: Fluxo completo da taxonomia TBM**

![Fluxo da TBM](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/full-tbm-flow.png)

**Modelo 2: Fluxo de custos de mão de obra**

![Fluxo de custos de mão de obra](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/labor-cost-flow.png)

**Padrão 3: Fluxo de custos de infraestrutura**

![Fluxo de custos de infraestrutura](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/infrastructure-flow.png)

Nota:

**Melhores práticas: Projeto de hierarquia**

Mantenha sua hierarquia o mais simples possível. Cada camada adicional aumenta a complexidade e pode dificultar o rastreamento de custos. A maioria das organizações utiliza de 3 a 5 camadas. Comece de forma simples e adicione camadas intermediárias apenas quando elas forneçam informações significativas.

Garanta uma granularidade consistente dentro de cada objeto. Se uma linha no seu objeto Fornecedor representa um único fornecedor, todas as linhas devem representar fornecedores únicos — não misture dados de nível de fornecedor e de nível de fatura no mesmo objeto.
