---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "A Taxonomia TBM"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Noções básicas sobre TBM"
source_path: "studio/new-uc/concepts-architecture/tbm-taxonomy.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# A Taxonomia TBM

A taxonomia TBM é uma estrutura padronizada para classificar os custos de TI em uma hierarquia em camadas. Ele oferece uma linguagem comum para mapear dados financeiros brutos aos serviços e consumidores que impulsionam os gastos com TI. Pense nisso como um prédio de quatro andares: os custos entram no térreo e vão subindo até chegarem às unidades de negócios que, por fim, os absorvem.

## As Quatro Camadas

A taxonomia padrão do TBM define quatro camadas principais. Cada camada responde a uma pergunta diferente sobre os gastos com TI:

|  |  |  |  |
| --- | --- | --- | --- |
| **Camada** | **Pergunta** | **Exemplos comuns** | **Mapeamento do TBM Studio** |
| **Centros de custo** | De onde vêm os custos? | Hardware, Software, Mão de obra, Instalações, Nuvem | Objeto do modelo de fonte de custo e tabelas do razão geral |
| **Torres de TI** | Como os custos são organizados? | Computação, Armazenamento, Rede, Usuário final, Segurança | Objetos de modelo intermediários (Fornecedores, Serviços de Tecnologia) |
| **Serviços de TI / Aplicativos** | O que a TI oferece? | E-mail, ERP, CRM, análise de dados, plataforma de DevOps | Objeto modelo de soluções |
| **Unidades de negócios** | Quem utiliza serviços de TI? | Vendas, Marketing, Finanças, Operações, P&D | Objeto do modelo de Unidades de Negócio |

## Camada 1: Grupos de custos — De onde os custos se originam

Os grupos de custos representam as categorias financeiras básicas das quais se originam os gastos com TI. Essas entradas correspondem, normalmente, a contas do razão geral ou a faturas de fornecedores. Os grupos de custos respondem à pergunta: “Em que tipo de coisa estamos gastando dinheiro?”

As categorias comuns de grupos de custos incluem:

- **Hardware** : servidores, dispositivos de armazenamento, equipamentos de rede, dispositivos de usuários finais
- **Software** : Software licenciado, assinaturas d SaaS, contratos de manutenção
- **Mão de obra** : equipe interna de TI, prestadores de serviços, serviços terceirizados
- **Instalações** : Espaço para data center, energia elétrica, refrigeração
- **Nuvem e hospedagem** : IaaS,, PaaS, e SaaS – tarifas de consumo
- **Telecomunicações** : Serviços de rede, conectividade à Internet, serviços de voz

Nota:

Por que isso é importante no TBM Studio

No TBM Studio, os grupos de custos são normalmente representados pelo objeto de modelo “Fonte de Custo”, que é alimentado por dados do razão geral importados por meio de um Data Studio A fonte de custo é geralmente o ponto de partida do seu modelo, situando-se na base da cadeia de alocação. O TBM Studio também oferece suporte à aprendizagem automática para mapear automaticamente contas contábeis para categorias padrão de centros de custo.

## Camada 2: Torres de TI — Como os custos são organizados

O grupo IT Towers agrupa os custos em categorias funcionais de tecnologia. Eles representam a infraestrutura e os serviços operados pela TI, independentemente das funções de negócios que os utilizam. Pense nas torres como os “blocos de construção” da prestação de serviços de TI.

As categorias padrão da IT Tower incluem Computação, Armazenamento, Rede, Informática para o usuário final, Desenvolvimento de aplicativos, Gestão de TI e Segurança. As plataformas fazem a ponte entre os custos de insumos e os serviços voltados para o negócio que elas suportam.

Nota:

Por que isso é importante no TBM Studio

No TBM Studio, as IT Towers são representadas como objetos de modelo intermediários entre a Fonte de Custo e as Soluções. Implementações comuns utilizam os objetos "Fornecedor" e "Serviços de Tecnologia" como camada de torre. As alocações de grupos de custos para torres geralmente utilizam a alocação baseada em fatores determinantes, com métricas como número de servidores, consumo de armazenamento ou número de funcionários em tempo integral.

## Camada 3: Serviços e aplicativos de TI — O que a TI oferece

Os serviços de TI representam as funcionalidades voltadas para os negócios que a área de TI oferece. É aqui que os custos passam a ter importância para as partes interessadas sem conhecimentos técnicos. Um líder empresarial pode não se importar com os custos dos servidores, mas se preocupa profundamente com os custos do seu sistema de CRM e se este agrega valor suficiente.

Essa camada mapeia os custos da torre para serviços específicos, como e-mail, planejamento de recursos empresariais (ERP), gestão de relacionamento com o cliente (CRM), plataformas de análise de dados e aplicativos internos personalizados.

Nota:

Por que isso é importante no TBM Studio

No TBM Studio, o objeto de modelo “Soluções” normalmente representa essa camada. Os custos são transferidos dos Serviços de Tecnologia para as Soluções por meio de alocações baseadas em dados de mapeamento entre aplicativos e infraestrutura. A visualização do diagrama do modelo oferece um rastreamento visual de como os custos fluem dos centros de custo, passando pelas torres, até os serviços individuais.

## Camada 4: Unidades de Negócios e Consumidores — Quem utiliza os serviços de TI

A camada final atribui os custos dos serviços de TI às unidades de negócios ou departamentos que os utilizam. Essa é a camada que possibilita o showback e o chargeback — mostrando a cada unidade de negócios quanto está pagando pelos serviços de TI com base no consumo real.

A alocação por unidade de negócios é normalmente determinada por métricas de consumo, como o número de usuários, o volume de transações ou os dados de uso dos aplicativos. O objetivo é criar uma distribuição justa e transparente dos custos de TI que reflita o uso real dos recursos.

Nota:

Por que isso é importante no TBM Studio

No TBM Studio, “Unidades de Negócio” é o objeto de modelo terminal no topo da cadeia de alocação. O fluxo completo de custos segue normalmente o seguinte caminho: Fonte de custo → Fornecedores → Serviços de tecnologia → Soluções → Unidades de negócios. Os relatórios de modelo (visualizações de Sankey) oferecem uma visualização intuitiva desse fluxo de custos completo.

## Como os dados circulam pelas camadas

O poder da taxonomia TBM reside no fluxo progressivo dos custos ao longo de cada camada. Aqui está um exemplo simplificado:

1. **Lançamento no centro de custo** : $10M nos custos de hardware de servidor é lançado a partir do razão geral
2. **Alocação de torres** : $10M é alocado à torre de computação com base na finalidade do servidor (produção, desenvolvimento, testes)
3. **Alocação de serviços** : os custos de computação são alocados aos serviços (CRM recebe $3M, ERP recebe $4M, E-mail recebe $1.5M, Outros recebem $1.5M ) com base nas métricas de uso do servidor
4. **Alocação de usuários** : o recurso “ $3M ” do CRM é alocado às equipes de Vendas ( $1.8M ), Marketing ( $0.9M ) e Suporte ( $0.3M ) com base no número de usuários

Em cada camada, o custo total permanece o mesmo — ele é simplesmente distribuído com maior granularidade. Esse princípio de contenção de custos é fundamental para a TBM e garante que cada centavo seja contabilizado.

## Flexibilidade e personalização

Embora a taxonomia de quatro camadas seja a estrutura padrão, as organizações dispõem de grande flexibilidade quanto à forma de implementá-la:

- **Camadas adicionais** : algumas organizações adicionam camadas (por exemplo, subtorejas ou níveis de serviço) para capturar mais detalhes
- **Categorias personalizadas** : as categorias específicas dentro de cada camada podem ser personalizadas para se adequarem à terminologia e à estrutura da sua organização
- **Modelos simplificados** : organizações menores podem combinar ou omitir camadas para obter um modelo mais simples
- **Várias rotas de alocação** : os custos podem ser alocados por diferentes rotas, dependendo de sua natureza (por exemplo, os custos com mão de obra podem seguir uma rota diferente daquela dos custos com hardware)

Observação: O TBM Studio não impõe uma estrutura taxonômica rígida. Você pode criar objetos de modelo que atendam às necessidades específicas da sua organização. No entanto, alinhar-se à taxonomia padrão do TBM permite a comparação com os padrões do setor e torna o seu modelo mais fácil de entender para os novos membros da equipe.
