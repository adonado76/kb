---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Modalidade de cobertura"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Guia para a funcionalidade de compromisso avançado"
source_path: "product/coverage_modal.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Modalidade de cobertura

## Propósito

Conforme discutido anteriormente, a cobertura é um importante KPI. Isso oferece uma visão tanto do desempenho — o que você já otimizou em termos de taxas por meio de compromissos — quanto do risco — qual porcentagem do seu gasto total comprometível está coberta no momento. A janela modal de cobertura explica como esse KPI é calculado, a fim de transmitir confiança aos nossos usuários e revelar insights sobre desempenho e oportunidades.

## Como acessar

Atualmente, é possível acessar a janela modal de cobertura por meio do botão “Detalhes” no KPI de cobertura na página do portfólio. Temos planos futuros para disponibilizar o acesso a essa janela nas páginas de recomendações e de gerenciamento. A janela modal herda a seleção atual do cabeçalho e os filtros da página, de modo que os dados da janela modal estejam sempre em contexto com o que você estava visualizando anteriormente.

## Layout da janela modal de cobertura

**Cálculo da cobertura:** O modal mostrará, em primeiro lugar, quais foram os dois valores do gráfico abaixo utilizados para calcular a métrica de cobertura.

**Discriminação das métricas de cobertura** : O modal, então, detalha cada um dos custos cobertos e não cobertos. Inspirando-se em um balanço financeiro, os valores que aparecem em cada linha são a soma dos valores anteriores.

**Resumo da cobertura do fornecedor** : Para oferecer uma noção da relevância na avaliação de diferentes métricas de cobertura de serviços, apresentamos os valores de ODE cobertos, não cobertos e inelegíveis para o fornecedor selecionado. Observe que esta seção não é alterada pela seleção atual do cabeçalho nem pelos filtros da página subjacente.

**Importante** : Todos os valores no Modal de Cobertura são expressos em termos de custos equivalentes à demanda (ODE). Para valores “não cobertos”, isso significa que eles se referem à demanda, e, portanto, o valor da demanda = ODE. Para valores “abrangidos”, isso significa que o valor exibido não é o custo, mas sim o ODE. Isso permite uma comparação direta entre os custos cobertos e os não cobertos.

## Terminologia relativa ao modal de cobertura

Todos os valores são expressos em termos de ODE. Primeiro, um lembrete sobre dois termos importantes:

**Compromissos baseados em recursos:**  Abreviados como compromissos de recursos. Oferece um desconto em troca do compromisso de utilizar uma determinada quantidade de um produto ou serviço (Instância Reservada, CUD).

**Compromissos baseados em gastos:** abreviados como “compromissos de gastos”. Oferece um desconto em troca do compromisso de gastar um determinado valor em um produto ou serviço (Plano de Poupança, CUD Flexível).

*Discriminação das métricas de cobertura - Cobertos*

- **Cobertura do recurso** : O valor coberto pelos compromissos baseados em recursos.
- **Despesas Cobertas** : O valor coberto por compromissos baseados em despesas.
- **Despesas Cobertas, Recursos Elegíveis** : Parte coberta por compromissos de despesas que poderia ter sido coberta por compromissos de recursos, considerando as mesmas regras de elegibilidade.
- **Coberto por recursos, elegível para despesas** : Parte coberta por compromissos de recursos que poderia ter sido coberta por compromissos de despesas, considerando as mesmas regras de elegibilidade.
- **Valor total coberto** : O ODE do valor total coberto.

*Discriminação das métricas de cobertura — Sem cobertura*

- **Despesas** **não cobertas exclusivas** : uso sob demanda que só um compromisso de despesas poderia ter coberto.
- **Recurso exclusivo** **não coberto** : uso sob demanda que só poderia ter sido coberto por um compromisso de recurso.
- **Não exclusivo** **não coberto** : uso sob demanda que poderia ter sido coberto por um recurso ou por um compromisso de gastos.
- **Valor total não coberto** : O valor total que poderia ter sido coberto, mas não foi.

*Discriminação das métricas de cobertura – Valor total*

- **Valor total** : o valor total coberto + o valor total não coberto. Outra interpretação é que esse valor representa a equação diferencial ordinária (ODE) do que poderia ter sido ou foi coberto pelos compromissos.

*Resumo da cobertura de fornecedores*

- **Valor coberto** : O valor dos compromissos cobertos. Observe que esse valor não leva em conta o custo de compromisso que não foi utilizado.
- **Valor não coberto** : O valor que não foi coberto pelos compromissos. Como foi cobrado sob demanda, isso pode ser considerado tanto como ODE quanto como custo real.
- **Não elegível para compromisso** : Custos que não podem ser cobertos por compromissos devido a regras relacionadas ao tipo de serviço ou uso.
- **Valor total do serviço** : O ODE total (custo caso não tenham sido adquiridos compromissos para o fornecedor em questão) dos serviços suportados por compromissos d Cloudability. (Veja o resumo dos tipos de compromisso)
- **Créditos de Desconto por Uso Contínuo (SUDs)** : Um desconto mensal específico do GCP para o uso contínuo do GCE, quando não houver outros descontos em vigor. É algo de menor importância, mas incluímos aqui para que todos fiquem cientes.

## Uso coberto x uso não coberto: como interpretar

A cobertura ajuda você a responder a duas perguntas:

1. Qual foi a parcela da minha demanda elegível que foi otimizada por meio de tarifas com desconto? (coberto)
2. Em que casos os compromissos poderiam ter sido aplicados, mas não foram? (à vista)

*Possíveis interpretações dos dados*

- Uma alta parcela de “Spend Covered” com grande sobreposição com “Resource Eligible” pode indicar margem para converter parte da demanda em mais compromissos de recursos, que geralmente apresentam uma taxa de desconto de compromisso (CDR) mais elevada.
- O nível “Alto, Não Exclusivo, Não Coberto” sugere uma ampla oportunidade — tanto compromissos com recursos quanto com gastos poderiam preencher essa lacuna. Use as recomendações para determinar qual combinação de categorias é a mais adequada para sua tolerância ao risco.
- O indicador “High Resource Exclusive Uncovered” frequentemente aponta famílias de instâncias ou regiões específicas que não contam com alocações de recursos. Os compromissos de gastos não se aplicariam neste caso; portanto, é necessário criar uma estratégia de compromisso específica para recursos a fim de otimizar esses gastos.
- O programa “High Spend Exclusive Uncovered” pode indicar padrões de uso pouco frequentes, mistos ou entre serviços, mais adequados a compromissos de gastos. Conforte-se sabendo que esse gasto não pode ser otimizado ainda mais com a alocação de recursos.

Lembrete: Se sua organização utiliza preços personalizados, a linha de base do ODE refletirá essas tarifas; as taxas de economia derivadas do ODE serão diferentes das linhas de base do varejo.

## Integração de links de relatórios

A partir da versão “ GCP ”, introduzimos links diretos nos valores exibidos na janela modal de cobertura. Esses links abrem uma nova aba e geram um relatório usando o recurso de relatórios nativo d Cloudability. Esse recurso amplia ainda mais a finalidade original do modal ao:

- Divulgar os custos subjacentes, de modo a garantir total transparência sobre como o KPI de cobertura foi calculado.
- Exposição dos custos subjacentes cobertos para casos de uso de estorno/reembolso.
- Apresentar os custos cobertos subjacentes para compreender o que estava coberto, com o objetivo de determinar se a renovação do compromisso é adequada.
- Revelar os custos subjacentes não cobertos para avaliar se esse custo é estável o suficiente a ponto de gerar economia caso seja coberto por um compromisso. Em conjunto com a funcionalidade de recomendações, os usuários podem adquirir confiança de que objetivos futuros resultarão em um desfecho positivo para um risco que vale a pena correr.

## Principais conclusões

- A cobertura é apresentada em ODE para padronizar a interpretação entre os prestadores.
- O modal distingue o que foi coberto do que poderia ter sido coberto e classifica a parte não coberta de acordo com a elegibilidade (apenas recursos, apenas despesas ou ambos).
- Use os links de relatórios para passar do sinal à causa raiz e, em seguida, teste estratégias nas Recomendações de Compromisso.

**Tópico principal:** [Guia sobre funcionalidades avançadas de compromisso](../product/guide_to_advanced_commitment_functionality.html)
