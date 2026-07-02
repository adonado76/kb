---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Juntar dados de várias fontes"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Transformar e enriquecer dados"
source_path: "studio/new-uc/howtoguides/work-with-data/join-data.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Juntar dados de várias fontes

## Objetivo

Combine dados de duas ou mais tabelas nas mesmas linhas com base na correspondência de valores em colunas-chave, enriquecendo sua tabela principal com informações complementares.

## Quando usar isto

Use a função JOIN quando precisar:

- Adicionar colunas de uma tabela de referência (por exemplo, detalhes do centro de custo a partir de dados de RH)
- Enriquecer os dados de custos com informações sobre ativos ou a hierarquia organizacional
- Combinar conjuntos de dados relacionados para a elaboração de relatórios abrangentes
- Crie uma única tabela com todos os dados necessários para os controladores das unidades do modelo

Observação: A operação "Join" combina os dados nas mesmas linhas. Se você quiser adicionar linhas, use a função Append (consulte C; Anexar várias fontes de dados).

## Pré-requisitos

- Tabela principal verificada
- Existem tabelas relacionadas com colunas-chave correspondentes
- Compreensão das chaves de junção (colunas com valores correspondentes)

## Tempo estimado

15 a 20 minutos

## Passos

1. Abra a tabela principal no **Explorador** de Projetos.
2. Adicione uma etapa **de junção** ao pipeline de transformação (ela aparecerá após a etapa Tabela).
3. No diagrama de junção, a tabela primária aparece à esquerda. As tabelas relacionadas aparecem à direita, com as porcentagens de correspondência.
4. Clique em **“Adicionar link”** para criar uma ligação.
5. Na caixa de diálogo “**Adicionar link** ”:
   - **Da tabela** : Selecione a tabela relacionada para realizar a junção
   - **Em Coluna** : Selecione a coluna-chave na tabela relacionada
   - **Para a coluna** : Selecione a coluna-chave correspondente na sua tabela principal
6. Clique em **OK** para criar o link.
7. Analise o diagrama de junção:
   - Clique no sinal **de +** nas tabelas para ver as porcentagens de correspondência por coluna
   - Clique em um link para ver os detalhes dos itens correspondentes, não correspondentes e de referência
8. Adicione outras junções, se necessário, repetindo os passos 4 a 6.
9. Clique em **Salvar** para aplicar a etapa de junção.
10. Verifique se as colunas unidas aparecem no **Explorador** de Projetos abaixo da sua tabela principal (indicadas com uma notação como *TableName.ColumnName* ).

## Resultados esperados

As colunas da tabela associada agora estão disponíveis na sua tabela principal. Você pode usar essas colunas em fórmulas, relatórios e configurações de modelo. A visualização da etapa **“Tabela”** não exibe as colunas unidas, mas elas estão disponíveis nas etapas subsequentes e no **Explorador de Projetos**.

## Armadilhas comuns

- **Baixa porcentagem de correspondência:** Se a porcentagem de correspondência for baixa, verifique se as colunas da chave de junção contêm os mesmos valores e tipos de dados. Espaços à esquerda ou à direita, ou diferenças de maiúsculas e minúsculas, podem impedir a correspondência.
- **Colunas unidas não visíveis na etapa "Tabela":** Esse é o comportamento esperado. As colunas unidas aparecem no Explorador de Projetos e nas etapas posteriores do pipeline, mas não na visualização da etapa Tabela.
- **Uso de dados combinados em fórmulas:** se você precisar de lógica condicional baseada tanto nas colunas primárias quanto nas colunas combinadas, use fórmulas Lookup() em uma etapa de Fórmulas, em vez de depender exclusivamente da função Join.

**Tarefas relacionadas**

- [Aplicar fórmulas para transformar dados](apply-formula.html)
- [Limpar e mapear dados](apply-formula.html)
- [Usando funções de pesquisa](../../reference/formula-function.html)

**Tópico principal:** [Transformar e enriquecer dados](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
