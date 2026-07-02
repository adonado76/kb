---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Organize seus gastos com a nuvem"
breadcrumb:
  - "Cloudability Premium"
  - "Configuração"
source_path: "admin/tag-data.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Organize seus gastos com a nuvem

Os dados de faturamento nativos da nuvem são, por natureza, granulares, específicos de cada provedor e otimizados para medição, e não para análise de negócios. Para tornar os custos da nuvem mais compreensíveis para as diversas equipes e perfis dentro da sua prática de gerenciamento de infraestrutura como serviço ( FinOps ), o Cloudability oferece um conjunto de **recursos de** organização que transformam dados brutos de faturamento em visões consistentes e alinhadas aos objetivos de negócios sobre os gastos.

Em linhas gerais, esses recursos ajudam a responder a perguntas como:

- *Quem é o responsável por essa despesa?*
- *Qual é o custo por equipe, aplicativo ou unidade de negócios?*
- *Como podemos garantir a consistência e a governança na atribuição de tags em diversas áreas da empresa?*
- *Como podemos manter os relatórios de custos nos níveis de equipe, departamento e grupo alinhados à medida que nossa hierarquia de relatórios evolui?*
- *Qual é o custo da nuvem por unidade de atividade comercial?*

Cloudability organiza os gastos com nuvem por meio de três recursos complementares:

**[Mapeamento de tags e rótulos](map-tags.html)** – normaliza marcações inconsistentes

O mapeamento de tags e rótulos permite padronizar várias versões da mesma tag em uma única dimensão consistente. Isso garante que tags logicamente equivalentes sejam tratadas como uma única, mesmo quando diferem em formato ou origem. Por exemplo, mapear várias chaves de tag como “Env”, “ENV” e “enviro” para uma única dimensão chamada “Ambiente”.

**[Grupos de contas](account-groups-spend.html)** – estruturam os gastos de acordo com a hierarquia das contas na nuvem (contas vinculadas, projetos, assinaturas)

Os grupos de contas permitem o agrupamento lógico de contas na nuvem de diferentes fornecedores em conjuntos significativos, como ambientes ou departamentos. Ao organizar os gastos no nível da conta, os Grupos de Contas oferecem uma maneira estável e fácil de entender para segmentar os custos em um nível geral.

**[Mapeamentos de negócios](business-tags.html)** – aplicam lógica de negócios personalizada para alocar e categorizar custos

Os Mapeamentos de Negócios oferecem um mecanismo baseado em regras que avalia dados de faturamento e uso e atribui custos às *Dimensões de Negócio,* de acordo com a taxonomia da sua organização. Esses mapeamentos convertem metadados específicos de fornecedores, como tags, nomes de contas, regiões ou serviços, em categorias de negócios otimizadas para análises e tomada de decisões. Isso garante que cada dólar seja classificado e alocado de forma adequada.

Além disso, **[os Mapeamentos Hierárquicos de Negócios](hierarchical-business-mapping.html)** podem ser utilizados para definir e manter relações pai-filho entre Dimensões de Negócios relacionadas, permitindo agregados de custos escaláveis e relatórios consistentes em todos os níveis organizacionais, à medida que as estruturas se alteram.

**[Métricas de Negócios](business-metrics.html)** – aplica cálculos aritméticos personalizados e baseados em regras aos dados de custo e uso da nuvem para gerar métricas financeiras específicas para cada negócio

As métricas de negócios ampliam as métricas de custo padrão d Cloudability, permitindo que você defina cálculos financeiros personalizados que transformam dados brutos de custo e uso da nuvem em indicadores relevantes para os negócios. Por meio de fórmulas configuráveis e lógica condicional, o Business Metrics permite que as equipes modelem taxas de estorno, custos unitários, índices de eficiência e outros KPIs específicos da organização.

- **[Mapeamento de tags e rótulos](../admin/map-tags.html)**
- **[Grupos de contas](../admin/account-groups-spend.html)**
- **[Mapeamento empresarial](../admin/business-tags.html)**
- **[Métricas calculadas](../admin/calculated_metrics.html)**
