---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Compartilhamento de custos em Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Configuração"
source_path: "product/cost-sharing.html"
images:
  - "images/cost-sharing-4.jpg"
  - "images/cost-sharing-6.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Compartilhamento de custos em Cloudability

## Introdução

O compartilhamento de custos ajuda as organizações a gerenciar os gastos em processos de showback e chargeback de maneira mais eficiente. Ao compartilhar itens de linha entre as empresas do grupo “ Cloudability ”, elas conseguem reduzir custos.

O compartilhamento de custos consiste em pegar um conjunto de despesas (por exemplo, os encargos diretos de um valor dimensional) e distribuir esse valor entre uma lista de valores dimensionais de destino. Uma maneira simples de entender isso é pensar que cada valor de dimensão tem um custo direto no ` Cloudability `. Esse custo foi calculado a partir da importação dos dados brutos relativos ao custo do recurso, seguida da atribuição de tags e, em seguida, do uso da lógica condicional do recurso de mapeamentos de negócios d Cloudability.

Cada valor dimensional está associado a um custo direto, a um custo indireto e a um custo total (direto + indireto).

As regras de alocação de custos são definidas no contexto de um único mapeamento de negócios. É possível configurar várias regras dentro de um Mapeamento de Negócios. No entanto, não é possível configurar regras que abranjam vários mapeamentos de negócios.

## Benefícios

Os benefícios da divisão de custos são:

- Atribuição precisa de custos : Permita o acompanhamento preciso de recursos e serviços compartilhados entre equipes, produtos e unidades de negócios.
- Modelo de estorno justificável : Crie uma distribuição de custos transparente e baseada em regras que apoie as práticas internas de faturamento.
- Estratégias flexíveis de alocação : Escolha entre vários métodos de alocação para atender aos requisitos de repartição de custos da sua organização.
- Gestão de custos alinhada aos negócios : Relacione os custos de tecnologia aos resultados de negócios e à estrutura organizacional.
- Maior visibilidade dos custos : obtenha informações claras sobre os custos diretos e compartilhados em todo o seu ambiente de nuvem.

## Conceitos-Chave

As organizações alocam e compartilham custos em diversos cenários. Tendo isso em mente. Incluímos para você as estratégias de alocação mais comuns na seção a seguir.

Os diversos custos incorridos são:

- Custo direto : Custos decorrentes da ingestão de dados brutos, da marcação sintética ou do mapeamento de negócios
- Custo compartilhado : Custos recebidos por meio de regras de compartilhamento de custos a partir de valores dimensionais de origem
- Custo total : valor combinado dos custos diretos e indiretos para qualquer valor dimensional

## Estratégias de alocação

As diversas estratégias de alocação são:

- A opção “Even Split” define uma distribuição dos custos diretos (s) por um conjunto de faixas dimensionais, com valores iguais. Os custos diretos podem ser de uma categoria unidimensional ou multidimensional.
- A ponderação fixa utiliza pesos fixos expressos em porcentagem. Trata-se de uma discriminação dos custos diretos de um grupo unidimensional ou multidimensional com base em uma ponderação definida pelo usuário.
- A opção “Proporcional (por custos diretos)” utiliza o custo direto como peso. Isso permite que você distribua dinamicamente a alocação com base nas cobranças diretas da origem e do destino. A pesagem proporcional leva em consideração as cargas diretas do balde de origem ao calcular a proporção de atribuição para a alocação selecionada.
- As alocações baseadas em telemetria/consumo utilizam dados de telemetria (métricas de uso, chamadas de API ou operações de armazenamento) para criar regras de alocação mais precisas e orientadas por dados, e estão disponíveis apenas para clientes do Cloudability Premium.

## Configurar regras de repartição de custos

Para configurar as regras de repartição de custos,

1. Na seção **“Organizar”** do menu principal, selecione “**Compartilhamento de custos** ”.
2. Selecione “Nova alocação ”. Como alternativa, selecione uma dimensão de negócios existente para editar a regra de alocação. Não há limite para o número de regras de alocação que você pode definir.
3. Especifique uma dimensão para a nova alocação.
4. Para criar uma nova regra, clique em “Nova regra ”. Selecione os buckets de origem dos quais deseja compartilhar os custos, os buckets de destino para os quais deseja compartilhar os custos e as estratégias de alocação a serem utilizadas para ponderar esses custos. As regras de alocação existentes, se houver, são exibidas na tabela Regras.
5. Clique em **Salvar**.
6. Acesse a guia **“Explorer”** para visualizar seus custos compartilhados e as regras de alocação aplicadas.

![captura de tela da nova regra de alocação](../../../../03-media/cloudability-premium/images/cost-sharing-4.jpg)

A guia “Explorer” exibe as regras de alocação criadas com os seguintes detalhes:

- Intervalo do relatório: O intervalo de datas selecionado, que vai de ontem até o ano passado.
- Métrica de custo : O tipo de custo selecionado.

Clique em “+Adicionar filtro” para definir filtros e exibir a lista de regras de alocação de custos.

Você pode alternar entre os botões “Todos” e “Compartilhados” para exibir a lista de todas as regras de alocação de custos ou apenas as compartilhadas, respectivamente.

## Relatório

Disponibilizamos uma nova projeção no Apptio BI para relatórios sobre custos compartilhados, chamada “ Cloudability : Custo e Uso (Alocados)”. Trata-se de uma projeção separada devido à escala e ao tamanho do conjunto de dados com o qual trabalhamos ao executar todas as regras de alocação de custos. Para criar um relatório com base nesse custo compartilhado, siga as etapas abaixo:

1. Acesse “ Apptio BI ” no painel de navegação à direita.
2. Na guia “Relatórios”, selecione “Criar novo relatório ”.
3. Clique em Adicionar visualização e selecione a projeção de Custo e Uso Cloudability (Alocado).
4. Crie seu relatório com as mesmas dimensões e métricas de custo disponíveis no Cloudability Cost and Usage.
5. Selecione na lista de Visualizações Cloudability.

   ![Captura de tela da divisão de custos](../../../../03-media/cloudability-premium/images/cost-sharing-6.jpg)

## Visualizações

A divisão de custos respeita a estrutura da nossa visualização, exibindo itens compartilhados no bucket de destino quando esse bucket está incluído em uma visualização. Por exemplo: para uma dimensão de negócios chamada “Produto”, que inclui vários produtos denominados A, B e C, nossa organização aloca os custos do produto A para os produtos B e C de forma proporcional (por meio de encargos diretos), o que faz com que os produtos B e C absorvam o custo direto do produto A. Agora, no caso de uma visão configurada com C, quando um relatório é criado em Apptio BI, a visão do produto C exibiria tanto seus custos diretos quanto o custo que foi compartilhado com ele pelo produto A.

## Boas Práticas

Algumas das melhores práticas em compartilhamento de custos incluem aspectos relacionados à configuração de regras e à gestão de custos.

A configuração das regras inclui o seguinte:

- Comece com regras de alocação mais simples e aumente gradualmente a complexidade
- Documentar a justificativa comercial para cada regra de alocação
- Revisar e validar regularmente as regras de alocação à luz das mudanças nos negócios
- Considere o impacto hierárquico das alocações dentro da sua organização
- As regras de alocação de custos operam dentro de um único mapeamento de negócios

A gestão de custos inclui o seguinte:

- Monitorar tanto os custos diretos quanto os compartilhados para identificar tendências e anomalias
- Validar mensalmente os resultados da alocação para garantir a precisão
- Manter uma documentação clara das decisões e metodologias de alocação
- Leve em consideração as variações sazonais ao definir regras de alocação

## Funcionalidade de importação e exportação para regras de alocação de custos

Oferecemos recursos de importação e exportação para regras de alocação de custos, a fim de agilizar a configuração e aumentar a flexibilidade:

- CSV Importação : É possível importar regras de alocação de custos por meio de CSV, eliminando a necessidade de configurá-las manualmente na interface do usuário ou programaticamente por meio da API.
  - Isso é ideal para a geração em massa de regras de alocação.
  - Um modelo CSV está disponível na parte inferior deste documento, fornecendo um exemplo que pode ser usado na importação de regras. Como alternativa, se você já tiver um conjunto de regras, elas serão exportadas com os cabeçalhos de coluna corretos e os valores compatíveis para upload.
  - A lista de colunas de que precisamos é a seguinte:
    - ID da regra : Um identificador exclusivo da regra em questão. Se você estiver criando várias instruções em uma determinada regra (por exemplo: se estiver distribuindo vários buckets de origem por vários destinos), será necessário incluir o mesmo ID da regra em todas as instruções
    - Método de alocação (deve ser um dos seguintes): Even\_split, proportional\_fixed\_weighting, proportional\_metric ou telemetry\_consumption. Observe que a telemetria é compatível apenas com as versões “ Cloudability Standard ” e “Premium”.
    - Fonte : O conjunto de buckets de origem dos quais você deseja alocar o custo
    - Destino : O conjunto de buckets de destino aos quais você deseja alocar o custo
    - Peso do destino : esse deve ser o peso da alocação para esse destino específico
    - Identificador de telemetria : deve ser definido como “personalizado”
    - Nome da métrica de telemetria : O nome da métrica utilizada para ponderar a alocação. Isso pode ser, por exemplo, o número de chamadas de API.
- Exportar regras existentes : É possível exportar o conjunto atual de regras de alocação de custos dentro de uma dimensão de negócios.

## Modelo de regras de alocação de custos

Tabela 1. Modelo de regras de alocação de custos

| ID de Regra | Método de alocação | Origem | Destino | Peso no destino | Telemetria de identificadores | Nome da Métrica |
| --- | --- | --- | --- | --- | --- | --- |
| 2310fe9f-6535-474b-a153-27719a485168 | even\_split | nuvem | faturamento | 0.5 |  |  |
| 2310fe9f-6535-474b-a153-27719a485168 | even\_split | nuvem | acme | 0.5 |  |  |
| 2 | consumo\_de\_telemetria | cálculo |  | 0 | customizar | Número de solicitações do SQS |
| 3 | métrica\_proporcional | dados | vanguarda | 0 |  |  |
| 3 | métrica\_proporcional | dados | nimbus | 0 |  |  |
| 3 | métrica\_proporcional | dados | billmx | 0 |  |  |
| 3 | métrica\_proporcional | pipeline | vanguarda | 0 |  |  |
| 3 | métrica\_proporcional | pipeline | nimbus | 0 |  |  |
| 3 | métrica\_proporcional | pipeline | billmx | 0 |  |  |
| 4 | ponderação\_proporcional\_fixa | dados de cobrança | ccm | 0.4 |  |  |
| 4 | ponderação\_proporcional\_fixa | dados de cobrança | segurança da informação | 0.6 |  |  |
| 4 | ponderação\_proporcional\_fixa | datalake | ccm | 0.4 |  |  |
| 4 | ponderação\_proporcional\_fixa | datalake | segurança da informação | 0.6 |  |  |
| 4 | ponderação\_proporcional\_fixa | operações técnicas | ccm | 0.4 |  |  |
| 4 | ponderação\_proporcional\_fixa | operações técnicas | segurança da informação | 0.6 |  |  |
| 5 | even\_split | Operações do | ccm | 0.5 |  |  |
| 5 | even\_split | Operações do | Vedas | 0.5 |  |  |

## Exportação de dados da página do Explorer

Adicionamos a funcionalidade de exportar dados da página “Explorer ”. Agora você pode baixar relatórios detalhados sobre:

- Custos diretos
- Custos compartilhados
- Custos totais

## Repartição de custos por indicadores de negócios

Estamos ampliando o poder e a precisão do Cost Sharing com um novo suporte para métricas de negócios personalizadas.

Distribuir custos por qualquer métrica de negócios baseada em moeda

Anteriormente, o Cloudability suportava a divisão de custos apenas por meio de um conjunto predefinido de métricas de custo padrão. Com esta atualização, agora é possível alocar custos compartilhados em qualquer métrica de negócios baseada em moeda em seu ambiente.

Essa melhoria oferece maior flexibilidade na forma como você define e aplica sua lógica de alocação de custos, permitindo:

- Alocações de custos mais relevantes do ponto de vista contextual, adaptadas ao modelo financeiro específico da sua empresa
- Maior justificativa para a distribuição de custos compartilhados, alinhando-a às métricas mais importantes para suas equipes
- Recursos ampliados de geração de relatórios utilizando métricas além das padrão

Atualmente, apenas as métricas de negócios baseadas em moeda são suportadas.

Onde você vai ver isso

- Página do Explorer : Ao configurar ou revisar as regras de repartição de custos, você verá todas as métricas de negócios elegíveis disponíveis para seleção
- Apptio BI : Você também pode escolher entre o conjunto completo de métricas compatíveis ao criar relatórios, o que permite análises mais aprofundadas e o alinhamento entre as partes interessadas

Esta atualização está disponível para todos os clientes do Cloudability e não requer nenhuma configuração adicional para começar a ser utilizada.

Guia de configuração do usuário: Lineage nos relatórios d ApptioBI

Este guia ajuda os usuários a incluir a dimensão “Fonte de Alocação” em seus relatórios do Apptio BI para obter informações detalhadas sobre a origem dos custos compartilhados.

Pré-requisitos:

- Acesso ao site Apptio BI e à projeção de Custo e Uso (Alocado) do Cloudability
- Regras estabelecidas no programa “ Cloudability ” (Compartilhamento de Custos)

Configuração passo a passo

1. Acesse Apptio BI :
   - Faça login na sua conta do Cloudability e acesse Apptio BI.
2. Selecione a projeção:
   - Acesse um painel e selecione “Novo widget” para criar um novo widget.
   - Escolha a projeção de Custo e Uso (Alocado).
3. Adicionar dimensão de fonte de alocação:
   - No painel de configuração do widget, clique em “Dimensões”.
   - Procure e selecione “Fonte de alocação”.
   - Arraste ou clique para adicionar a dimensão “Fonte de alocação” ao seu widget.
4. Personalize seu widget:
   - Adicione quaisquer outras dimensões ou métricas necessárias.
   - Confirme e aplique as configurações do seu widget.
5. Validar e publicar:
   - Visualize o widget para garantir a precisão e a clareza dos dados.
   - Clique em “Salvar” para finalizar e publicar seu relatório.

Nota:

- A “Fonte de alocação” fornece detalhes em nível de linha sobre os custos compartilhados e aumentará o número de linhas em seus relatórios.
- Evite utilizar a “Fonte de alocação” com várias dimensões de negócios ativadas simultaneamente para o repartição de custos, pois isso gerará erros.

## Solução de problemas conhecidos

- Erro: “Não foi possível exibir a fonte de alocação”:
  - Causa: A fonte de alocação está sendo utilizada com várias dimensões que apresentam repartição de custos.
  - Solução: Certifique-se de que a fonte de alocação seja combinada apenas com uma dimensão compartilhada por vez em cada widget.

- **[Compartilhamento de custos para relatórios e painéis](../product/cost-sharing-for-reports-and-dashboards.html)**
- **[Compartilhamento de custos — Alocações com base em telemetria e consumo](../product/cost-sharing-telemetry.html)**
