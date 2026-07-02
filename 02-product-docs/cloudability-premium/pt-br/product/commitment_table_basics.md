---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Noções básicas sobre a tabela de compromissos"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Noções básicas sobre gerenciamento de compromissos no Cloudability"
source_path: "product/commitment_table_basics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Noções básicas sobre a tabela de compromissos

## Propósito

O objetivo deste documento é apresentar como os metadados são exibidos na expectativa das páginas de compromisso e explicar os dados mostrados nas tabelas de compromisso do Cloudability e como ler, filtrar e exportá-los de forma consistente nas páginas (Manager, Portfolio, Recommendations). Esta é uma referência prática para colunas, classificação e interpretação.

## Arquitetura da informação

Os metadados de compromissos, recomendações e grupos aparecem em três padrões de interface do usuário no aplicativo:

**Tabela** - Uma grade tabular com colunas e grupos de colunas (cabeçalhos) que organizam campos relacionados para facilitar a comparação.

**Painel de detalhes (gaveta direita)** - Um painel deslizante que exibe propriedades de nível de campo e ações contextuais para a linha ou o cartão selecionado.

**Cartão de resumo** - Um cartão no nível da página que apresenta as principais métricas ou atributos relevantes para a exibição atual (geralmente usado na página Recomendações).

Por que isso é importante: os padrões de exibição padronizados tornam as informações digitalizáveis, alinham a terminologia da Central de Ajuda com a interface do usuário do produto e garantem relatórios e análises consistentes entre os provedores.

## Onde você verá os componentes da interface do usuário

**Commitment Manager** - Visão geral em nível agregado com um gráfico de série temporal de custos e economias de compromisso. No futuro, adicionaremos uma tabela Monthly Rollup para resumir os custos periodizados mostrados no gráfico.

**Portfólio de compromissos** - Um inventário tabular de compromissos. Cada linha inclui uma ação de Detalhes (alinhada à direita) que abre o Painel de Detalhes (Gaveta Direita) para mostrar campos não presentes na tabela.

**Recomendações de compromisso** - Uma visão resumida que reflete as interações do portfólio. A ação Detalhes abre uma página de detalhes dedicada (em vez da gaveta). Um cartão de resumo destaca as premissas da recomendação (prazo, escopo, compartilhamento, pagamento) e os KPIs modelados, como custo e economia líquida.

Por que isso é importante: estamos definindo uma nomenclatura consistente para esses componentes da interface do usuário (Tabela, Painel de detalhes, Cartão de resumo, Página de detalhes) para explicar com mais eficiência os conceitos posteriormente nesta documentação.

## Referência de dados

A tabela a seguir fornece uma referência para cada campo mostrado nas páginas de compromisso.

*Detalhes do compromisso*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Campo** | **AWS** | **GCP** | **AZURE** | **Notas** |
| ID do compromisso | ID | ID | — | Identificador exclusivo para o registro de compromisso. |
| Categoria | Categoria | Categoria | — | Categoria independente de fornecedor (por exemplo, recursos vs. gastos). |
| Serviço | Serviço | Serviço | — | Família de serviços ou produtos (por exemplo, EC2, GCE, RDS ). |
| Região | Região / Zona de disponibilidade | Região | — | Localização de um recurso. |
| Termo | Termo | Termo | — | Normalmente, 1 ou 3year. |
| Opção de pagamento / frequência de cobrança | Opção de Pagamento | — | — | AWS : Não/Parcial/Tudo adiantado. GCP : na prática, não há pagamento inicial para a maioria dos compromissos. |
| Custo inicial | Custo inicial | — | — | Reconhecido por base (caixa vs. ajustado). |
| Valor do compromisso por hora | Valor por hora | Valor por hora | — | De acordo com o compromisso, por exemplo, GCP. Os CUDs de recursos mostram vCPU/Memory/SSD/GPU quantidades; AWS EC2. O RI mostra contagem/quantidade. |
| Taxa de desconto da lista de compromissos | — | Taxa de poupança da lista | — | Taxa de desconto publicada para o item. |
| OS | OS | — | — | Aplicável a alguns compromissos de computação. |
| Ocupação | Ocupação | — | — | Locação dedicada vs. compartilhada ( AWS ). |
| Classe | Classe | — | — | Padrão vs. conversível (quando aplicável). |
| Compartilhamento | ISF | — | — | Indicador de flexibilidade/compartilhamento do tamanho da instância ( AWS ). |
| Unidades (obsoleto) | Unidades | — | — | Não é mais necessário. |
| Compartilhamento de região Bool | MultAZ | — | — | Indica o comportamento de compartilhamento do multiAZ/region ( AWS ). |
| Tipo de mecanismo | Tipo de mecanismo | — | — | Aplicável a determinados produtos de banco de dados/pesquisa. |

*Conta e propriedade*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Campo** | **AWS** | **GCP** | **AZURE** | **Notas** |
| Nome da conta do pagador | Conta do pagador | Conta de cobrança | — | Proprietário da fatura/contexto de faturamento. |
| ID da conta do pagador | — | ID da conta de cobrança | — | Identificador da conta de cobrança ( GCP ). |
| Nome da conta vinculada | Conta vinculada | Projeto | — | Conta/projeto de consumo. |
| ID da conta vinculada | — | ID de Projeto | — | Identificador do projeto ( GCP ). |

*Desempenho ( NonKPI Fields)*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Campo** | **AWS** | **GCP** | **AZURE** | **Notas** |
| custo do compromisso [relatado | Custo | Custo | — | Custo total dos compromissos dentro do escopo/período selecionado. |
| custo do compromisso [Pago | Custo pago | Custo pago | — | Reconhecido por base (caixa vs. ajustado). |
| custo do compromisso [Lifetime] | Custo vitalício | Custo vitalício | — | Custo cumulativo durante a vida útil do compromisso. |
| Compromisso relatado Economia líquida | Economia líquida | Economia líquida vitalícia | — | Pode haver diferenças na nomenclatura; reflete a distinção entre “período” e “tempo de vida” no site GCP. |
| Taxa de poupança de compromisso relatada | Taxa de economia | Taxa de economia | — | Taxa de economia atual para o escopo da linha (não é um KPI de portfólio). |
| Utilização do compromisso relatado | Utilização | Utilização | — | Utilização combinada para a linha (não é um KPI de portfólio). |
| custo do compromisso [restante | Custo restante | Custo restante | — | Exposição a termo até a expiração. |
| Economia líquida não realizada informada | Poupança líquida não realizada | — | — | Economias potenciais ainda não realizadas devido à subutilização. |
| Por hora OnDemand Compromisso | — | OnDemand compromisso | — | GCP valor de referência para comparação (quando disponível). |
| Economia líquida por hora | — | Economia líquida (por hora) | — | Quando exposto em granularidade horária. |
| Ponto de equilíbrio | — | Ponto de equilíbrio (meses) | — | Meses para atingir o ponto de equilíbrio com o uso atual. |

*SubQuantities (CUDs de recursos do GCP )*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Campo** | **AWS** | **GCP** | **AZURE** | **Notas** |
| Valor do compromisso por hora - Núcleos | — | Valor do compromisso por hora (núcleos) | — | vCPU quantidade comprometida. |
| Utilização - Núcleos | — | Utilização (núcleos) | — | vCPU utilização da quantidade comprometida. |
| Valor do compromisso por hora - Memória | — | Valor do compromisso por hora (memória) | — | Quantidade de memória ( GiB ) comprometida. |
| Utilização - Memória | — | Utilização (memória) | — | Utilização de memória da quantidade confirmada. |
| Valor do compromisso por hora - SSD | — | Valor do compromisso por hora (SSD) | — | Quantidade de SSD comprometida. |
| Valor do compromisso por hora - GPU | — | Valor do compromisso por hora (GPU) | — | Quantidade de GPU comprometida. |

*Detalhes da recomendação (quando aplicável)*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Campo** | **AWS** | **GCP** | **AZURE** | **Notas** |
| Recomendação SubType | Família de instâncias / Nó / Tipo de instância | Tipo de máquina | — | Forma/família proposta para a recomendação. |
| Recomendação mensal Crédito SUD | — | Recomendação Crédito de desconto por uso sustentado (estimativa mensal) | — | GCP estimativa específica. |
| Crédito SUD de recomendação vitalícia | — | Recomendação Crédito de desconto por uso sustentado (vida útil estimada) | — | GCP estimativa específica. |

*Status e interface do usuário*

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Campo** | **AWS** | **GCP** | **AZURE** | **Notas** |
| Estado | Estado | — | — | Estado atual (ativo, aposentado, etc.). |
| Data de Início | Data de Início | — | — | Início efetivo. |
| Data de Término | Expiration | — | — | Fim efetivo / expiração. |
| Botão de detalhes | Detalhes do ícone | Detalhes do ícone | — | Controle de interface do usuário para abrir a página de gaveta/detalhes. |
| Número total de compromissos | Compromissos | — | — | Rótulo acima da tabela, ao lado do ícone de exportação (rótulo da interface do usuário). |

## Trabalhando com a tabela

**Barra de filtros** - Filtre manualmente os metadados usando a barra de ferramentas comum de filtros.

**Hiperlink de filtro** - As células com hiperlink na tabela ficam imediatamente disponíveis para serem filtradas como "iguais". Selecione um hiperlink para filtrar a tabela por esse valor. O chip de filtro aparecerá na barra de ferramentas de filtros acima.

**Show/Hide Columns (Mostrar/ocultar colunas** ) - Use a barra Show/hide columns (Mostrar/ocultar colunas) no lado direito da tabela para selecionar quais colunas você deseja visualizar. (em breve)

**Sort & MultiSort** - Clique em um cabeçalho para classificar de forma decrescente. Clique novamente para classificar em ordem crescente. Clique uma terceira vez para retornar ao estado padrão.

**Exportar** — O botão “Exportar” gera uma CSV dos dados da tabela no formato “o que você vê é o que você obtém”. Observe que todos os metadados estão incluídos nessa exportação.

## Lembrete

É fundamental dominar as tabelas, os rótulos e os layouts usados no Commitment Manager, no portfólio e nas recomendações. Com um vocabulário consistente (Tabela, Painel de detalhes, Cartão de resumo, Página de detalhes) e um mapeamento claro dos nomes de campo entre os provedores, você poderá:

- Leia as linhas no contexto (escopo, prazo, pagamento), evitando interpretações errôneas.
- Rastrear a propriedade e o compartilhamento corretamente (pagador/conta de faturamento vs. conta/projeto vinculado).
- Compare as nuvens de forma homogênea usando campos normalizados.
- Passe mais rapidamente do que você vê (tabela) para o que importa (detalhes, subquantidades, campos de desempenho) e o que fazer em seguida (filtros, exportação e recomendações).

Com essas informações básicas, a documentação subsequente se aprofundará no aplicativo e em como ele é usado para otimizar os gastos com a nuvem.

**Tópico dos pais:** [Entendendo os fundamentos do gerenciamento de compromissos em Cloudability](../product/commitment_management_basics.html)
