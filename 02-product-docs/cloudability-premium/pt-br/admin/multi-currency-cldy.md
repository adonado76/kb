---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "admin"
title: "Serviço de várias moedas em Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Administração"
source_path: "admin/multi-currency-cldy.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Serviço de várias moedas em Cloudability

O Serviço Multimoeda oferece uma plataforma centralizada para gerenciar tabelas de câmbio para seus produtos do Apptio. O serviço simplifica a administração e elimina a necessidade de manter tabelas separadas para cada produto. É possível carregar as tabelas de câmbio a partir de uma interface comum e configurar os diferentes produtos do Apptio para que utilizem as mesmas tabelas nos cálculos cambiais.

Para obter mais informações, consulte [https://www.ibm.com/docs/en/apptio-platform/multi-currency-service/saas?topic=multi-currency-service](https://www.ibm.com/docs/en/apptio-platform/multi-currency-service/saas?topic=multi-currency-service "(Abre em uma nova guia ou janela)").

O Serviço Multimoeda permite que você utilize uma moeda comum em todo o site Cloudability, independentemente do provedor de serviços em nuvem ou da moeda em que a cobrança é feita. As organizações podem operar e se comunicar na moeda de sua preferência, sem a necessidade de converter moedas fora do Cloudability.

O Contato de Faturamento do Cloudability de uma organização pode designar uma moeda preferencial para os usuários visualizarem relatórios e painéis, além de definir as taxas de câmbio utilizadas para a conversão de moedas.

Somente usuários com a função **“ Cloudability ” (Administrador de faturamento)** ou com a permissão “ **OrgCurrencyFeatureAccess** ” atribuída à sua função podem configurar as preferências de moeda

**Como habilitar a configuração multimoeda no Cloudability**

No Cloudability, a configuração multimoeda só pode ser ativada por usuários com a função **Cloudability Administrador de Faturamento** ou com a permissão **OrgCurrencyFeatureAccess** atribuída à sua função (doravante denominado “Administrador de Faturamento”).

Primeiro, o administrador de faturamento precisa definir a moeda preferencial seguindo as etapas abaixo:

1. Acesse a página inicial do site Cloudability.
2. Selecione o ícone **Perfil** no canto superior direito da página e selecione **Gerenciar perfil**.
3. Na página do seu perfil, selecione a aba **MOEDA**.
4. No menu MOEDA, selecione a moeda de sua preferência.
5. No menu **LOCALE**, selecione a configuração regional desejada. Uma prévia da moeda definida é exibida dinamicamente.
6. Selecione as configurações **de “Salvar moeda** ”.

Essa é uma configuração única, válida apenas durante a instalação inicial.

Em seguida, o administrador de faturamento deve acessar a tela de configuração de múltiplas moedas a partir do menu “Configurações” (ícone de engrenagem) no canto superior direito do Apex Shell e selecionar “Configuração de múltiplas moedas”. Isso abrirá a página “Gerenciar câmbio”.

Ao clicar em “Carregar nova tabela de câmbio”, você encontrará, no painel à direita, uma opção para baixar uma tabela de câmbio de exemplo. Você pode criar sua tabela de câmbio utilizando este arquivo.

Você pode criar uma tabela de câmbio usando um editor de texto ou um aplicativo de planilha. Multi-Currency Service suporta os formatos de arquivo .xls, .xlsx,.csv e.tsv.

Sua tabela de câmbio deve incluir as três colunas a seguir:

- currrencyCode: Especifica o código de moeda ISO 4217 de três caracteres, por exemplo, USD, CAD, JPY e GBP. currencyCode não pode ficar em branco.
- currencyRate: Especifica a taxa de câmbio entre esta moeda e sua moeda base. A moeda base terá sempre um currencyRate: igual a 1. O currencyRate: deve ser numérico e não pode ficar em branco.
- rateType: Especifica se a taxa de câmbio é do tipo “Planejada” ou “Real”. Você pode usar as taxas planejadas para custos orçados/planejados, enquanto as taxas reais se destinam a custos reais/históricos que foram efetivamente incorridos. Embora essa coluna seja obrigatória, as células podem ficar em branco. Deixe esta célula em branco para a moeda-base.

O exemplo a seguir mostra uma tabela de câmbio de moedas.

| currencyCode | currencyRate | rateType |
| --- | --- | --- |
| EUR | 0.96 | Real |
| EUR | 0.91 | Planejar |
| CAD | 1.33 | Real |
| CAD | 1.2 | Planejar |
| GBP | 0.85 | Real |
| GBP | 0.75 | Planejar |
| USD | 1 |  |

Depois de criar a tabela, arraste e solte o arquivo na área de destino. Como alternativa, selecione “Procurar um arquivo ” e, no explorador de arquivos, selecione o arquivo.

Em “Válido a partir de ”, selecione o mês e o ano a partir dos quais suas taxas de câmbio devem entrar em vigor

Selecione “Salvar ”.

Observação: Ao clicar em “Salvar”, o arquivo enviado será verificado quanto à validade dos códigos de moeda, e serão exibidos erros caso algum dos códigos de moeda enviados seja inválido. Além disso, se você já tiver enviado uma tabela de câmbio anteriormente e se o arquivo enviado mais recentemente não contiver alguma das moedas que você havia selecionado como “Moedas exibidas” (no envio anterior), um aviso será exibido após clicar em “Salvar”.

Após a conclusão do upload, a nova tabela de câmbio é adicionada à tabela na página “Gerenciar câmbio ”. Você pode selecionar o título da tabela para visualizar os dados armazenados nela. O campo “Moeda base (global) ” é atualizado para refletir a moeda base definida na tabela de câmbio. Observe que a moeda cuja taxa de câmbio está definida como 1 é considerada a moeda-base.

A lista de “Moedas exibidas” é atualizada para incluir todas as outras moedas especificadas na tabela de câmbio. Você pode abrir a lista “Moedas exibidas” e desmarcar as caixas de seleção das moedas que não deseja mostrar aos usuários finais.

Depois que essas etapas forem concluídas, pode levar até 24 horas para que as alterações entrem em vigor.

Observação: Se você receber pagamentos em moedas diferentes de diversos provedores de nuvem, será necessário definir as taxas de câmbio para todas essas moedas na sua tabela de câmbio, para que cada moeda seja convertida para a moeda da organização usando as taxas de câmbio carregadas no MCS.

Lista de códigos de moeda compatíveis com o Cloudability

| Nome da moeda | Código de unidade monetária |
| --- | --- |
| Peso argentino | ARS |
| Dólar australiano | AUD |
| Real brasileiro | R$ |
| Dólar canadense | CAD |
| Franco suíço | CHF |
| Yuan chinês | CNY |
| Peso chileno | CLP |
| Coroa tcheca | CZK |
| Coroa dinamarquesa | DKK |
| Euro | EUR |
| Libra esterlina britânica | GBP |
| Dólar de Hong Kong | HKD |
| Rúpia indonésia | IDR |
| Shekel israelense | ILS |
| Rúpia indiana | INR |
| Iene japonês | JPY |
| Won sul-coreano | KRW |
| Peso mexicano | MXN |
| Ringgit da Malásia | MYR |
| Coroa norueguesa | NOK |
| Dólar neozelandês | NZD |
| Zloty polonês | PLN |
| Rublo russo | RUB |
| Rial saudita | SAR |
| Coroa sueca | SEK |
| Dólar de Cingapura | SGD |
| Baht tailandês | THB |
| Lira turca | TRY |
| Dólar de Taiwan | TWD |
| Dólar americano | USD |
| Dong vietnamita | VND |
| Rand sul-africano | ZAR |
