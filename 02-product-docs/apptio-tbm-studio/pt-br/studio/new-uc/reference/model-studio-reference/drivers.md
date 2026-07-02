---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Motoristas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Referência do Model Studio"
source_path: "studio/new-uc/reference/model-studio-reference/drivers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Motoristas

Os drivers inserem valores em um objeto de modelo e determinam como esses valores são distribuídos. Elas constituem o principal mecanismo para conectar os dados de origem ao modelo de custos.

## Tipos de motoristas

O TBM Studio suporta três tipos de drivers, cada um atendendo a diferentes necessidades de alocação.

**Motorista de unidade**

**Descrição:** Um driver de unidade insere um valor em um objeto de modelo a partir de uma coluna da tabela subjacente. Os drivers de unidade são normalmente utilizados no nível mais baixo de um modelo, onde os dados financeiros são inseridos no sistema.

**Configuração do driver da unidade**

|  |  |  |  |
| --- | --- | --- | --- |
| **Parâmetro** | **Necessário** | **Valores** | **Descrição** |
| Nome | Sim | Sequência de texto | Nome de exibição do motorista |
| Adicionar a | Sim | Seleção de métrica | A quais métricas este driver se aplica |
| Está usando | Sim | Coluna, Métrico, Fórmula | Origem do valor do driver |
| Notas | Não | Sequência de texto | Documentação para o motorista |

**Como usar as opções**

|  |  |  |
| --- | --- | --- |
| **Opção** | **Origem** | **Caso de uso** |
| Coluna | Valor de uma coluna da tabela | O mais comum. Mapeamento direto da coluna de custo/orçamento |
| Métrica | Valor proveniente de outra métrica do modelo | Quando o driver depende de outra métrica calculada |
| Fórmula | Valor calculado a partir da fórmula | Cálculos complexos ou referências entre tabelas |

**Exemplo: Criação de um driver de unidade**

Criar um driver de unidade para um OpEx a custa:

1. Dê uma olhada na tabela e clique na etapa “Modelo”
2. Na área de trabalho do Modelo, clique em “Adicionar driver de unidade” na coluna “Drivers”
3. Em “Adicionar a”, selecione a métrica “Custo”
4. Em “Usar”, selecione “Coluna” e escolha a coluna “ OpEx ”
5. Salvar alterações

*→ Consulte a seção [“Adicionar drivers de unidade” para obter o procedimento detalhado](../../howtoguides/build-cost-model/adv-model.html)*

**Motor de alocação**

**Descrição:** Os controladores de alocação aparecem no lado esquerdo da área de trabalho de edição do modelo e representam as alocações recebidas de outros objetos do modelo. Elas são criadas automaticamente quando você configura uma alocação de um objeto de origem para um objeto de destino.

**Observação:** os drivers de alocação são exibidos entre parênteses quando se utilizam nomes padrão. Os nomes personalizados não levam parênteses.

**Piloto de Fórmula**

**Descrição:** Um piloto de Fórmula utiliza um cálculo para determinar o valor. As fórmulas podem fazer referência a colunas de tabelas, outras métricas ou valores de outras tabelas.

**Exemplos de sintaxe de fórmulas**

|  |  |
| --- | --- |
| **Propósito** | **Fórmula** |
| Coluna de referência na mesma tabela | table.column nome |
| Somar todos os valores de uma coluna | tabela:nome da coluna |
| Soma condicional | tabela:coluna[ column2= "valor"] |
| Métrica de corrente de referência | $\_ (abreviação de “nome métrico”) |
| Referência entre projetos | projeto!tabela:nome da coluna |

*→ Consulte a seção Fórmulas e funções do 5.4: para obter uma referência completa às fórmulas*

- **[Opções de configuração do driver](../../../../studio/new-uc/reference/model-studio-reference/driver-config-option.html)**
- **[Requisitos relativos aos dados do motorista](../../../../studio/new-uc/reference/model-studio-reference/driver-data-requirements.html)**
- **[Regras de validação de motoristas](../../../../studio/new-uc/reference/model-studio-reference/driver-validation-rules.html)**
- **[Excluir um motorista](../../../../studio/new-uc/reference/model-studio-reference/delete-driver.html)**
