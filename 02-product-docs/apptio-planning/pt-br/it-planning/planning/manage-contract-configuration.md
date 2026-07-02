---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Configurar contratos"
breadcrumb: []
source_path: "it-planning/planning/manage-contract-configuration.html"
images:
  - "resources/images/icons/3-dots.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurar contratos

As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

As dimensões são as categorias de dados essenciais nos itens de linha do orçamento. Muitas dimensões incorporadas têm dependências de outras dimensões (consulte [Dependências de atributos e dimensões de dados de referência](manage-reference-data.html) para obter mais informações). Você pode importar dados de referência de dimensões de um arquivo.csv ou do site Costing Standard e exportar modelos de dados de referência de dimensões e dados de tabela (consulte [Gerenciar dimensões](manage-reference-data.html) ).

![ver ícone](../../resources/images/it%20planning_images/icon_video.png)

## Gerenciar dados de referência do tipo de contrato

Um proprietário ou administrador do processo orçamentário pode definir regras para controlar como os tipos de contrato são contabilizados nos orçamentos do site OpEx. Você pode especificar que um determinado tipo de contrato sempre seja acumulado em uma conta OpEx específica com um método de amortização específico.

1. Ative os recursos de Contratos e IVA no Perfil da empresa (consulte [Editar o perfil da empresa.](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.")
2. No menu de navegação, selecione Configuração > Dados de referência > Tipo de contrato.
3. Selecione ![mais ícone](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) no canto superior direito da tabela, selecione Exportar > Exportar tudo.
4. Atualize os valores da tabela de dados conforme necessário no arquivo.csv:
   - Tipo de contrato - Forneça um nome para a combinação da conta do razão geral e do método de amortização. Nomes significativos de tipos de contrato podem ajudar os proprietários de centros de custo a alocar suas despesas de contrato para os códigos corretos de contas do razão geral.

     Por exemplo, os tipos de contrato com nomes significativos para o proprietário do centro de custo, como Manutenção de hardware, podem ser mapeados para o mesmo código de conta do razão geral de Serviços do fornecedor.
   - Método de amortização do contrato - Especifica como seu contrato será amortizado ao longo da vida do contrato. A amortização de contratos permite que você distribua os custos ao longo da vida útil de um contrato em vez de acumular o valor total do contrato na data de início desse contrato. O Offset de início de amortização atrasa o início da amortização, altera o número de períodos e mantém a mesma data final para os contratos. Como isso atrasa a data de início, o número de períodos no cronograma de amortização muda. No entanto, o período final do cronograma não é alterado. Todos os cálculos para cada dia são baseados no calendário gregoriano padrão. Os seguintes métodos estão disponíveis:
     - Amortização manual - permite que você importe, insira e edite manualmente os valores de despesas amortizadas por período para um contrato.
     - Straight Line Even Periods - (Método padrão) Amortiza as despesas uniformemente para cada período. O período de amortização é definido pelo mês inicial e final do contrato.
     - Linha reta por duração - Amortiza as despesas uniformemente para cada período. O período de amortização é definido pelo número de meses do contrato.
     - Straight Line Prorate First and Last - Amortiza valores iguais para períodos que não sejam o primeiro e o último período. Para o primeiro e o último período, os valores são rateados com base no número de dias em cada período.
     - Linha reta usando dias do calendário - Amortiza os valores individualmente para cada período com base no número de dias do calendário em cada período.
   - Conta - Especifica o código da conta do razão geral em que o contrato será acumulado. As opções disponíveis são fornecidas pelos dados de referência do Plano de Contas.
5. Agora, Configuration > Reference Data > Contract Type e, em seguida, importe o arquivo.csv atualizado

## Exemplo de amortização de contrato

O exemplo a seguir usa esses valores iniciais:

- Valor - $ 400.00
- Data de início - 20 de agosto de 2017
- Data final - 19 de dezembro de 2017
- Duração calculada usando apenas o mês (usado pelo método dos períodos pares) - 5 meses
- Duração calculada usando mês e dia (usada pelo método Duration) - 4 meses

| Método de amortização | Ago. | Setembro. | Out. | Nov. | Dez. | Total |
| --- | --- | --- | --- | --- | --- | --- |
| Linha reta Períodos pares | $400 / 5 = $80 | $400 / 5 = $80 | $400 / 5 = $80 | $400 / 5 = $80 | $400 / 5 = $80 | US$ 400 |
| Linha reta por duração | $400 / 4 = $100 | $400 / 4 = $100 | $400 / 4 = $100 | $400 / 4 = $100 |  | US$ 400 |
| Linha reta ratear primeiro e último | 12 / 122 $400 = $ 39.34 | $ 298.36 / 3 = $ 99.45 | $ 298.36 / 3 = $ 99.45 | $ 298.36 / 3 = $ 99.45 | 19 / 122 $400 = $ 62.30 | US$ 400 |
| Linha reta usando dias do calendário | 12 / 122 $400 = $ 39.34 | 30 / 122 $400 = $ 98.36 | 31 / 122 $400 = $ 101.64 | 30 / 122 $400 = $ 98.36 | 19 / 122 $400 = $ 62.30 | US$ 400 |

Nota:

- As quantias são calculadas com valores exatos. Os valores são arredondados para a unidade monetária inteira mais próxima (por exemplo, USD).
- Adicione atributos personalizados para capturar informações suplementares sobre contratos para aprimorar seus recursos de análise e relatórios (consulte [Adicionar atributos personalizados às dimensões do contrato](manage_schema.html "Os esquemas definem a estrutura dos dados no Apptio Planning. Eles especificam as tabelas, os campos e os relacionamentos que determinam como as informações são armazenadas, vinculadas e exibidas nas guias Despesas, como Trabalho, Contratos, Ativos e Finanças.")).
- O método de amortização suportado para calendários personalizados é Linha reta período par, Linha reta usando dias do calendário, Amortização manual e Linha reta por duração do calendário fiscal personalizado.

## Gerenciar dados de referência de taxas de IVA

Depois que o proprietário ou administrador do processo orçamentário ativar os recursos de planejamento de contrato e IVA, o aplicativo Apptio Planning poderá calcular um imposto sobre valor agregado (IVA), também conhecido como imposto sobre mercadorias e serviços, para contratos e gerenciar a taxa de IVA. Consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning."). A taxa de IVA (uma dimensão incorporada) especifica a porcentagem de imposto aplicada a cada local. O IVA é baseado no valor de Localização do item de linha do contrato nos dados de referência. Portanto, antes de importar os dados de referência de taxas de IVA, é necessário atualizar os dados de referência de localização para incluir todas as localizações para as quais você planeja inserir uma taxa de IVA. Consulte [Dimensões de dados de referência](manage-reference-data.html).
