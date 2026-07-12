---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Aplicar fórmulas para transformar dados"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Transformar e enriquecer dados"
source_path: "studio/new-uc/howtoguides/work-with-data/apply-formula.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Aplicar fórmulas para transformar dados

## Objetivo

Crie colunas calculadas, transforme tipos de dados e aplique lógica de negócios aos seus dados antes que eles entrem na camada de modelagem.

## Quando usar isto

Use fórmulas quando for necessário:

- Criar colunas derivadas (por exemplo, Custo total = Custo unitário × Quantidade)
- Converter tipos de coluna (numérico para texto, texto para numérico)
- Aplicar lógica condicional (instruções IF, categorização)
- Enriquecer os dados com consultas a outras tabelas
- Padronizar valores ou formatar texto

## Pré-requisitos

- Tabela de origem com dados importados
- Compreensão da sintaxe das fórmulas do TBM Studio
- Nomes e tipos das colunas identificados

## Tempo estimado

10 a 15 minutos por coluna de fórmula

## Passos

1. Confira a tabela no **Explorador de Projetos**.
2. Adicione uma etapa **de Fórmulas** ao pipeline de transformação.
3. Clique em “**Adicionar uma nova coluna** ”.
4. Configure a nova coluna:
   - **Tipo** : Selecione o tipo da coluna (Chave, Rótulo, Numérico, Data)
   - **Nome** : Insira um nome descritivo para a coluna
   - **Fórmula** : Digite sua fórmula começando com =
5. Crie sua fórmula usando a sintaxe do TBM Studio:
   - Faça referência às colunas existentes usando chaves: *{Column Name}*
   - Use os operadores: + - \* / para operações matemáticas e & para concatenação de texto
   - Aplique funções: IF(), Lookup(), Value(), NumberFormat(, etc.
6. Clique em **Salvar** para adicionar a coluna.
7. Analise a pré-visualização para verificar se a fórmula produz os resultados esperados.
8. (Opcional) Para editar uma coluna de fórmula existente, selecione-a no menu suspenso “**Selecionar coluna para editar** ”, faça as alterações e clique em “**Salvar** ”.

## Exemplos comuns de fórmulas

|  |  |
| --- | --- |
| **Caso de uso** | **Exemplo de fórmula** |
| Calcular o custo total | `={Unit Cost} * {Quantity}` |
| Classificar despesas | ``` =IF({Cost Pool} IN ("FTE                 Labor&","Depreciation&"),"Fixed&","Variable&") ``` |
| Converter número em texto | `=NumberFormat({Account},"#,###&")` |
| Pesquisa em outra tabela | ``` =Lookup({Account}, Chart of Accounts,                 Account,   Cost Pool) ``` |
| Adicionar prefixo ao ID | `="pm-&"&{Asset Tag}` |

## Resultados esperados

As novas colunas de fórmula aparecem no topo da lista de colunas no painel de edição. As colunas originais da tabela permanecem na parte inferior. A visualização mostra valores calculados com base na lógica da sua fórmula.

## Armadilhas comuns

- **Erro "Não é possível encontrar a coluna&":** Verifique se os nomes das colunas correspondem exatamente (leva em conta maiúsculas e minúsculas quando estiverem entre chaves). Se o nome da coluna contiver caracteres especiais, ele deve ser colocado entre chaves.
- **Incompatibilidade de tipos nas consultas:** Ao usar a função Lookup(), certifique-se de que as colunas-chave da consulta tenham tipos compatíveis. Converta, se necessário, usando a função `Value()` ou ` NumberFormat( ()`.
- **A fórmula faz referência a colunas da etapa "Fórmulas" atual:** a maioria das fórmulas só pode fazer referência a colunas de etapas anteriores do pipeline, e não a colunas criadas na mesma etapa "Fórmulas". Crie várias etapas de fórmulas se precisar basear-se em colunas calculadas.

**Tarefas relacionadas**

- Referência de fórmulas e funções (Seção 5.4 )
- [Juntar dados de várias fontes](join-data.html)
- [Limpar e mapear dados](clean-map.html)

**Tópico principal:** [Transformar e enriquecer dados](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
