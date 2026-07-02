---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Métricas de negócios em Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Configuração"
  - "Organize seus gastos com a nuvem"
  - "Mapeamento de negócios"
source_path: "admin/business-metrics.html"
images:
  - "images/business-mappings-new1.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Métricas de negócios em Cloudability

**Visão geral**

As métricas de negócios permitem que você organize sua infraestrutura em nuvem de acordo com as necessidades da sua empresa. Essas métricas personalizadas permitem que você crie relatórios significativos que atendam aos requisitos financeiros e operacionais específicos da sua organização.

**O que são métricas de negócios?**

As métricas de negócios são cálculos financeiros personalizáveis que você pode definir no Cloudability para acompanhar aspectos específicos dos seus gastos com nuvem. Ao contrário das métricas padrão, as métricas de negócios permitem que você:

- Crie fórmulas personalizadas usando dados de custo existentes
- Aplicar lógica condicional com base em dimensões como fornecedor, serviço ou conta
- Transformar dados brutos de custos de nuvem em métricas financeiras relevantes para os negócios
- Definir condições específicas para determinar quando as métricas devem ser aplicadas

**Criação de uma métrica de negócios (usando a interface do usuário d Cloudability )**

Para criar uma métrica de negócios, siga as etapas abaixo:

1. Acesse a seção “Mapeamento de Negócios”.
2. Selecione a guia “Métricas”.
3. Clique no botão “Nova métrica de negócios”.
4. Digite um nome significativo para sua métrica.
5. Escolha o formato do valor (Moeda ou Número).
6. Configure a definição da métrica usando uma das seguintes opções:
   - Valor padrão: um valor simples ou uma referência métrica

     Métrica de valor fixo

     Cenário: Custo padrão por funcionário para repasse de despesas

     ```
     Metric Name: "Cost Per Employee" 
     Type: Default Value 
     Value: 150 
     Usage: Allocate $150 per employee per month for cloud infrastructure
     ```

     Referência métrica

     Calcular o índice de eficiência de custos

     ```
     Metric Name: "Cost Efficiency Ratio" 
     Type: Default Value 
     Formula: Total_Cost / Total_Usage_Hours 
     Where: 
     Total_Cost = Sum of all cloud costs 
     Total_Usage_Hours = Sum of instance hours
     ```
   - Expressão pré-partida: Condições que determinam quando a métrica se aplica

     Cenário: Taxas de alocação de custos diferentes para ambientes distintos

     ```
     Metric Name: "Environment Cost Multiplier"
     Type: Prematch Expression
      
     Prematch Expression 1:
       IF tag:Environment = "Production"
       THEN Multiplier = 1.0
      
     Prematch Expression 2:
       IF tag:Environment = "Staging"
       THEN Multiplier = 0.5
      
     Prematch Expression 3:
       IF tag:Environment = "Development"
       THEN Multiplier = 0.3
      
     Default:
       Multiplier = 0.1
     ```

**Definindo a lógica das suas métricas**

As métricas de negócios utilizam instruções para definir seu comportamento. Cada declaração é composta por:

1. Expressão de correspondência: Condições que determinam quando a instrução se aplica
   - Exemplo: DIMENSION['fornecedor'] == ' GCP '
   - Exemplo: DIMENSION['date'] >= '2021-12-01' && DIMENSION['date'] < '2026-12-01'
2. Expressão de valor: o cálculo a ser realizado quando as condições forem atendidas
   - Exemplo: METRIC['bytes\_transferred']
   - Exemplo: METRIC['unblended\_cost']
   - Exemplo: {Cost (Adjusted Amortized)} \* 0.83
3. ![captura de tela dos mapeamentos de negócios](../../../../03-media/cloudability-premium/images/business-mappings-new1.png)

É possível criar várias instruções para uma única métrica, e elas serão avaliadas na ordem em que aparecem na lista.

**Utilização de métricas de negócios em relatórios**

Depois de criadas, suas métricas de negócios podem ser utilizadas em relatórios da mesma forma que qualquer métrica padrão:

1. Crie ou edite um relatório.
2. Adicione sua métrica de negócios personalizada ao relatório.
3. Combine com dimensões como mapeamentos de “ ATUM ”, fornecedor ou nome do serviço.

**Casos de uso comuns**

- Normalização de custos: Criar métricas que normalizem os custos entre diferentes provedores de nuvem
- Preços internos: Implementar modelos de preços personalizados para cobranças internas
- Acompanhamento do orçamento: acompanhe os gastos em relação aos orçamentos predefinidos
- Cálculos de economia: Calcule a economia efetiva ou potencial resultante das iniciativas de otimização
- Amortização personalizada: defina suas próprias regras de amortização para instâncias reservadas ou planos de economia
- Economia por unidade: Calcule o custo por usuário, por transação ou por usuário para entender melhor sua economia

**Recursos avançados**

- Use operadores matemáticos (+, -, \*, /) para criar fórmulas complexas
- Faça referência a métricas existentes usando a sintaxe {}
- Aplique lógica condicional usando os operadores && (AND) e || (OR)
- Filtrar com base em valores específicos de dimensões, como fornecedor, nome do serviço ou região

**Como as métricas de negócios funcionam em conjunto com os mapeamentos de negócios?**

As métricas de negócios são elaboradas por meio de declarações de mapeamento de negócios que utilizam uma combinação de dados de faturamento existentes e dados fornecidos pelos clientes. Os usuários podem criar métricas personalizadas relacionadas aos conceitos de faturamento do Cloud, preenchidas com os valores específicos derivados da lógica que melhor atenda às suas necessidades de relatórios no contexto de seus negócios.

**Avaliado no momento da ingestão**

Quando o Cloudability recebe os dados detalhados de faturamento dos fornecedores de nuvem, avaliamos cada item de custo em relação às declarações de mapeamento de negócios para as métricas de negócios configuradas por você. Para aqueles que têm conhecimentos de programação, podem pensar na lista de instruções como algo semelhante a uma instrução `case`. Assim que houver uma correspondência, o nome da própria instrução é avaliado, e o valor resultante é calculado aritmeticamente e utilizado para preencher a Métrica de Negócios desse item. Esse nome de métrica personalizada pode ser simplesmente uma sequência de caracteres significativa que você fornecer. Quando os provedores de serviços em nuvem publicarem novos dados de faturamento, detectaremos automaticamente quaisquer alterações ou acréscimos que você fizer em seus extratos do Business Mapping. Para que os meses históricos reflitam as regras atualizadas, você pode entrar em contato com o suporte ou com seu TAM para que isso seja providenciado.

**O nome da métrica personalizada**

Cada métrica de negócios que você criar precisa ter um nome. Reflita bem sobre o contexto empresarial que você está tentando transmitir e escolha um nome que as pessoas consigam entender rapidamente. Você está definindo um nome para a métrica personalizada, que será exibido nos relatórios e painéis d Cloudability.

**O formato de métrica personalizado**

Além do nome, você deve decidir se essa métrica personalizada exibirá dados no formato de moeda ou de número comum. O caso de uso que motiva essa métrica personalizada ajudará você a decidir qual é o formato adequado.

Por exemplo: se o seu caso de uso for aplicar uma sobretaxa para cobrir taxas de administração, o formato da métrica personalizada será “moeda”.

**O valor padrão**

Depois de decidir o nome e o formato, é preciso definir um valor padrão. Este é o valor que a métrica de negócios herdará caso nenhuma das condições declaradas por você seja atendida.

Por exemplo: uma opção seria utilizar o valor do custo já constante nos dados de faturamento. À medida que você for definindo suas métricas de negócios, cada caso de uso ajudará a determinar um bom valor padrão.

**Trata-se de fazer correspondências com afirmações**

Toda instrução possui dois componentes:

Uma expressão que define o que deve ser comparado. Essa expressão pode envolver lógica booleana complexa, um intervalo de tempo e possui uma lista bastante abrangente de operadores que podem ser aplicados a todos os atributos importantes dos itens de custo.

Uma expressão a ser avaliada, que resulta no valor da métrica de negócios caso os critérios do item 1 sejam atendidos.

Veja a seguir um exemplo simples:

```
"statements": [{
	"matchExpression": "DIMENSION['vendor'] == 'Amazon'
		|| DIMENSION['vendor'] == 'Azure' ",
	"valueExpression": "METRIC['unblended_cost'] * 1.15"
}]
```

**Por que você usa métricas de negócios?**

**Casos de uso**

As métricas de negócios podem ajudar a atender a diversos casos de uso em que, além das métricas nativas do Cloudability, você pode precisar de métricas personalizadas para atender às necessidades de relatórios da sua empresa. A seguir, apresentamos exemplos de alguns dos casos de uso mais comuns entre os clientes:

|  |  |
| --- | --- |
| Economia unitária | Também conhecido como Custo por X. Um cliente pode contextualizar seus gastos com a nuvem como um custo unitário em uma única métrica dentro do aplicativo. Por exemplo: custo por viagem, custo por usuário ativo, custo por assinatura, etc. |
| Custo orientado por KPIs | Custo no contexto de um KPI específico da empresa. Por exemplo, um cliente pode contextualizar o custo em termos de engenheiros em tempo integral (custo em FTEs) para entender seus gastos com nuvem em termos do número de engenheiros de DevOps necessários para dar suporte a um aplicativo implantado. |
| Sobretaxa/Aumento de preço | É possível incorporar uma sobretaxa ou margem de lucro para gastos com nuvem e apresentar os custos, incluindo taxas de gestão, custos de licença ou outras sobretaxas, por meio de uma única métrica no aplicativo. |

O mecanismo de regras que controla esse recurso está equipado com recursos lógicos sofisticados, e as regras individuais podem se basear em praticamente todos os atributos importantes que os fornecedores disponibilizam junto aos dados de faturamento e uso. Esses atributos incluem dimensões e métricas fornecidas pelos fornecedores, como etiquetas de custo, nomes de contas e custo não ajustado, mas também incluem dimensões e métricas aprimoradas fornecidas pelo Cloudability, como Família de Uso, Tipo de Contrato de Locação e Custo Ajustado.

**Criação de uma métrica de negócios (usando a API d Cloudability )**

É possível criar métricas de negócios por meio da API, utilizando a linguagem de expressões do Business Mapping. As regras são definidas por meio de expressões e instruções no formato JSON, que são avaliadas aritmeticamente, resultando em uma métrica personalizada e no valor correspondente.

**Trabalhando com métricas de negócios**

No [Endpoint de Mapeamentos de Negócios](../api-v3/business_mappings_endpoint.html), você pode ver uma visão geral dos recursos, incluindo os endpoints de Métricas de Negócios com as respectivas descrições e exemplos disponíveis para você trabalhar com as Métricas de Negócios. Além disso, você encontrará modelos que podem ser usados para ajudar a dar o pontapé inicial na configuração de suas métricas personalizadas, além de outros recursos úteis.

Você pode configurar no máximo cinco métricas de negócios.

A seguir, apresentamos referências rápidas e exemplos para (i) listar uma métrica de negócios que você já criou, (ii) criar uma nova métrica de negócios e (iii) atualizar uma métrica de negócios existente.

**Métrica de negócios de listagem**

```
 curl -X GET 'https://api.cloudability.com/v3/business-mappings/metrics/' -u '[auth_token]:'
```

**Criar uma métrica de negócios**

```
 curl -X POST 'https://api.cloudability.com/v3/internal/business-mappings/metrics/' \
  -H 'Content-Type: application/json' \
  -u '[auth_token]:' \
  -d @- >> EOF
{
  "name": "Cost (Surcharge)",
  "numberFormat": "number",
  "defaultValueExpression": "METRIC['unblended_cost']",
  "statements": [
    {
      "matchExpression": "DIMENSION['vendor'] == 'Amazon' || DIMENSION['vendor'] == 'Azure' ",
      "valueExpression": "METRIC['unblended_cost'] * 1.15"
    }
  ]
}
EOF
```

**Resultado esperado**

```
{
  "result": {
    "name": "Cost (Surcharge)",
    "index": 1,
    "kind": "BUSINESS_METRIC",
    "defaultValue": "METRIC['unblended_cost']",
    "numberFormat": "number",
    "updatedAt": "2025-11-12T07:29:27.182Z",
    "statements": [
      {
        "matchExpression": "DIMENSION['vendor'] == 'Amazon' || DIMENSION['vendor'] == 'Azure' ",
        "valueExpression": "METRIC['unblended_cost'] * 1.15"
      }
    ]
  }
}
```

**Atualizar uma métrica de negócios**

```
curl -X PUT 'https://api.cloudability.com/v3/internal/business-mappings/1/metrics/' \
  -H 'Content-Type: application/json' \
  -u '[auth_token]:' \
  -d @- >> EOF
{
  "name": "Cost (Surcharge)",
  "numberFormat": "number",
  "defaultValueExpression": "METRIC['unblended_cost']",
  "statements": [
    {
      "matchExpression": "DIMENSION['vendor'] == 'Amazon' || DIMENSION['vendor'] == 'Azure' ",
      "valueExpression": "METRIC['unblended_cost'] * 1.25"
    }
  ]
}
EOF
```

**Resultado esperado**

```
 {
  "result": {
    "name": "Cost (Surcharge)",
    "index": 1,
    "kind": "BUSINESS_METRIC",
    "defaultValue": "METRIC['unblended_cost']",
    "numberFormat": "number",
    "updatedAt": "2025-11-12T07:32:16.858Z",
    "statements": [
      {
        "matchExpression": "DIMENSION['vendor'] == 'Amazon' || DIMENSION['vendor'] == 'Azure' ",
        "valueExpression": "METRIC['unblended_cost'] * 1.25"
      }
    ]
  }
}
```

**Operadores**

Ao utilizar a linguagem de expressões do Business Mappings, você terá à disposição uma ampla variedade de operadores para testar a lógica de suas instruções. Alguns exemplos de operadores que você pode usar incluem o operador “maior que”, que pode ser útil para comparar valores como datas. Escolha um operador que torne sua expressão o mais direta possível. Ao utilizar nossa API, você terá opções adicionais, incluindo expressões regulares.

Por exemplo, definir um intervalo de tempo para o valor de uma métrica de negócios entre duas datas:

```
 {
  "name": "Cost (Surcharge)",
  "numberFormat": "number",
  "defaultValueExpression": "METRIC['unblended_cost']",
  "statements": [
    {
      "matchExpression": "DIMENSION['date'] >= '2019-01-01T00:00' && DIMENSION['date'] <= '2019-01-31T23:59'",
      "valueExpression": "METRIC['unblended_cost'] * 1.25"
    }
  ]
}
```

**Lógica booleana**

Dentro de uma instrução, é possível agrupar expressões usando operadores OR e combiná-las com operadores AND para obter o resultado lógico exato que atenda às suas regras de negócios.

Segue abaixo um exemplo bem básico:

```
{
  "name": "Cost (in FTEs)",
  "numberFormat": "number",
  "defaultValueExpression": "METRIC['unblended_cost']",
  "statements": [
    {
      "matchExpression": "DIMENSION['date'] >= '2019-01-01T00:00:00' && DIMENSION['date'] <= '2019-01-31T23:59:59' && (DIMENSION['transaction_type'] == 'usage' || DIMENSION['transaction_type'] == 'recurring')",
      "valueExpression": "METRIC['unblended_cost']  / 115000"
    }
  ]
}
```

Para obter orientações adicionais sobre como utilizar o Business Metrics de forma eficaz, entre em contato com o representante da sua conta ou envie um ticket de suporte.

**Tópico principal:** [Mapeamento de negócios](../admin/business-tags.html)
