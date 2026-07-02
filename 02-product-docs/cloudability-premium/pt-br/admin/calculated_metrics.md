---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Métricas calculadas"
breadcrumb:
  - "Cloudability Premium"
  - "Configuração"
  - "Organize seus gastos com a nuvem"
source_path: "admin/calculated_metrics.html"
images:
  - "images/calculated-metric-add-button.png"
  - "images/calculated-metric-create-modal.png"
  - "images/calculated-metric-delete-dropdown.png"
  - "images/calculated-metric-delete-message.png"
  - "images/calculated-metric-details-page.png"
  - "images/calculated-metric-edit-dropdown.png"
  - "images/calculated-metric-update-modal.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Métricas calculadas

## O que são métricas calculadas?

As métricas calculadas são métricas personalizadas e reutilizáveis que você pode criar no Cloudability utilizando métricas padrão, métricas de negócios, constantes e operações aritméticas básicas.

Ao contrário das métricas fornecidas pelos fornecedores, as Métricas Calculadas oferecem flexibilidade para definir KPIs específicos para o negócio e indicadores de economia por unidade que se alinham aos requisitos exclusivos da sua organização.

As métricas calculadas suportam as seguintes operações aritméticas:

- Adição (`+`)
- Subtração (`-`)
- Multiplicação (`*`)
- Divisão (`/`)

Essas métricas ajudam a adaptar os relatórios d Cloudability e às necessidades comerciais e financeiras específicas da sua organização. As métricas calculadas permitem que as equipes criem KPIs reutilizáveis que podem ser utilizados de forma consistente em painéis e relatórios, sem a necessidade de recriar fórmulas repetidamente.

## Como funcionam as métricas calculadas?

Avaliado no momento da consulta

Quando um painel ou relatório é carregado, o Cloudability avalia as métricas calculadas com base no conjunto de resultados agregados. Isso significa que os cálculos são realizados com base nos dados agregados finais, e não nas partidas de custo individuais, durante a importação dos dados.

Essa abordagem oferece várias vantagens:

- As métricas ficam disponíveis imediatamente após a criação
- Não é necessário reprocessar os dados
- Os relatórios históricos refletem automaticamente as atualizações das fórmulas
- As alterações entram em vigor imediatamente em todos os relatórios e painéis

Aplicado aos resultados agregados

As métricas calculadas operam com dados agregados após o agrupamento e a síntese. Isso significa que a fórmula é aplicada a totais, médias ou outros valores agregados, e não a linhas individuais.

Dicas para criar métricas calculadas

Escolha um nome claro

Cada métrica calculada deve ter um nome exclusivo. Escolha um nome que transmita claramente sua finalidade, pois ele aparecerá nos relatórios e em todo o site Cloudability. O nome deve ser exclusivo dentro da sua organização e não pode coincidir com nomes de medidas básicas já existentes.

Selecione a fonte de dados adequada

Escolha entre “Custo” ou “Uso” como sua fonte de dados. Todas as medidas mencionadas na sua fórmula devem corresponder ao tipo de fonte de dados selecionado.

Definir uma fórmula clara

Crie fórmulas utilizando nomes de medidas válidos, constantes e operadores aritméticos. Certifique-se de usar os parênteses corretamente para controlar a ordem das operações.

Adicionar uma descrição

Forneça uma descrição clara que explique a finalidade da métrica e a lógica de cálculo. Isso ajuda outros usuários a compreender e aplicar corretamente a métrica em seus relatórios.

## Trabalhando com métricas calculadas

Listagem e análise das métricas calculadas

Na página “Mapeamentos de negócios”, você pode visualizar todas as métricas calculadas que criou. A lista mostra o nome da métrica, a descrição, a fonte de dados e os detalhes de criação.

Criação de novas métricas calculadas

Para criar uma nova métrica calculada:

1. Vá para **Organizar → Mapeamentos de negócios**
2. Selecione **“Nova métrica calculada”** no menu suspenso **“Nova dimensão de negócios”**

   ![Novo botão “Métrica calculada”](../../../../03-media/cloudability-premium/images/calculated-metric-add-button.png)
3. Digite um **nome** para a métrica
   - O nome deve ser único dentro da sua organização
   - Não é possível encontrar correspondência com nomes de medidas básicas existentes
4. Adicionar uma **descrição**
   - A descrição aparece como uma dica de ferramenta quando a métrica é usada em painéis ou relatórios
   - Ajuda outros usuários a compreender a finalidade da métrica
5. Selecione um **tipo de métrica** (formato numérico)
   - **Número** - Formato padrão para valores numéricos em geral
   - **Valor** - Para valores em moeda/custo
   - **Porcentagem** — Para cálculos de proporção ou porcentagem
6. Selecione a **fonte de dados**
   - **Custo** — Utilize métricas relacionadas ao custo (por exemplo, unblended\_cost, amortized\_cost)
   - **Uso** — Utilize métricas de utilização (por exemplo, avg\_cpu\_utilization, memory\_usage)
   - Todas as medidas na sua fórmula devem corresponder à fonte de dados selecionada
7. Defina a **fórmula**
   - Utilize nomes de medidas válidos da sua fonte de dados selecionada
   - Inclua constantes (números) conforme necessário
   - Aplique os operadores aritméticos: +, -, \*, /
   - Use parênteses para controlar a ordem das operações

   ![Modal “Criar métrica calculada”](../../../../03-media/cloudability-premium/images/calculated-metric-create-modal.png)
8. Clique em **“Salvar”** para criar a métrica

Depois de salva, a métrica calculada fica imediatamente disponível em todos os relatórios d Cloudability.

Edição de métricas calculadas

Para atualizar uma métrica calculada existente:

1. Vá para **Organizar → Mapeamentos de negócios**
2. Encontre na lista a **métrica calculada** que você deseja editar
3. Clique no ícone de engrenagem e selecione **“Editar métrica”** no menu suspenso

   ![Editar menu suspenso de métricas](../../../../03-media/cloudability-premium/images/calculated-metric-edit-dropdown.png)
4. Atualize os campos conforme necessário:
   - Descrição
   - Formato numérico
   - Fórmula
   - Origem de Dados

   ![Atualizar a janela modal “Métrica calculada”](../../../../03-media/cloudability-premium/images/calculated-metric-update-modal.png)
5. Clique em **“Salvar”** para aplicar as alterações

Exclusão de métricas calculadas

Para excluir uma métrica calculada:

1. Vá para **Organizar → Mapeamentos de negócios**
2. Encontre na lista a **métrica calculada** que você deseja excluir
3. Clique no ícone de engrenagem e selecione **“Excluir métrica”** no menu suspenso

   ![Excluir o menu suspenso de métricas](../../../../03-media/cloudability-premium/images/calculated-metric-delete-dropdown.png)
4. Clique em **OK** na mensagem de confirmação “Excluir métrica calculada”

   ![Mensagem de confirmação de exclusão](../../../../03-media/cloudability-premium/images/calculated-metric-delete-message.png)

**Importante:** uma métrica calculada só pode ser excluída se não estiver sendo referenciada por nenhum relatório, painel ou widget salvo no momento. Se a métrica estiver em uso, é necessário remover essas referências antes da exclusão.

Visualização dos detalhes da métrica calculada

Para visualizar os detalhes de uma métrica calculada específica:

1. Vá para **Organizar → Mapeamentos de negócios**
2. Encontre na lista a **métrica calculada** que você deseja visualizar
3. Clique no **nome** da métrica
4. Veja os detalhes completos na página de detalhes da métrica

   ![Página de detalhes da métrica calculada](../../../../03-media/cloudability-premium/images/calculated-metric-details-page.png)

A página de detalhes exibe:

- Nome e descrição completos do indicador
- Expressão completa
- Carimbos de data e hora de criação e modificação
- Informações sobre o criador e o último modificador

## Casos de uso comuns

**Compare modelos de custo de nuvem**

Compreenda a diferença entre o custo original da nuvem e o custo efetivo amortizado da nuvem para avaliar o impacto financeiro de compromissos, descontos e preços negociados.

**Exemplo:**

```
Cost (List) - Cost (Amortized)
```

Este cálculo mostra a economia total obtida por meio de otimizações de preços.

**Analisar a eficiência das economias**

Avalie a eficácia com que as otimizações de preços reduzem os custos entre fornecedores, serviços, equipes e unidades de negócios.

**Exemplo:**

```
(Cost (List) - Cost (Amortized)) / Cost (List)
```

Essa porcentagem indica a proporção do preço de tabela economizada por meio de otimizações.

**Analisar a economia da unidade**

Crie KPIs operacionais para avaliar a escalabilidade e a eficiência operacional.

**Exemplos:**

- Custo por recurso: `unblended_cost / usage_quantity`
- Custo por cluster: `unblended_cost / cluster_count`
- Custo por ambiente: `unblended_cost / environment_count`
- Custo por carga de trabalho: `unblended_cost / workload_count`

**Aplicar descontos ou sobrepreços**

Simule diferentes cenários de preços aplicando ajustes baseados em porcentagens.

**Exemplos:**

- Desconto de 20%: `unblended_cost * 0.8`
- Margem de lucro de 10%: `unblended_cost * 1.1`
- Preços diferenciados: `(unblended_cost + 100) / 2`

**Calcular as reservas de utilização**

Adicione margens de segurança às métricas de utilização para o planejamento de capacidade.

**Exemplo:**

```
avg_cpu_utilization * 1.1
```

Isso adiciona uma margem de 10% à utilização da CPU para fins de planejamento.

## Permissões

As Métricas Calculadas oferecem três níveis de permissão que controlam o acesso e as capacidades dos usuários.

**Acesso total**

**Permissão:** `CalculatedMetricsFeatureFullAccess`

Os usuários com acesso total podem:

- Ver todas as métricas calculadas
- Criar novas métricas calculadas
- Atualizar qualquer métrica calculada
- Excluir qualquer métrica calculada

**Acesso para edição própria**

**Permissão:** `CalculatedMetricsFeatureOwnEditAccess`

Os usuários com acesso para editar seus próprios conteúdos podem:

- Ver todas as métricas calculadas
- Criar novas métricas calculadas
- Atualizar apenas as métricas criadas por eles
- Excluir apenas as métricas criadas por eles

**Acesso somente para visualização**

**Permissão:** `CalculatedMetricsFeatureViewOnlyAccess`

Os usuários com acesso somente para visualização podem:

- Ver todas as métricas calculadas
- Visualizar definições e fórmulas de métricas
- Utilize métricas em relatórios e painéis
- Não é possível criar, editar ou excluir métricas

## Qual é a diferença entre métricas calculadas e métricas de negócios?

| **Funcionalidade** | **Métricas calculadas** | **Métricas de negócios** |
| --- | --- | --- |
| Prazo para avaliação | Avaliado no momento da consulta | Avaliado no momento da ingestão |
| Nível de processamento | Aplicado aos resultados agregados | Aplicado a cada linha separadamente |
| Lógica condicional | Sem expressões condicionais | Suporta expressões de correspondência |
| Disponibilidade | Disponível imediatamente | Requer reprocessamento dos dados |
| Limites métricos | Ilimitado | Até 5 métricas de negócios |
| Complexidade da fórmula | Apenas operações aritméticas | Suporta lógica condicional complexa |
| Dados históricos | As atualizações têm efeito retroativo | Requer reprocessamento dos dados históricos |

## Regras de expressão e validação

**Operadoras compatíveis**

- `+` Adição
- `-` Subtração
- `*` Multiplicação
- `/` Divisão

**Regras de validação**

- **Nome:** Deve ser único dentro da organização e não pode coincidir com nomes de medidas básicas já existentes
- **Expressão:** É necessário usar operadores e nomes de métricas válidos para a sua organização
- **Tipo de fonte:** Todas as medidas na expressão devem corresponder ao source\_type especificado (custo ou uso)
- **Parênteses:** devem estar devidamente equilibrados nas expressões
- **Nomes das medidas:** Podem conter letras, dígitos e sublinhados
- **Decimais:** Use o ponto (.) para números decimais

**Exemplos de expressões**

**Métricas de custo:**

```
unblended_cost * 0.8
(unblended_cost + 100) / 2
business_metric9 / total_adjusted_amortized_cost * bytes_transferred
```

**Métricas de uso:**

```
avg_cpu_utilization * 1.1
burst_balance * 100
avg_running_instances_per_hour / business_metric9
```

## Perguntas frequentes (FAQ)

Quando as métricas calculadas são avaliadas?

As métricas calculadas são avaliadas no momento da consulta. Isso significa que os cálculos são realizados quando um painel ou relatório é carregado, e não durante a importação dos dados de faturamento.

Consequentemente:

- As métricas ficam disponíveis imediatamente após a criação
- Os relatórios históricos refletem automaticamente as atualizações das fórmulas
- Não é necessário reprocessar os dados
- As alterações entram em vigor imediatamente em todos os relatórios

Que tipos de fórmulas são compatíveis?

As métricas calculadas suportam fórmulas criadas com:

- Métricas padrão (medidas de custo e uso)
- Métricas de negócios
- Valores constantes (números)
- Adição (`+`)
- Subtração (`-`)
- Multiplicação (`*`)
- Divisão (`/`)
- Parênteses para a ordem das operações

**Exemplo:**

```
(Cost (List) - Cost (Amortized)) / Cost (List)
```

As métricas calculadas podem utilizar lógica condicional?

Nº As métricas calculadas não oferecem suporte a:

- Lógica SE/ENTÃO
- CASE declarações
- Condições booleanas
- Expressões correspondentes

Para lógica condicional ou baseada em regras, utilize, em vez disso, o Business Metrics ou o Business Mappings.

As métricas calculadas exigem o reprocessamento de dados?

Nº As métricas calculadas ficam disponíveis imediatamente após a criação ou modificação e não exigem o reprocessamento dos dados de faturamento. As alterações nas fórmulas são aplicadas automaticamente a todos os dados históricos quando os relatórios são gerados.

Existe um limite para o número de métricas calculadas?

Nº Cloudability suporta um número ilimitado de métricas calculadas por organização.

As métricas calculadas podem fazer referência a outras métricas calculadas?

Nº As métricas calculadas foram projetadas para utilizar métricas padrão, métricas de negócios, constantes e operações aritméticas. Métricas calculadas aninhadas ou encadeadas (nas quais uma métrica calculada faz referência a outra) não são suportadas no momento.

O que acontece se eu excluir uma métrica calculada que está em uso?

Não é possível excluir uma métrica calculada se ela estiver sendo referenciada por algum relatório, painel ou widget salvo. É necessário primeiro remover todas as referências à métrica para que a exclusão seja permitida. Isso evita que os relatórios e painéis existentes deixem de funcionar corretamente.

Como posso usar a API para gerenciar métricas calculadas?

Você pode usar as APIs d Cloudability s para criar, ler, atualizar e excluir métricas calculadas por meio de programação. A documentação da API para gerenciar métricas calculadas está disponível no tópico “[Endpoint de métricas calculadas](../api-v3/calculated_metrics_end_point.html) ”.

**Tópico principal:** [Organize seus gastos com nuvem](../admin/tag-data.html)
