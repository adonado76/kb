---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurar menus suspensos e validação"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Entrada manual de dados"
source_path: "studio/new-uc/howtoguides/work-with-data/config-dd-valid.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar menus suspensos e validação

**Objetivo:** Adicionar restrições de lista suspensa e regras de validação às colunas editáveis da tabela para garantir a qualidade e a consistência dos dados.

## Quando usar

- Qualquer coluna utilizada como dimensão de relatório ou base de alocação
- Campos de classificação em que a consistência dos valores é fundamental
- Campos com um conjunto conhecido de valores válidos
- Esquemas de classificação em vários níveis (por exemplo, Torre → Serviço → Subserviço)
- Campos numéricos que exigem validação de intervalo

Importante: sem validação, os usuários inserem dados inconsistentes que prejudicam a geração de relatórios e as alocações. Uma única dimensão pode conter "Serviços de TI", "Serviços de TI", "Tecnologia da Informação" e "Serviços de TI", quando todas deveriam ser "Serviços de TI" Os menus suspensos e a validação evitam esse problema.

## Pré-requisitos

- Uma tabela editável (em branco ou preenchida) já criada
- Compreensão dos valores válidos para cada coluna
- Para menus suspensos em cascata: tabelas de referência com dados hierárquicos

## Tempo estimado

10 a 30 minutos, dependendo da complexidade

## A. Configurar listas suspensas simples

1. **Abra sua tabela editável**
   - Acesse **Data Studio**
   - Confira a tabela editável
   - Vá para **Etapas > Configurar colunas**
2. **Selecione a coluna a ser configurada**
   - Clique no nome da coluna na lista de colunas
   - As propriedades da coluna aparecem no lado direito
3. **Definir os valores possíveis**
   - Localize o campo **“Valores possíveis”**
   - Insira uma lista de valores permitidos separados por vírgulas
   - Exemplo: *Desenvolvimento, Teste, Produção*
   - Exemplo: *Alto, Médio, Baixo*
4. **Definir o comportamento do menu suspenso**
   - **Permitir valores que não constam na lista de valores possíveis:** Desmarcado (recomendado) — Os usuários devem selecionar a partir do menu suspenso
   - **Desativar edição na célula de valores possíveis:** Desmarcado (recomendado) — Os usuários podem digitar para filtrar/pesquisar na lista suspensa

## B. Configurar listas suspensas dinâmicas

Os menus suspensos dinâmicos extraem valores de outras tabelas, permitindo uma manutenção centralizada.

1. **Crie uma tabela de referência** (se ainda não existir)
   - Crie uma tabela de transformação contendo sua lista de valores válidos
   - Exemplo: Tabela “Torres de TI” com as colunas: ID da Torre, Nome da Torre, Descrição da Torre
2. **Configurar o menu suspenso baseado em fórmula**
   - Na etapa **“Configurar colunas”** da sua tabela editável, selecione a coluna de destino
   - Em "**Valores possíveis** ", insira uma fórmula usando esta sintaxe:

`%TableName/TableFunction[].ColumnName`

- Exemplo: `%IT Towers/Distinct[].Tower Name`

## C. Configurar menus suspensos em cascata (dependentes)

Os menus suspensos em cascata filtram com base nos valores selecionados em outras colunas.

**Exemplo de cenário:** os usuários selecionam Torre → Serviço → Subserviço, sendo que as opções de Serviço dependem da Torre selecionada.

1. **Configurar a estrutura de referência**
   - Crie uma tabela de referência com relações hierárquicas
   - Exemplo: “Hierarquia de serviços de TI” com as colunas: Torre, Serviço, Subserviço
2. **Configurar o menu suspenso de primeiro nível** (Tower)
   - Nos **valores possíveis** : `%IT Service
     Hierarchy/Distinct[].Tower`
3. **Configurar o menu suspenso de segundo nível** (Serviço)
   - Em "**Valores possíveis** ", use uma fórmula que filtre com base na coluna "Torre":

```
%IT Service Hierarchy/Filter[Tower =
        [Tower]]/Distinct[].Service
```

- Definir **o contexto de valores possíveis** para **a linha atual**
  - **Configurar o menu suspenso de terceiro nível** (Subserviço)
- Fórmula semelhante, filtrando tanto por Torre quanto por Serviço:

```
%IT Service Hierarchy/Filter[Tower = [Tower] AND Service =
        [Service]]/Distinct[].Subservice
```

## D. Configurar regras de validação

1. **Use as opções de validação integradas**
   - **Valor obrigatório:** marque esta caixa para impedir a inserção de valores vazios
   - **Permitir apenas valores únicos:** marque esta opção para evitar duplicatas
   - **Tipo de dados:** Ao selecionar "Numérico", o sistema verifica automaticamente se os valores inseridos são números
2. **Ativar interface de validação** (Recurso em fase beta)
   - Vá até a guia **Projeto** > **Ativar recursos**
   - Selecione **“Ativar etapa de validação para tabela editável (Beta)”**
   - Quando ativada, os erros de validação são exibidos diretamente no campo ao inserir dados

## Armadilhas comuns

|  |  |
| --- | --- |
| **Problema** | **Solução** |
| **Os valores do menu suspenso não aparecem** | Verifique se a sintaxe da fórmula está correta. Verifique se a tabela de referência existe e contém dados. Verifique se os nomes das colunas estão escritos exatamente como aparecem (leva-se em conta maiúsculas e minúsculas). |
| **Os menus suspensos em cascata não filtram corretamente** | Verificar se o contexto de "Valores possíveis" está definido como "Linha atual". Verifique a sintaxe da fórmula do filtro: Filter[ ColumnA = [ ColumnB ]] onde ColumnA está na tabela de referência e ColumnB está na linha atual. |
| **Existem valores demais na lista suspensa (inutilizável)** | Se a lista suspensa tiver mais de 100 valores, considere uma abordagem hierárquica (listas suspensas em cascata). Ou ative a opção "Permitir edição na célula de valores possíveis" para que os usuários possam digitar para filtrar. |
| **Os usuários ainda podem inserir texto livre, mesmo com o menu suspenso** | Certifique-se de que a opção "Permitir valores que não constam na lista de valores possíveis" esteja desmarcada. |

**Tópico principal:** [Entrada manual de dados](../../../../studio/new-uc/howtoguides/work-with-data/manual-data-entry.html)
