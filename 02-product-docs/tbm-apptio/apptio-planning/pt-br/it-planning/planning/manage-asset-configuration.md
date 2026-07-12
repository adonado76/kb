---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Configurar ativos"
breadcrumb: []
source_path: "it-planning/planning/manage-asset-configuration.html"
images:
  - "resources/images/icons/3-dots.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configurar ativos

As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

Assista a este vídeo do site Apptio Education Services: [Configuração de dados de referência: Dimensões do contrato e do ativo](https://community.apptio.com/videos/1994 "(Abre em uma nova guia ou janela)").

Ou veja todos os [recursos de vídeo e treinamento do site Apptio Planning](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Abre em uma nova guia ou janela)") .

As dimensões são as categorias de dados essenciais nos itens de linha do orçamento. Muitas dimensões incorporadas têm dependências de outras dimensões (consulte [Dependências de atributos e dimensões de dados de referência](manage-reference-data.html) para obter mais informações). Você pode importar dados de referência de dimensões de um arquivo.csv ou do site Costing Standard e exportar modelos de dados de referência de dimensões e dados de tabela (consulte [Gerenciar dimensões](manage-reference-data.dital "(Abre em uma nova guia ou janela)") ).

Os dados de referência da classe de ativos controlam como as compras de ativos de capital e a depreciação são contabilizadas nos orçamentos OpEx e CapEx. Por exemplo, você pode especificar que uma determinada classe de ativos sempre acumula em uma conta de compra CapEx específica e em uma conta de depreciação OpEx.

1. Ative os ativos (consulte [Editar o perfil da empresa](edit-company-profile.dita "(Abre em uma nova guia ou janela)") ).
2. No menu de navegação, selecione Configuração > Dados de referência > Classe de ativos.
3. Selecione ![](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) no canto superior direito da tabela, selecione Exportar > Exportar tudo.
4. Abra o arquivo.csv baixado e atualize os valores dos dados conforme necessário:
   - Classe de ativos - O identificador exclusivo do nome da categoria da classe de ativos
   - Conta de depreciação - OpEx conta que acumula a despesa de depreciação da classe de ativos selecionada
   - Método de depreciação - Modelo usado para prever o declínio do valor ao longo do tempo para a classe de ativos. Para obter mais informações, consulte Planejar a redução dos valores do ativo com métodos de depreciação.
   - Conta de compra - A conta CapEx que acumula a despesa de compra da classe de ativos selecionada
   - Vida útil do ativo (meses) - A vida útil de depreciação padrão da classe de ativos
   - Valor residual % - A porcentagem do preço de compra a ser calculada como valor residual para a classe de ativos
   - Taxa de saldo (%) - A taxa de saldo decrescente a ser aplicada para a depreciação anual de saldo decrescente. Para esse método de depreciação, a taxa de saldo será aplicada ao valor do ativo a cada ano. Por exemplo, um ativo com um preço de compra de US$ 100.000 que se deprecia com uma taxa de saldo de 40% depreciaria US$ 40.000 em seu primeiro ano.
5. Agora, Configuration > Reference Data > Asset Class e, em seguida, importe o arquivo.csv atualizado.

Dica: você pode adicionar atributos personalizados às dimensões do ativo para capturar informações suplementares sobre os ativos e aprimorar seus recursos de análise e relatório. Para saber mais, consulte [Adicionar e gerenciar atributos personalizados de dados de referência (dimensões e tabelas de itens de linha)](manage_schema.dita "(Abre em uma nova guia ou janela)").

## Fórmulas para calcular a amortização para cada um dos métodos de depreciação listados

**Straight Line usa a fórmula:**

- Valor da depreciação = (preço do ativo \* (1 - valor residual)) / Vida útil do ativo
- Vida útil do ativo = duração em meses ou dias

**O Double Declining usa a fórmula:**

- Valor da depreciação = 2 \* ( 1 / Vida útil do ativo) \* Valor contábil do período inicial
- Vida útil do ativo = duração em meses ou dias
- Valor contábil do período inicial = Preço do ativo - Depreciação acumulada

**O saldo decrescente usa a taxa de saldo para calcular cada período:**

- Valor da depreciação = Saldo do ativo \* Taxa de saldo / 12
- Recentemente calculado no início de cada ano: Saldo do ativo = Saldo do ativo - Saldo do ativo \* ( Taxa de saldo / 12 ) \* Número de meses depreciados no ano anterior

## Exemplo

Preço do ativo = $40K

Vida útil do ativo = 12 meses

Data de entrada em serviço = 15/1/2024

Linha reta ( P1 FY24 ) = $40K \* (1 - 0) / 12 = $3333

Declinação dupla ( P1 FY24 ) = 2 \* (1/12) \* ( $40K - $0) = $6667

Declinação dupla ( P2 FY24 ) = 2 \* (1/12) \* ( $40K - $6666) = $5556 (editado)

Observação: O declínio duplo calcula o valor contábil no início de cada período, em vez de no início do ano. Portanto, se você quiser modelar um declínio duplo padrão (duas vezes a taxa da linha reta), deverá usar o saldo decrescente com uma taxa de saldo = 200%.
