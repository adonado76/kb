---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Usando recomendações de compromisso para analisar oportunidades de economia"
breadcrumb:
  - "Cloudability Premium"
  - "Otimizar"
  - "Guia para a gestão de compromissos"
source_path: "product/using_commitment_recommendations_to_analyze_savings_opportunities.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Usando recomendações de compromisso para analisar oportunidades de economia

## Propósito

O objetivo deste documento é fornecer uma visão geral de como usar as Recomendações de Compromisso. Em um nível resumido, você usa as Recomendações de Compromisso para entender onde existem oportunidades de economia com base em seus gastos atuais com a nuvem e nos compromissos que você já possui. As recomendações são geradas por um modelo proprietário que aplica suas preferências e restrições comerciais. A página de detalhes permite que você execute análises de sensibilidade e análises hipotéticas para criar um caso de negócios para compras incrementais e moldar uma estratégia de compromisso otimizada para sua organização.

## Como acessar e usar

A página Recomendações de compromisso está localizada na seção Otimizar no menu de navegação à esquerda e, assim como o portfólio, é organizada por fornecedor.cada guia compartilha uma estrutura comum para que você possa comparar as nuvens sem trocar de modelos mentais. A barra de ferramentas do cabeçalho permite que você crie uma exibição de recomendação focada:

**Tipo de compromisso**

Essa seleção é organizada por fornecedor ( AWS ), por serviço ( EC2 ) e por tipo de compromisso ( EC2 Instâncias reservadas). Observe que a página de serviço intermediário não é necessária quando há um único tipo de compromisso que cobre o serviço.

- **Todos os níveis** (página de destino baseada no fornecedor): Mostra todos os serviços/tipos suportados para o fornecedor selecionado.
- **Nível de serviço** : Mostra todos os tipos de compromisso compatíveis com o serviço selecionado.
- **Nível de tipo** : Mostrou todos os tipos de compromisso para os vários tipos.

Notavelmente, as páginas agregadas no nível do fornecedor e do serviço garantem que as recomendações fornecidas sejam mutuamente exclusivas umas das outras. Para obter mais informações sobre esse comportamento, consulte a seção de tipo de recomendação abaixo.

**Conta**

O selecionador de contas escolhe o uso das contas que nosso modelo analisará para uma recomendação. Geralmente, é uma prática recomendada escolher uma seleção de conta que corresponda às suas preferências de compartilhamento configuradas no console do fornecedor. Como não temos um sistema para consultar essas informações, oferecemos a opção de configurar isso no aplicativo. O seletor representa a natureza hierárquica de suas contas e é de seleção múltipla.

- A seleção de uma ou mais contas de pagador (Gerenciamento, Assinatura, Faturamento) seleciona todas as contas vinculadas abaixo dela.
- A seleção de conta(s) vinculada(s) específica(s) (Membro, Assinatura, Projeto) mostra um estado de seleção parcial na conta do pagador.

  Para obter mais informações sobre a terminologia da conta, consulte [Estrutura da conta por fornecedor](commitments_vendor_account_structure.html)

**Ação**

Relevante apenas para AWS neste momento, essa seleção permite que você escolha se deseja avaliar recomendações de compra, troca ou subutilização. Isso é particularmente relevante para o serviço de instâncias reservadas conversíveis do AWS EC2, que oferecem maior flexibilidade para atingir níveis mais elevados de cobertura.

**Termo**

Essa seleção informa ao nosso modelo qual comprimento de termo deve ser analisado nas recomendações fornecidas. Para os tipos de recomendação ideal e de destino, esse menu suspenso exibirá Mix quando várias recomendações de termos forem mostradas na página.

**Base de custo**

A escolha de preços de lista ou ajustados permite que os usuários entendam suas recomendações a partir de preços de lista ou negociados sob demanda e de compromisso. Os KPIs e as tabelas refletem a base que você selecionou. Observe que as páginas de compromisso do Azure talvez ainda não apresentem uma alternância. Quando presentes, os valores refletem o Custom quando aplicável. Para obter mais informações, consulte [Como os fatores de preços negociados afetam os compromissos](custom_pricing_factors_across_commitments.html).

**Período de análise**

Essa seleção orienta todos os KPIs e metadados da tabela na página. O perfil de uso padrão, o nome de preferência do período de análise padrão na página de recomendações, é o último mês anterior e as horas estão em UTC. Nossa sugestão é evitar a geração de relatórios sobre as 24 horas mais recentes para permitir que os dados concluam o processamento em nosso pipeline. Para obter mais informações, consulte [Atualização de dados](data_freshness.html).

É importante ressaltar que nosso modelo atual é orientado exclusivamente pelo período de análise selecionado. Para obter mais informações sobre como selecionar um intervalo de análise apropriado para seu caso de uso, consulte o Perfil de uso.

**Opção de Pagamento**

Especificamente para AWS e Azure, essa seleção determina como as recomendações selecionadas serão pagas. Em geral, há um desconto adicional para pagamentos antecipados.

**Classe de oferta**

Especificamente para as Instâncias Reservadas do AWS EC2, esta seleção determina se serão fornecidas recomendações padrão ou conversíveis.

**Preferência por região**

Especificamente para as Instâncias Reservadas do AWS EC2, esta seleção determina se as recomendações devem ser limitadas a uma região ou a uma zona de disponibilidade.

**Compartilhamento de contas**

Essa seleção determina se as recomendações serão fornecidas com escopo para contas individuais ou agregadas no pagador.

**Limites de taxa**

Essa seleção funciona como um filtro simples para especificar quais limiares de taxa de utilização e economia são relevantes no cálculo das recomendações

## Interpretação dos KPIs de recomendação

Todos os KPIs são esperados com base em nosso modelo de recomendação. Eles são formalmente retirados do período de análise selecionado.

- A economia líquida é definida como a economia bruta esperada menos o desperdício esperado das compras propostas no escopo.
- PSR (esperado), CSR (esperado) e CDR (conhecido) são usados para ajudar a interpretar as recomendações
- Mostramos a cobertura atual e futura para mostrar como a cobertura mudaria se as recomendações especificadas fossem adquiridas.
- A utilização é ponderada pelo impacto/tamanho relativo das recomendações na tabela.

## Página de resumo e detalhes por tipo

Abaixo do cabeçalho está a tabela. Cada linha resume uma recomendação. As colunas se adaptam ao tipo de compromisso selecionado.diferentemente da gaveta do portfólio, a ação de detalhes abre uma página de detalhes dedicada a essa recomendação. A partir daí, o escopo é focado nessa recomendação, fornecendo um gráfico e um recurso de ajuste.

**Operações e filtros de tabela**

- **Classificar** : Clique em um cabeçalho de coluna para classificar de forma descendente, clique novamente para classificar de forma ascendente e uma terceira vez para redefinir.
- **Mostrar/ocultar colunas** : Use o controle Columns para escolher quais campos serão exibidos.
- **Paginação** : Os controles de paginação padrão aparecem abaixo da tabela.
- **Exportar** : O botão Exportar gera um arquivo do tipo “ CSV ” no formato WYSIWYG (o que você vê é o que você obtém) para o escopo atual e as colunas visíveis.

**Adicionar filtro e filtragem em linha**

- Use Add Filter (abaixo do cabeçalho) para filtrar por qualquer campo suportado.
- As células com hiperlink estão disponíveis para filtragem. A seleção de uma célula vinculada filtrará a tabela por esse atributo e adicionará um chip à barra de filtros.

**Alertas e visualizações**

- **Suporte a visualizações** : A página de recomendação oferece suporte a visualizações com escopo de conta e fornecedor. Outros mapeamentos de negócios não são suportados aqui porque as métricas por compromisso não podem ser computadas de forma confiável em remapeamentos arbitrários.

****Página de detalhes da recomendação****

- **KPIs modelados** : Economia líquida, taxa de economia, cobertura e utilização para as recomendações selecionadas no momento.
- **Gráfico de análise** : Espelha a estrutura do Commitment Manager com o custo de compromisso atual sobreposto ao custo da recomendação proposta e ao custo sob demanda resultante.
- **Cartão de resumo de detalhes** : Mostra os detalhes da recomendação e as informações adicionais necessárias para avaliar a recomendação
- **Ajuste da recomendação** : O botão de ação Ajustar permite que os usuários usem nosso modelo para ajustar a recomendação. Aqui, oferecemos suporte a três métodos de ajuste. Consulte a seção Tipo de recomendação abaixo para obter mais informações.
- **Links para relatórios** : Fornecemos links para relatórios a fim de proporcionar uma compreensão das despesas comprometedoras que respaldam a recomendação. Melhoraremos isso no futuro, adicionando o modal de cobertura à página de recomendações.

## Tipo de recomendação

Cloudability produz vários modos de recomendação para atender a diferentes estilos de decisão. Esses modos estão disponíveis para comparação nas páginas de resumo e de detalhes.

**Recomendação ideal -** Essa recomendação maximiza a economia líquida dos compromissos. Assim, analisamos os diferentes parâmetros de compromisso para o tipo de compromisso selecionado, apresentando uma recomendação que oferece a maior taxa de economia esperada (CSR) com base no consumo coberto no período de análise selecionado. Em situações em que um serviço tem vários tipos de compromisso aplicáveis (computação), a página “Todos” fornecerá a recomendação ideal entre os tipos de compromisso disponíveis. As páginas dedicadas a cada tipo de compromisso ignorarão a possibilidade de utilizar outros tipos de compromisso ao determinar a recomendação ideal.

Tomando AWS como exemplo, EC2 pode ser coberto por EC2 Reserved Instances (instâncias reservadas), EC2 Instance Savings Plans (planos de economia de instâncias) e Compute Savings Plans (planos de economia de computação). Quando estiver na página de recomendações All Compute, a recomendação ideal examinará os três tipos de compromisso aplicáveis para recomendar o que é ideal em gastos comprometíveis. Quando estiver na página All EC2, a recomendação ideal examinará os dois tipos de compromisso específicos do EC2 para recomendar o que é ideal em gastos comprometíveis, ignorando os Compute Savings Plans. Por fim, na página de recomendações EC2 Instance Savings Plans, a recomendação ideal demonstrará qual é o máximo que se pode economizar com EC2 Instance Savings Plans, ignorando EC2 Reserved Instances

Nota: O comportamento ideal das recomendações foi introduzido com [as melhorias nas recomendações de compromisso](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-enterprise/saas?topic=cloudability-whats-new-in#topic__cldy-commit-mgmt-2.0subrelease "(Abre em uma nova guia ou janela)") do AWS em maio de 2026

**Recomendação de meta -** Essa recomendação maximiza a economia líquida dos compromissos, considerando as preferências configuradas.

Observação: a recomendação de destino está disponível, no momento, apenas para o GCP. O suporte a outros fornecedores está previsto para uma versão futura.

**Recomendação modificada** — Esta recomendação reflete o comportamento da página de recomendações antes da introdução do tipo de recomendação otimizada. A recomendação modificada simplesmente maximiza a economia dentro das opções modeladas. Quando uma combinação de seleções corresponde aos parâmetros de recomendação “Ótima” ou “Alvo”, a página altera o tipo de recomendação de “modificada” para “calculada”. Qualquer outra combinação de seleções resultará na modificação do tipo de recomendação.**Recomendação personalizada** — Os usuários podem personalizar uma recomendação na página de detalhes da recomendação. Para isso, basta clicar no botão “personalizar” e escolher uma das três opções disponíveis. Os três métodos de recomendação personalizados são os seguintes:

- **Valor do compromisso** : Esse método simplesmente recebe um valor com o qual você deseja se comprometer, seja em termos de custo sob demanda ou de compromisso, e fornece o resultado esperado com base na interface de usuário de recomendação.
- **Porcentagem de cobertura** : Esse método pressupõe que você deseja criar um caso de negócios para uma porcentagem de cobertura diferente da estratégia de compromisso de meta configurada. Insira uma porcentagem de cobertura e nosso modelo tentará estimar qual compra resultaria na porcentagem de cobertura desejada para a variante atual.
- **Uso mínimo sustentado** : Esse método pressupõe que você deseja cobrir todo o uso sustentado. Fornecemos uma entrada para omitir até 5% das horas de uso que são discrepantes.

  Observação: a recomendação personalizada continua levando em conta a utilização prevista com base no período de análise selecionado.

## **Usar esta página para implementar as práticas recomendadas**

- **Entenda o desempenho atual** : Sempre verifique primeiro o portfólio para ter uma sólida compreensão dos próximos vencimentos e da utilização atual.
- **Entenda o nível de cobertura atual** : Nossas recomendações não levam em conta os vencimentos de compromissos futuros
- **Entenda como o uso pode mudar** : Nossas recomendações são baseadas no uso atual e, portanto, não levam em conta aumentos ou reduções no uso.
- **Configurar preferências de compromisso** : Por padrão, definimos suas preferências de compromisso para mostrar uma recomendação de meta. Recomendamos que você revise essas preferências e as ajuste de acordo com sua empresa antes de usar a página de recomendações.
- **Compare o ideal versus o alvo versus o personalizado** : Se a cobertura ideal exceder substancialmente a cobertura alvo, valide sua tolerância ao risco ajustando suas preferências de compromisso. Você pode estar deixando uma economia significativa de lado. Use entradas personalizadas para desenvolver um entendimento em nível de resumo de como as diferentes preferências podem afetar suas recomendações
- **Crie um caso de negócios** : Use a página de detalhes das recomendações para criar um caso de negócios para uma estratégia de cobertura de longo prazo ou uma compra incremental.

## Principais conclusões

- As recomendações refletem a estrutura do portfólio, mas são prospectivas e práticas.
- A página de detalhes é um espaço de trabalho completo: inspecione suposições, visualize gráficos e ajuste propostas.
- Use os modos Optimal/Target/Custom/Adjusted para alinhar as decisões às restrições de risco, política e caixa.
- Configure as preferências para configurar a recomendação de destino; use [Cobertura](coverage_modal.html) e [Economia Líquida](net_savings_modal.html) no portfólio para obter contexto adicional.

**Tópico dos pais:** [Guia para gerenciamento de compromissos](../product/guide_to_commitment_management.html)
