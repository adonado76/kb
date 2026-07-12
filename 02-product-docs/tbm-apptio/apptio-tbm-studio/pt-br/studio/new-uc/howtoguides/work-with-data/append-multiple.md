---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Adicionar várias fontes de dados"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Trabalhar com dados"
  - "Transformar e enriquecer dados"
source_path: "studio/new-uc/howtoguides/work-with-data/append-multiple.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adicionar várias fontes de dados

## Objetivo

Combine linhas de uma ou mais tabelas de origem em uma tabela de destino, criando um conjunto de dados unificado a partir de várias fontes.

## Quando usar isto

Use a função Append quando precisar:

- Combinar dados de várias fontes semelhantes (por exemplo, inventários de servidores virtuais e físicos)
- Consolidar os dados regionais em uma única tabela mestre
- Adicionar linhas de dados complementares a uma tabela existente
- Agrupar conjuntos de dados com estruturas semelhantes, mas não idênticas

Observação: A função Append adiciona linhas à sua tabela. Se você quiser adicionar colunas às linhas existentes, use a função "Juntar" (consulte "Juntar dados de várias fontes&").

## Pré-requisitos

- A tabela de destino é uma tabela de transformação (não uma tabela carregada)
- Existem tabelas de origem com dados a serem anexados
- Compreensão do mapeamento de colunas entre a fonte e o destino

## Tempo estimado

15 a 20 minutos para a configuração inicial; 5 minutos para adicionar fontes adicionais

## Passos

1. Confira a tabela de destino no **Explorador de Projetos**.
2. Adicione uma etapa **de acréscimo** ao pipeline de transformação.
3. Clique em “**Adicionar fonte de dados** ”.
4. Selecione a tabela de origem à qual deseja anexar os dados e clique em **Avançar**.
5. Mapeie as colunas de origem para as colunas de destino:
   - **Colunas correspondidas automaticamente:** as colunas com nomes correspondentes (sem distinção entre maiúsculas e minúsculas) são mapeadas automaticamente e exibidas com marcas de seleção verdes
   - **Mapeamento manual:** para colunas não mapeadas, use o menu suspenso para selecionar a coluna de origem correspondente
   - **Valores fixos:** Para usar o mesmo valor em todas as linhas anexadas, selecione “Insira um valor fixo para todas as linhas” e insira o valor
   - **Fórmulas:** Digite uma fórmula começando com = para transformar os dados de origem (por exemplo, ="pm-&"& {Asset Tag} )
6. (Opcional) Clique em **“Selecionar coluna adicional da fonte”** para adicionar novas colunas da tabela de origem à tabela de destino.
7. Consulte as tabelas de pré-visualização na parte inferior para verificar o mapeamento.
8. Clique em **Salvar**.
9. Para adicionar tabelas de origem adicionais, clique novamente **em** “Adicionar fonte de dados” e repita as etapas 4 a 8.

## Resultados esperados

As linhas de todas as tabelas de origem são adicionadas à tabela de destino. A pré-visualização mostra dados combinados de todas as fontes. Cada fonte é listada no painel da etapa “Anexar” com o número de colunas necessárias mapeadas.

## Gerenciamento de fontes anexadas

No painel da etapa “Anexar”, você pode:

- **Editar** : Modificar os mapeamentos de colunas para uma fonte anexada
- **Remover** : Excluir uma fonte anexada da tabela de destino
- **Anexar fonte de dados** : Adicionar outra tabela de origem para anexar

## Armadilhas comuns

- **Incompatibilidades de tipo de coluna:** Se uma coluna de origem não aparecer no menu suspenso, verifique se ela tem o mesmo tipo que a coluna de destino. Se necessário, use fórmulas para converter tipos.
- **Fórmulas x valores fixos:** Os valores fixos não calculam fórmulas. Para usar uma fórmula, adicione uma etapa “Fórmulas” antes da etapa “Anexar” e, em seguida, mapeie a coluna resultante.
- **Bloqueio de adições para períodos fora do intervalo:** em tabelas com versões, as adições se aplicam apenas à versão atual. Ao selecionar um período fora do intervalo de datas da versão, o anexo fica bloqueado e não pode ser editado.

## Tarefas relacionadas

- [Juntar dados de várias fontes](join-data.html)
- [Aplicar fórmulas para transformar dados](apply-formula.html)
- Usando funções de pesquisa (Referência: Fórmulas e funções)

**Tópico principal:** [Transformar e enriquecer dados](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
