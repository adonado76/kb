---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Configurar várias moedas"
breadcrumb: []
source_path: "studio/admin/configure-multi-currency.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar várias moedas

Aplica-se a: TBM Studio v12.1 e posterior

Se a sua empresa tiver escritórios em mais de um país, você deverá configurar a multimoeda. No mínimo, você deve inserir as taxas de câmbio anuais. Se precisar de números mais atualizados, você pode usar taxas de câmbio trimestrais ou mensais.

- Quando você configura várias moedas para um projeto, os seguintes recursos são ativados:
- O administrador seleciona uma moeda base e uma localidade para um projeto (use a guia **Projeto**, grupo **Configuração de projeto**, comando **Configurações de projeto** ).
- O administrador pode inserir taxas de câmbio para qualquer número de outras moedas (guia Dados > tabela Câmbio de moedas).
- Todos os valores de moeda nos relatórios são exibidos com base nas taxas de câmbio.
- Ao definir uma métrica, você pode selecionar um tipo de taxa padrão em várias moedas. Por exemplo: se houver dois tipos de taxa, Planejada e Real, você poderá escolher Planejada ou Real.

  Observação: para produtos em várias moedas do Apptio Cloud, os valores na coluna Type (Tipo) nos dados que você carrega na tabela Currency Exchange (Câmbio de moedas) devem ser rotulados como Real em seus dados brutos para que o recurso de várias moedas funcione.
- Os usuários podem selecionar uma moeda e localidade para seu perfil (clique no nome do usuário no cabeçalho).
- Os usuários podem selecionar uma moeda para um relatório específico e todos os valores nos componentes Ad Hoc do relatório serão exibidos na moeda (clique na lista de várias moedas na barra de ferramentas do relatório).![](../../resources/images/studio_images/studioimages/studio_report%20toolbar_multi-currency.png)
- No modo TBM Studio , os valores são sempre exibidos na moeda base.
- As moedas são convertidas a partir da moeda base.
- Todos os relatórios com reconhecimento de tempo usam a taxa de câmbio do mês apropriado ou a taxa de câmbio anual. Ao usar a taxa de câmbio mensal, as alterações nos valores podem ser vinculadas a alterações nas taxas de câmbio.
- Você pode adicionar colunas às tabelas Ad Hoc e selecionar a moeda e o tipo de taxa para a coluna. Uma tabela pode ter colunas que exibem valores em diferentes moedas.

Para obter informações adicionais relacionadas ao uso de várias moedas para os produtos do Apptio Cloud, consulte [Configurar várias moedas para o Cloud](../../cost-transparency/configuration/multicurrency.html "(Abre em uma nova guia ou janela)").

## Moedas e localidades suportadas

A moeda determina o símbolo da moeda (por exemplo, g.: €/$) e o código de três letras da moeda internacional (por exemplo, g.: EUR/USD) exibido com os valores. A localidade determina o formato dos números. Os dois são independentes um do outro. A localidade determina o posicionamento e o espaçamento do símbolo de moeda, mas não por uma interpretação literal do modelo de formato de gráfico. Portanto, $#,### é interpretado como "mostrar como moeda", com separadores de "mil", precisão zero e o símbolo de moeda posicionado (prefixo vs. sufixo, espaçamento) com base na localidade.

O aplicativo é compatível com todos os códigos de moeda listados na lista de códigos ISO 4217 da International Organization for Standardization. O aplicativo é compatível com os seguintes locais. Os códigos de moeda correspondentes e os formatos de localidade estão listados ao lado de cada localidade.

> Argentina | ARS | #.##0,##
>
> Austrália | AUD | # ##0.##
>
> Áustria | EUR | #.##0,##
>
> Bélgica (holandês) | EUR | #.##0,##
>
> Bélgica (francês) | EUR | #.##0,##
>
> Botsuana | BWP | #,##0.##
>
> Brasil | BRL | #.##0,##
>
> Canadá (francês) | CAD | #.##0,##
>
> Canadá (inglês) | CAD | #,##0.##
>
> China (continente) | CNY | #,##0.##
>
> Colômbia | COP | #.##0,##
>
> República Tcheca | CZK | #.##0,##
>
> Dinamarca | DKK | #.##0,##
>
> Equador | USD (anteriormente ECS) | #,##0.##
>
> Etiópia | ETB | #,##0.##
>
> Finlândia | EUR | #.##0,##
>
> França | EUR | #.##0,##
>
> Alemanha | EUR | # ##0,##
>
> Gana | GHS | #,##0.##
>
> Honduras | HNL | #,##0.##
>
> Hungria | HUF | # ##0,##
>
> Irlanda (inglês) | EUR | #.##0,##
>
> Irlanda (irlandês) | EUR | #.##0,##
>
> Itália | EUR | #.##0,##
>
> Japão | JPY | #,##0
>
> Quênia | KES | #,##0.##
>
> Luxemburgo (francês) | EUR | #.##0,##
>
> Luxemburgo (alemão) | EUR | #.##0,##
>
> Malawi | MWK | #,##0.##
>
> Maurício | MUR | #,##0
>
> México | MXN | #,##0.##
>
> Moçambique | MZN | #.##0,##
>
> Países Baixos | EUR | #.##0,##
>
> Nigéria | NGN | #,##0.##
>
> Noruega (Bokmal) | NOK | # ##0,##
>
> Noruega (Nynorsk) | NOK | # ##0,##
>
> Panamá | PAB | #,##0.##
>
> Peru | PEN | #,##0.##
>
> Polônia | PLN | # ##0,##
>
> Portugal | EUR | #.##0,##
>
> Romênia | RON | #.##0,##
>
> Eslováquia | EUR | #.##0,##
>
> África do Sul | ZAR | # ##0.##
>
> Coreia do Sul | KRW |#,##0 (adicionado em R11.8.1.5 )
>
> Espanha (catalão) | EUR | #.##0,##
>
> Espanha (espanhol) | EUR | #.##0,##
>
> Suazilândia | SZL | #,##0.##
>
> Suécia | SEK | # ##0,##
>
> Suíça (francês) | CHF | #'##0.##
>
> Suíça (alemão) | CHF | #'##0.##
>
> Suíça (italiano) | CHF | #'##0.##
>
> Tanzânia | TZS | #,##0.##
>
> Uganda | UGX | #,##0.##
>
> Emirados Árabes Unidos | AED | #,##0.##
>
> Reino Unido | GBP | #.##0,##
>
> Estados Unidos | USD | #,##0.##
>
> Vietnã | VND | #,##0

## Restrições

A multimoeda tem as seguintes restrições:

- Nos relatórios, somente os valores baseados em métricas modeladas dos tipos Costing e Pricing podem ser exibidos na moeda escolhida pelos usuários. Todos os outros valores serão exibidos na moeda base ou na moeda para a qual foram convertidos.
- A multimoeda se aplica somente a tabelas e gráficos Ad Hoc. Não se aplica a tabelas e gráficos antigos.
- As tabelas editáveis são exibidas na moeda atribuída ao conjunto de dados e não podem ser alteradas.
- Ele não se aplica ao aplicativo legado de orçamento e previsão.
- Os gráficos em cascata são sempre exibidos na moeda base definida para o projeto.
- No modo TBM Studio , a moeda da sessão é trocada pela moeda base.

## Configurar várias moedas

Principais etapas para configurar várias moedas:

1. Insira as taxas de câmbio na tabela **Câmbio de moeda** na categoria **Outros**. Se a tabela não estiver na categoria **Other (Outro** ), defina o filtro como **Hidden (Oculto** ) para exibir o nome da tabela.![](../../resources/images/studio_images/studioimages/studio_project%20explorer_currency%20exchange.png)
2. Atribua tipos de taxas padrão a cada métrica de custo e precificação.
3. Selecione uma moeda (e localidade) para o projeto.

   Observação: A moeda determina o símbolo da moeda (por exemplo, g.: €/$) e o código de três letras da moeda internacional (por exemplo, g.: EUR/USD) exibido com os valores. A localidade determina o formato dos números. Os dois são independentes um do outro.

## Inserir taxas de câmbio

Insira as taxas de câmbio na tabela Câmbio de moeda. A moeda base é sempre definida como 1. O **código da moeda** deve ser um dos códigos de moeda internacionais padrão de três letras. A taxa deve ser um multiplicador de conversão da taxa da moeda base. O tipo é uma breve descrição da taxa de câmbio. Duas descrições comuns são Plan (Plano) para valores anuais e Actuals (Real) para valores mensais. Um exemplo de tabela de câmbio é mostrado na imagem a seguir:

![](../../resources/images/studio_images/studioimages/studio_currency%20exchange_table.png)

Você deve inserir os mesmos tipos de taxa para cada moeda. Por exemplo, se você definir tipos de taxas planejadas e reais para a moeda EUR, também deverá definir tipos de taxas planejadas e reais para todas as outras moedas.

Observação: A moeda base não tem um tipo e pode ser exibida em qualquer lugar da tabela. Não é necessário que seja a primeira entrada da tabela.

Se você inserir um código de moeda que não corresponda a uma localidade, o código de moeda de três letras será exibido em vez do símbolo de moeda. Por exemplo: CNL59,000.

## Atribuir um tipo de taxa padrão a cada métrica monetária

Para que os relatórios sejam exibidos corretamente, você deve definir um tipo de taxa para cada métrica modelada de custo e preço. Os tipos de taxas comuns são: planejada, real, mensal e semanal. Para atribuir um tipo de taxa padrão:

1. No Project Explorer, clique na métrica.
2. No campo **Default Multi-Currency Rate Type (Tipo de taxa padrão para várias moedas** ), selecione um tipo de taxa.![](../../resources/images/studio_images/studioimages/studio_cost%20ytd_formula%20metric.png)
3. Verifique se o campo **Table Format** (consulte acima) tem uma entrada =Currency.

## Selecione uma moeda (e localidade) para o projeto

1. Abra a guia **Projeto** e clique em **Configurações do projeto**.
2. Selecione uma moeda no campo **Moeda base**.
   - Isso controla o símbolo da moeda (por exemplo, g.: €/$) e o código de três letras da moeda internacional (por exemplo, g.: EUR/USD) exibidos com valores.

     Observação: Quando os usuários estiverem trabalhando em TBM Studio, todos os valores serão exibidos na moeda base, independentemente das preferências de moeda que o usuário tiver selecionado.
   - Se você selecionar Moeda única, a opção de várias moedas não estará ativa para o projeto.
3. Selecione uma localidade no campo **Localidade**. A localidade determina o formato dos números. A localidade é independente da moeda. Exemplo de localidades:
   - Estados Unidos: 12, 345.67
   - França: 12 345,67
   - Alemanha: 12.345,67

## Converter dados em taxa básica

Se estiver importando dados em várias moedas que deseja mesclar em um único conjunto de dados, primeiro converta os dados para a moeda base do projeto. Por exemplo, você pode estar importando valores de vários livros contábeis gerais.

1. Importar o conjunto de dados.
2. Adicione uma coluna ao conjunto de dados de transformação usando o parâmetro [ConvertCurrencyToBase](../formulas-and-functions/functions/convertcurrencytobase.htm "(Abre em uma nova guia ou janela)") function.This a coluna conterá os valores da moeda base.
3. Anexar o conjunto de dados ao conjunto de dados mesclado.

   Observação: Há também uma função.
