---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Metodologias de alocação de custos"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Noções básicas sobre TBM"
source_path: "studio/new-uc/concepts-architecture/cost-allocation-method.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Metodologias de alocação de custos

A alocação de custos é o processo de distribuir os custos desde a sua origem até os serviços e consumidores que deles se beneficiam. A escolha da metodologia de alocação correta é uma das decisões mais importantes na implementação do TBM — ela determina o grau de precisão com que o seu modelo de custos reflete a realidade.

## Alocação direta

**Definição**

A alocação direta atribui custos que são clara e exclusivamente atribuíveis a um único alvo. Não é necessário compartilhar ou dividir, pois a relação entre custo e consumidor é de um para um.

**Quando usar** 

- Um custo é atribuído a um único aplicativo, serviço ou unidade de negócios
- Uma fatura de fornecedor é específica para um cliente
- Um recurso é utilizado exclusivamente por uma entidade

**Vantagens e desvantagens**

|  |  |
| --- | --- |
| **Vantagens** | **Desvantagens** |
| Máxima precisão — sem necessidade de estimativas | Aplica-se apenas a recursos dedicados |
| Fácil de explicar e defender | A maioria dos custos de TI é compartilhada, o que limita sua aplicabilidade |
| Não são necessários dados do motorista | Não é compatível com infraestrutura compartilhada |

**Exemplo**

Um servidor de banco de dados dedicado que executa apenas o aplicativo de CRM custa $5,000/month em hospedagem. Esse custo é alocado diretamente ao serviço de CRM, sem necessidade de divisão.

Nota:

**Por que isso é importante no TBM Studio**

No TBM Studio, a alocação direta é implementada por meio de uma correspondência um-para-um na configuração de alocação. Quando o registro de origem possui um identificador único que se mapeia diretamente para um único destino, os custos são transferidos sem divisão. Isso é configurado no Model Studio, no Single Object Modeler, utilizando condições de correspondência exata em campos como ID da aplicação ou ID do fornecedor.

## Alocação indireta

**Definição**

A alocação indireta distribui os custos que são compartilhados entre vários destinatários. Como o benefício em termos de custo beneficia mais de um consumidor, é necessário um método para determinar a parcela justa de cada um deles.

**Quando usar** 

- A infraestrutura é compartilhada entre várias aplicações ou unidades de negócios
- Os custos não podem ser atribuídos a um único consumidor (por exemplo, rede compartilhada, instalações de data center)
- Uma equipe presta vários serviços simultaneamente

**A necessidade de fatores determinantes da alocação**

A alocação indireta requer um fator de repartição — um indicador mensurável que determina como distribuir os custos entre os consumidores. A qualidade da sua alocação indireta está diretamente ligada ao grau em que o seu fator determinante reflete os padrões reais de consumo. Escolher o piloto certo é tanto uma arte quanto uma ciência.

**Exemplo**

Um data center compartilhado implica um $500,000/month e em termos de infraestrutura (energia, refrigeração, espaço físico). Esse custo é alocado aos conjuntos de servidores instalados no centro de dados com base no espaço de rack ocupado. Se o conjunto de servidores CRM ocupar 30% do espaço do rack, ele receberá US$ 150.000 dos custos das instalações.

## Alocação baseada em drivers

**O que é um driver?**

Um driver é uma métrica mensurável que determina como os custos compartilhados são distribuídos entre os alvos. Os fatores determinantes representam a relação causal entre um custo e seus consumidores — eles respondem à pergunta: “Por que esse consumidor arca com essa parcela do custo?”

**Tipos comuns de drivers**

|  |  |  |
| --- | --- | --- |
| **Tipo de motorista** | **Descrição** | **Ideal para** |
| Número de funcionários / ETI | Número de funcionários ou equivalentes em tempo integral | Informática para usuários finais, central de atendimento, licenças de " SaaS " |
| Volume de transações | Número de transações processadas | Hospedagem de aplicativos, middleware, serviços de processamento |
| Consumo de armazenamento | GB ou TB de espaço de armazenamento utilizado | Infraestrutura de armazenamento, serviços de backup |
| CPU / Utilização de recursos de computação | Núcleos da CPU, horas de processamento ( vCPUs, ) ou horas de computação consumidas | Infraestrutura de servidores, computação em nuvem |
| Número de usuários | Número de usuários ativos de um serviço | Licenciamento de aplicativos, serviços por usuário |
| Receita / Orçamento | Indicadores financeiros da entidade consumidora | Alocação geral de despesas gerais (menos precisa) |

**Escolhendo os drivers adequados**

  

O melhor motorista tem três qualidades:

- **Relevância causal:** O fator determinante deve refletir o que realmente causa o custo. O número de servidores é um indicador mais relevante para os custos de computação do que o número de funcionários.
- **Disponibilidade dos dados:** Os dados do motorista devem estar disponíveis de forma confiável a cada período. Um driver perfeito que você não pode adquirir não serve para nada.
- **Proporcionalidade:** O motor deve refletir o consumo relativo. Se o Aplicativo A utiliza três vezes mais recursos de computação que o Aplicativo B, o valor do seu driver deve ser aproximadamente três vezes maior.

**Considerações sobre a qualidade dos dados dos motoristas**

- Os controladores devem ser numéricos. Valores não numéricos em uma coluna de ponderação causam falhas na alocação no TBM Studio.
- Valores negativos para o driver não são suportados e farão com que a alocação falhe.
- A falta de dados de controladores para uma entidade de destino resulta em custos não alocados — esses custos permanecem na fonte até que sejam resolvidos.
- Os dados dos motoristas devem ser atualizados a cada período para refletir os padrões de consumo atuais.

Nota:

Por que isso é importante no TBM Studio

No TBM Studio, os drivers são configurados no Modelador de Objetos Únicos do Model Studio. Cada alocação especifica uma métrica de origem, uma coluna de ponderação (o fator determinante) e condições de correspondência que vinculam as linhas de origem às linhas de destino. Estão disponíveis três opções de ponderação: Tabela (valores do conjunto de dados de destino), Métrica (proporcional à alocação de outra métrica) e Outro fator (valores de uma tabela de fatores separada). Verifique sempre a qualidade dos dados dos motoristas antes de executar as alocações.

## Custeio Baseado em Atividades (ABC)

**Visão geral do conceito**

O Custeio Baseado em Atividades distribui os custos com base nas atividades específicas realizadas para prestar um serviço. Em vez de utilizar um simples índice (como o número de funcionários), o ABC identifica as atividades específicas envolvidas na prestação de serviços e atribui custos com base no volume de cada atividade consumida.

**Quando o método ABC é adequado**

- Vocês oferecem serviços muito variados, com diferentes estruturas de custos
- Os fatores simples não refletem com precisão a origem dos custos
- Você precisa de um cálculo de custos por nível de serviço muito preciso para tomar decisões de precificação

## Compromissos entre complexidade e precisão

O método ABC oferece a maior precisão na alocação, mas exige um esforço significativamente maior em termos de coleta de dados e manutenção. Para a maioria das organizações, a alocação baseada em fatores determinantes oferece precisão suficiente com muito menos custos indiretos. Considere o método ABC para os seus serviços de maior custo ou mais críticos e utilize métodos mais simples nos demais casos.

Dica:

Comece com métodos de alocação mais simples e aumente o nível de sofisticação ao longo do tempo. Muitas organizações começam com indicadores baseados no número de funcionários ou mesmo na receita e, à medida que sua prática de gerenciamento baseado em objetivos (TBM) amadurece, passam gradualmente a utilizar indicadores mais precisos, baseados no consumo. O TBM Studio facilita esse processo — você pode alterar os drivers sem precisar reestruturar o modelo.
