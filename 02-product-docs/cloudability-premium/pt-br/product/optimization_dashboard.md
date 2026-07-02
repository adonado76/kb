---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Painel de otimização"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
source_path: "product/optimization_dashboard.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Painel de otimização

## Centro de Otimização

O Dashboard de otimização oferece uma visão centralizada de todas as iniciativas e percepções relacionadas à otimização. Esse centro de comando de otimização fornece

- Uma visão prospectiva das oportunidades para gerar economias em Compromissos e Redimensionamento
- Uma visão retrospectiva do impacto dessas iniciativas e das economias que foram obtidas por meio de compromissos e redimensionamento

## Oportunidades

A página de oportunidades mostra as oportunidades de otimização de recursos (com base nas recomendações de redimensionamento do site Cloudability ) e de compromissos (com base na recomendação de compromisso do site Cloudability ).

## Oportunidades de otimização de recursos

Informações resumidas da superfície de otimização de recursos de suas recomendações de dimensionamento de direitos, sujeitas às seleções de Preferências feitas nas Preferências de dimensionamento de direitos: Dashboard.

A otimização de recursos oferece visibilidade de alto nível sobre o total de oportunidades e fornece links para acessar mais informações sobre as recomendações de dimensionamento em Cloudability.

Juntamente com as próprias oportunidades, o painel de otimização fornece uma pontuação COIN para contextualizar essas oportunidades.

**Pontuação COIN:** COIN (ou Índice de Otimização de Custos) é um método que fornece contexto em torno de uma oportunidade de otimização.

Calculado **como** COIN = 100\*(1 – (Oportunidade de otimização/Gastos)), portanto, um COIN de 100 implicaria em gastos sem nenhuma oportunidade disponível.

Em que:

- **Oportunidade de otimização:** é a soma das economias disponíveis com o redimensionamento, sujeita às preferências selecionadas, visualização e filtros aplicados.

- **Despesa:** refere-se à despesa relevante e otimizável, medida pela métrica de custo relevante com base na sua seleção de preferências. Quando a base de custo sob demanda é selecionada na página de preferências, a pontuação COIN será calculada usando o gasto como medida no custo (lista). Quando a Base de Custo Efetivo é selecionada, a pontuação COIN será calculada usando Custo (Amortizado Ajustado) ou Custo (Amortizado), dependendo da disponibilidade das métricas. Quando o gasto amortizado ajustado não está disponível, o cálculo usa a métrica Custo (amortizado).

O COIN, conforme calculado neste painel, limita-se aos serviços suportados no mecanismo de dimensionamento de direitos do Cloudability, portanto, as despesas com serviços não suportados no mecanismo de dimensionamento de direitos do Cloudability não são incluídas no cálculo do COIN.

**Preferências**

As recomendações de otimização da carga de trabalho exibidas como parte do Painel de Otimização podem ser controladas por meio das preferências. A página de preferências (localizada *em* Configurações>Preferências de dimensionamento>Painel) oferece as seguintes opções, que se aplicam a toda a organização.

**Base de custo efetivo vs. sob demanda** – A base de custo desejada para o conjunto de recomendações apresentado. Embora nem todos os tipos de recomendação tenham uma base de custo “efetiva”, quando a base de custo efetiva é selecionada: A base de custo efetiva será mostrada quando relevante e a base de custo sob demanda será fornecida para ainda oferecer uma visão completa das suas oportunidades de otimização.

Essa seleção também afeta os custos usados para contextualizar as oportunidades em seus cálculos COIN. Quando a base de custo sob demanda é selecionada, a pontuação COIN será calculada usando o custo (lista). Quando a Base de Custo Efetivo é selecionada, a pontuação COIN será calculada usando Custo (Amortizado Ajustado) ou Custo (Amortizado), dependendo da disponibilidade das métricas.

**Recomendações avançadas vs. básicas –** Esta configuração está disponível apenas para clientes Cloudability Premium e permite que as organizações escolham se desejam que o painel seja preenchido com as recomendações de redimensionamento geradas por Cloudability (visíveis na guia “Básico” na página de redimensionamento) ou com as recomendações geradas pelo poderoso mecanismo de redimensionamento de Turbonomic (visíveis na guia “Avançado”)

**Preferências** de recomendações básicas – Esta seção permite que a organização personalize ainda mais o conjunto básico de recomendações quando a opção acima é selecionada. As recomendações avançadas podem ser refinadas por meio de políticas, em vez dessas preferências no painel.

- **Período de análise de 10 vs 30 dias – Os usuários podem selecionar se desejam ver recomendações com base na utilização de recursos nos últimos 10 dias ou nos últimos 30 dias.**
- **Incluir recomendações adiadas –** as organizações podem optar por ver o panorama completo das oportunidades (incluindo aquelas que decidiram “adiar” e que podem não ser viáveis no curto prazo) ou concentrar-se nas oportunidades mais viáveis, excluindo as recomendações adiadas.
- **Chaves de tag ou dimensões** de negócios – estão presentes nos menus suspensos “dividir por” em cada widget.

## Oportunidades de compromisso

A seção de oportunidades de compromisso fornece uma visão geral das economias disponíveis por meio de descontos baseados em compromisso.

Observação: as oportunidades de compromisso têm como padrão compromissos de 3 anos e os descontos associados no momento.

Assim como a otimização de recursos, também está disponível uma pontuação COIN baseada na otimização de taxas.

## Economias realizadas

A economia realizada mostra o impacto das atividades de economia de custos, tanto nas atividades de recursos quanto nas de rightsizing.

Um intervalo de datas selecionável na parte superior da página de economia realizada permite que os usuários personalizem o intervalo de datas.

- Para a economia de recursos realizada, o intervalo de datas selecionado filtra a data da ação (quando o site Cloudability detecta uma alteração na configuração do recurso), de modo que somente o impacto das ações
- Para economias de compromisso realizadas, o intervalo de datas selecionado fornece uma janela de relatório para as economias obtidas durante esse intervalo. Porque diferentes provedores fornecem diferentes níveis de dados:
- Para economias de compromisso AWS e Azure : as economias realizadas para o intervalo selecionado são calculadas com base na diferença entre o que você teria pago (o custo equivalente sob demanda do uso de recursos) menos o que você realmente pagou (custo (ajustado amortizado) que inclui compromissos).
- Para uma poupança de compromisso d GCP : a poupança é reportada a partir da carteira de compromissos.

Além da data, as páginas de economia realizada podem ser filtradas por serviço, conta, grupo de contas ou região.

**Recurso**

A economia de recursos realizada é construída sobre a funcionalidade de ROI de redimensionamento, mostrando o impacto das recomendações e ações rastreadas no ROI de redimensionamento.

**Confirmação**

As superfícies de economia realizada do compromisso resumem as informações relacionadas à economia obtida pela comparação do custo real do uso com base na cobertura do compromisso e nos descontos relativos ao preço On Demand

## Explorador COIN

A terceira guia no Painel de Otimização oferece uma experiência dinâmica de relatórios para a Pontuação COIN com a granularidade desejada. Os usuários podem selecionar os campos desejados, incluindo Tags ou Mapeamentos de Negócios, para visualizar e comparar suas pontuações COIN

O cálculo do COIN e as métricas utilizadas são descritos acima e são consistentes entre a guia Oportunidade e a guia Explorador.

O COIN Explorer permite que os usuários selecionem dinamicamente o período de análise ou a base de custo (substituindo a página de preferências) e respeita a preferência selecionada para incluir ou excluir recomendações adiadas ou a fonte da recomendação (quando relevante).

## Tópicos adicionais

**Permissões**

O painel de otimização não tem permissões independentes associadas a ele. Os insights desse conjunto de recursos são criados com base na funcionalidade que abrange Rightsizing, Rightsizing ROI e Commitments, juntamente com os dados de custo subjacentes. Para utilizar efetivamente essa funcionalidade, você precisa das permissões associadas a esses recursos subjacentes.

**Como funcionam as visualizações**

As visualizações funcionarão de maneiras diferentes com partes diferentes do painel de otimização, com base em como as visualizações funcionam com os dados subjacentes.

Por exemplo, as visualizações baseadas em dimensões de negócios podem ser usadas com o painel Otimização, mas como essas visualizações não são compatíveis com as páginas de recomendações de compromisso ou portfólio, os aspectos das páginas de oportunidades de compromisso e de economia realizada não serão preenchidos.

**Exportando dados**

Os dados no painel de otimização podem ser extraídos diretamente das APIs de origem ( E.g., o redimensionamento, os compromissos ou os pontos finais de custo), mas as APIs não estão disponíveis para a pontuação COIN pré-calculada.

Os dados do COIN Explorer podem ser exportados para csv com a granularidade desejada na página do COIN Explorer.
