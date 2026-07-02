---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Propriedades do objeto modelo"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
  - "Objetos modelo"
source_path: "studio/new-uc/reference/model-studio-reference/model-objects-properties.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Propriedades do objeto modelo

Cada objeto do modelo possui propriedades configuráveis que controlam seu comportamento no modelo.

**Características principais**

|  |  |  |  |
| --- | --- | --- | --- |
| **Propriedade** | **Tipo** | **Descrição** | **Notas** |
| Nome | Sequência | Nome de exibição do objeto modelo | Deve ser único dentro do projeto |
| Tabela | Referência | A tabela de transformação subjacente | A tabela deve conter a etapa "Modelo" |
| Identificador | Coluna(s) | Colunas que identificam exclusivamente as linhas | Semelhante à chave primária |
| Descrição | Sequência | Documentação opcional | Exibido no diagrama do modelo |
| Métricas | Seleção múltipla | Quais métricas se aplicam a este objeto | Custo, orçamento, previsão, etc. |

**Configuração do identificador da tabela**

O identificador da tabela determina a granularidade do objeto do modelo. Por padrão, o TBM Studio cria um identificador que identifica cada linha de forma exclusiva. Você pode personalizar isso para obter maior precisão nos relatórios e na alocação.

**Opções de configuração do identificador**

|  |  |  |
| --- | --- | --- |
| **Opção** | **Comportamento** | **Caso de uso** |
| Padrão (nível de linha) | Cada linha é tratada como única | Máxima granularidade para rastreamento e geração de relatórios |
| Coluna única | Agrupa as linhas por um valor de coluna | Agrupar por departamento, conta ou categoria |
| Várias colunas | Agrupa as linhas por combinação de colunas | É necessária uma combinação única (por exemplo, fornecedor + conta) |

Dica: leve em consideração os tempos de cálculo e o desempenho ao escolher a granularidade. Uma granularidade mais alta oferece mais detalhes, mas aumenta o tempo de processamento.

**Exemplo: Criação de um identificador personalizado**

Para agrupar custos por departamento, em vez de por transações individuais:

1. Clique na etapa “Modelo” no fluxo de transformação da tabela
2. Clique na tabela na visualização de tabela única
3. No painel “Linhas”, marque a coluna “Departamento”
4. Salvar alterações – os custos agora estão agrupados por departamento

Aviso: Alterar o identificador de um objeto de modelo existente afeta todas as alocações que fazem referência a ele. Verifique as alocações posteriores antes de fazer alterações.

*→ Consulte [“Configurar identificadores de tabela” para obter o procedimento detalhado](../../howtoguides/build-cost-model/create-allocation.html)*

**Tópico principal:** [Objetos de modelo](../../../../studio/new-uc/reference/model-studio-reference/model-objects.html)
