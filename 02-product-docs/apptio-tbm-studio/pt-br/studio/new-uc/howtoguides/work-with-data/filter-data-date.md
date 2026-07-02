---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Filtrar dados por partição de data"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Transformar e enriquecer dados"
source_path: "studio/new-uc/howtoguides/work-with-data/filter-data-date.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filtrar dados por partição de data

## Objetivo

Distribua dados com registro de data e hora por períodos e filtre automaticamente de acordo com o período ativo selecionado no TBM Studio, permitindo uma análise de custos centrada no mês.

## Quando usar isto

Use a partição por data quando:

- Seus dados contêm datas de transações e você precisa de intervalos mensais
- Trabalho com dados do razão geral com carimbos de data por transação
- Os dados apresentam os meses em colunas separadas (jan, fev, mar, etc.)
- Você precisa que os valores sejam atualizados automaticamente quando os usuários mudarem de período

Observação: O TBM Studio é organizado por mês. As partições de data filtram os dados para mostrar apenas os valores selecionados de month&#x2019;s. A agregação entre períodos ocorre na camada de relatórios.

***Nota:***

## Pré-requisitos

- Dados com informações de data (em linhas ou colunas)
- Compreensão do formato de data dos seus dados
- Colunas de data com tipo de dados definido corretamente (para dados organizados em linhas)

## Tempo estimado

10 a 15 minutos

**Passos**

## Para dados organizados em linhas (datas em linhas)

*Utilize essa abordagem quando seus dados tiverem colunas de data com uma data por linha (por exemplo, data da transação no Razão).*

1. Dê uma olhada na tabela e adicione uma etapa **de partição por data** ao pipeline de transformação.
2. **As datas** selecionadas são apresentadas em linhas.
3. Selecione a coluna **"Data de início"** (obrigatória).
4. (Opcional) Selecione a coluna **“Data de término”** se seus dados abrangerem intervalos de datas.
5. Clique em **Salvar**.

## Para dados organizados em colunas (datas nos cabeçalhos das colunas)

*Use essa abordagem quando seus dados tiverem uma coluna para cada mês (por exemplo, Orçamento com as colunas Jan, Fev e Mar).*

1. Dê uma olhada na tabela e adicione uma etapa **de partição por data** ao pipeline de transformação.
2. **As datas** selecionadas são apresentadas em colunas.
3. Em “**Interpretar ano como** ”, selecione **“Ano fiscal”** ou “**Ano civil** ”.
4. Em “**Prefixo da nova coluna** ”, insira um rótulo para ser usado como prefixo nas colunas de data (por exemplo, “Valor&” cria “Valor Jan&”, “Valor Fev&”).
5. Selecione quais conjuntos de colunas devem ser particionados:
   - Se você tiver vários conjuntos (por exemplo, Custo e Orçamento), selecione quais deseja incluir
   - Você pode particionar por um ou por todos os conjuntos de colunas
6. Clique em **Salvar**.

## Resultados esperados

A tabela agora responde ao intervalo de tempo selecionado no TBM Studio. Quando você altera o mês usando o seletor de datas, a visualização é atualizada para mostrar apenas os dados d month&#x2019;s. Para partições baseadas em colunas, novas colunas são criadas com o prefixo especificado e os rótulos de mês.

## Armadilhas comuns

- **Formato de data não reconhecido:** para dados em colunas, os nomes dos meses devem ser reconhecíveis (Jan, Janeiro, P1, etc.). Os anos podem estar em qualquer posição, exceto no meio (formatos como “2016 Jan&” ou “Jan 2016&” são válidos, mas “Jan 2016 Cost&” não é).
- **Não há dados visíveis após o particionamento:** verifique se o período selecionado corresponde às datas dos seus dados. Se estiver trabalhando com dados históricos, certifique-se de que o seletor de datas do TBM Studio abranja o período relevante.
- **Não é possível selecionar vários meses:** esse é o comportamento esperado. Filtrar as divisões por data para um único período ativo. Para agregações que abrangem vários meses, utilize funções da camada de relatórios, como YTD (Acumulado no ano), ou crie colunas baseadas em datas.

**Tarefas relacionadas**

- [Tabelas de versões para dados mensais](version-tables-monthly-data.html)
- Compreensão dos períodos de tempo (Conceitos: Arquitetura de dados)
- Fórmulas baseadas em data e hora nos relatórios (Referência: Fórmulas e funções)

**Tópico principal:** [Transformar e enriquecer dados](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
