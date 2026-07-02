---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Tarefas comuns de relatórios e padrões de uso"
breadcrumb:
  - "Billing"
  - "Trabalhando com relatórios de faturamento"
source_path: "boit/billing/work-bill-reports/common-rep-ratasks.html"
images:
  - "boit/billing/work-bill-reports/clip_image001_-162976121.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Tarefas comuns de relatórios e padrões de uso

Independentemente da edição, os usuários tendem a realizar as mesmas ações principais nos relatórios de faturamento. Esta subseção concentra-se em padrões, em vez de controles específicos da interface do usuário.

## Filtragem e foco

Tarefas comuns:

- Filtre para um único período ou um pequeno intervalo de períodos.
- Filtre para um consumidor específico (por exemplo, uma unidade de negócios).
- Filtre por uma oferta ou serviço específico.
- Combine filtros (por exemplo, um consumidor e um serviço ao longo de três meses).

Dicas de uso:

- Comece com uma abordagem ampla e, à medida que surgirem perguntas, concentre-se na área de interesse.
- Salve combinações de filtros comumente usadas se o front-end suportar visualizações salvas ou favoritos.

## Detalhamento e rastreabilidade

Os usuários frequentemente precisam aprofundar-se de um resumo para os detalhes:

- De uma cobrança total pelo consumidor à lista de serviços que geram essa cobrança.
- De um total de serviços aos itens de linha subjacentes ou detalhamento em nível de domínio (por exemplo, contas na nuvem, aplicativos ou dispositivos).
- De uma visão do período atual para períodos anteriores, a fim de compreender as tendências.

Dicas de uso:

- Use ações de treino para evitar exportações desnecessárias.
- Para investigações repetidas (por exemplo, sempre investigando um serviço específico), considere documentar esse caminho em procedimentos locais ou treinamentos internos.

## Comparando períodos

Os relatórios de faturamento são frequentemente usados para responder à pergunta “o que mudou neste mês?”

Abordagens típicas:

- Use colunas de comparação no mesmo relatório:
  - Período atual vs. período anterior.
  - Período atual vs. mesmo período do ano passado.
- Use visualizações de gráficos ou tabelas que mostrem vários períodos no mesmo eixo.
- Exporte dois períodos e compare externamente quando necessário.

Dicas de uso:

- Concentre-se em movimentos significativos por valor ou por porcentagem, não em pequenas variações.
- Use o faturamento em combinação com o cálculo de custos quando as alterações forem motivadas por mudanças no modelo de custos subjacente.

## Exportando dados

As exportações são utilizadas para:

- Análise local (planilhas, gráficos personalizados).
- Compartilhando com pessoas que não fazem login no front-end.
- Alimentação de ferramentas externas ou sistemas financeiros.

Padrões comuns de exportação:

- Exporte relatórios no formato de fatura para:
  - Consumidores individuais.
  - Grupos de consumidores com um gerente comum.
- Exporte relatórios detalhados quando for necessária uma análise mais aprofundada ou uma rotação personalizada.
- Exporte relatórios de diário no layout exato exigido pelo departamento financeiro.

![](../../../../../../03-media/apptio-billing/boit/billing/work-bill-reports/clip_image001_-162976121.png)

Fig. #: Menu Exportar mostrando opções para exportar o relatório de faturas para Excel, PDF, e-mail e assinatura de e-mail.

Dicas de uso:

- Mantenha um pequeno conjunto de layouts de exportação “oficiais” que o departamento financeiro espera e evite criar várias variantes ligeiramente diferentes.
- Se você estiver exportando a mesma visualização personalizada repetidamente, considere adicionar um relatório dedicado ou uma visualização salva.

## Reconciliação com custos e finanças

Os relatórios de faturamento geralmente ficam no meio do trabalho de reconciliação:

- **Para Cálculo de Custos**
  - Some as cobranças por consumidor e compare com o custo recuperável do Cálculo de Custos.
  - Investigue as lacunas:
    - Intencional (por exemplo, subsídio ou margem planejada).
    - Não intencional (por exemplo, consumo ausente ou taxas incorretas).
- **Para financiar**
  - Compare a saída do diário de faturamento com os lançamentos contábeis lançados.
  - Certifique-se de que:
    - Os totais estão alinhados.
    - Os segmentos de consumidores ou centros de custos correspondem.
    - Qualquer tratamento de moeda estrangeira ou câmbio segue as regras acordadas.

Documentar as etapas de reconciliação ajuda a evitar a repetição das mesmas investigações todos os meses.
