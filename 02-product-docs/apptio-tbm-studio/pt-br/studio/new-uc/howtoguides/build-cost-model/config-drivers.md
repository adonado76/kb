---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurar drivers para alocações"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Criar modelos de custos"
  - "Criar alocações"
source_path: "studio/new-uc/howtoguides/build-cost-model/config-drivers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar drivers para alocações

**Objetivo:** Criar fatores de alocação que controlem com precisão o fluxo de custos das tabelas de origem para as tabelas de destino, utilizando condições de correspondência e colunas de ponderação.

**Quando usar:** Você precisa de um controle detalhado sobre o comportamento da alocação, incluindo a atribuição de custos a linhas-alvo específicas com base em atributos compartilhados (como ID do fornecedor ou conta) e a aplicação de uma lógica de ponderação personalizada.

**Tempo estimado:** 20 a 30 minutos

## Compreendendo os fatores determinantes

Os fatores determinantes definem a mecânica da distribuição de custos. Existem dois tipos:

**Drivers de unidade:** definem como os valores são inseridos em um objeto de modelo a partir dos dados subjacentes. Os drivers de unidade fazem referência às colunas da tabela de origem.

**Motores de alocação:** definem como o valor flui de um objeto do modelo para outro. Os fatores de alocação especificam a lógica de correspondência e o comportamento de ponderação.

## Passo a passo: Configurar um driver de alocação com correspondência

**Cenário:** Alocar os custos de fornecedores aos serviços de tecnologia, fazendo a correspondência entre o ID do fornecedor e a conta, ponderada pela coluna “Ponderação de alocação”.

1. **Abra a etapa "Modelo" da tabela de origem**
   - Acesse a tabela de origem (por exemplo, “Fornecedores”) no Explorador de Projetos.
   - Clique na etapa “Modelo” no fluxo de transformação.
2. **Criar ou editar a alocação**
   - Clique em “Adicionar alocação” ou selecione uma alocação existente para editar.
   - Definir: Alocar = Custo, Utilizando = Valor ponderado, Para = Serviços de Tecnologia.
3. **Configurar condições de correspondência (Relação de dados)**
   - Na seção "Relação de dados", clique para adicionar colunas correspondentes.
   - Adicione os pares: ID do fornecedor → ID do fornecedor, Conta → Conta, Tipo de despesa → Tipo de despesa.

   Observação: ambas as colunas devem existir nas respectivas tabelas. Os valores devem corresponder exatamente para que os custos sejam alocados.
4. **Defina a coluna de ponderação**
   - Em “Peso por”, selecione “Tabela”.
   - Selecione a coluna de ponderação (por exemplo, “Ponderação de alocação”).
   - Certifique-se de que esta coluna contenha valores numéricos, sem valores nulos ou negativos.
5. **Visualizar e verificar**
   - Clique em “Visualizar” para examinar os resultados da alocação.
   - Verifique se há linhas não atribuídas (linhas sem destinos correspondentes).
6. **Salvar a configuração do driver**
   - Clique em Salvar para confirmar a alocação.
   - Verifique na tabela quando todas as alocações estiverem concluídas.

## Melhores práticas para configuração de drivers

**Mantenha as tabelas de drivers pequenas e organizadas**

- Inclua apenas as colunas necessárias para a correspondência e a ponderação.
- Remova as colunas não utilizadas para melhorar o desempenho.
- Documente o objetivo do driver para futuros mantenedores.

**Use a correspondência explícita em vez da automática**

- A correspondência automática (recurso antigo) pode gerar resultados inesperados.
- Sempre especifique explicitamente os pares de colunas de origem e destino.
- Se você vir a caixa de seleção "Relação automática", desmarque-a e configure chaves explícitas.

**Verifique se os tipos de dados correspondem**

- As colunas correspondentes devem ter o mesmo tipo de dados (texto com texto, número com número).
- A correspondência de texto diferencia maiúsculas de minúsculas.
- Remova os espaços em branco das colunas de texto no ` Data Studio ` caso a correspondência falhe inesperadamente.

## Referência de tipos de drivers

|  |  |  |
| --- | --- | --- |
| **Tipo de motorista** | **Definição** | **Exemplo de caso de uso** |
| **Coluna** | Valor obtido de uma coluna da tabela | Número de servidores, área útil, número de usuários |
| **Métrica** | Valor obtido de outra métrica do modelo | Use a métrica de custo para ponderar a alocação do orçamento |
| **Fórmula** | Valor calculado usando uma fórmula personalizada | Lógica de ponderação complexa, distribuição condicional |

**Tópico principal:** [Criar alocações](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
