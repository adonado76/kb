---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Várias moedas"
breadcrumb: []
source_path: "it-planning/planning/support-multiple-currencies.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Várias moedas

Apptio Planning os aplicativos suportam as necessidades de planejamento, geração de relatórios e análise das organizações que trabalham com várias moedas. Os recursos que suportam várias moedas incluem o seguinte:

- Uma moeda única e comum usada para todas as conversões de moeda. A moeda comum geralmente é a moeda de registro da organização. Todas as taxas de conversão de moeda são definidas em relação a essa moeda e, a menos que outra seja especificada, essa é a moeda de exibição padrão por centro de custo. Para obter mais informações, consulte [Definir a moeda comum](set-common-currency.html "Uma moeda única e comum é usada para todas as conversões de moeda. A moeda comum geralmente é a moeda de registro da organização. Todas as taxas de conversão de moeda são definidas em relação a essa moeda e, a menos que outra seja especificada, essa é a moeda de exibição padrão por centro de custo.").
- Suporte a todas as moedas que usam um código ISO. Para obter mais informações sobre a lista de códigos reconhecidos internacionalmente, consulte [https://www.iso.org/iso-4217-currency-codes.html](https://www.iso.org/iso-4217-currency-codes.html "(Abre em uma nova guia ou janela)"). O código ISO especifica a abreviação de três letras da moeda (por exemplo, USD para dólar americano) e a exibição correta da moeda (por exemplo, o símbolo $ e a vírgula e o posicionamento decimal). Um administrador pode optar por exibir códigos ISO de moeda em vez de símbolos de moeda e pode ativar recursos para oferecer suporte a várias moedas.
- Atribuição opcional de uma moeda local para centros de custo individuais ou em grupo. Os códigos de moeda local dos centros de custo são gerenciados como dados de referência do centro de custo. Se nenhum código de moeda local for especificado, o padrão será o código da empresa.
- Tabelas separadas de taxas de conversão de moeda para dados financeiros planejados (orçamento e previsão) e reais. As tabelas de taxas de conversão definem as taxas de conversão de moeda (FX) em relação à moeda comum e são gerenciadas como dados de referência. As taxas de conversão com tempo definido para os dados reais podem ajudar a distinguir a variação real do plano da variação devida às flutuações da moeda.
- Suporte para taxas de conversão com caixa de tempo por moeda em tabelas de taxas. Especifique as taxas de conversão em qualquer escala, de diária a anual. As taxas de conversão por moeda permitem a entrada de valores orçamentários em uma moeda local para o centro de custo e, em seguida, a conversão para a moeda comum (ou qualquer outra moeda suportada) quando compactada.

## Ativar recursos de várias moedas

Os usuários atribuídos às funções Administrador ou Proprietário do processo orçamentário podem ativar os recursos de várias moedas. Escolha mostrar ou ocultar os recursos de suporte a várias moedas. O suporte a várias moedas é definido na seção Perfil da empresa e se aplica a todos os usuários do locatário selecionado no momento. Para obter mais informações, consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning.").

1. No menu Apptio Planning , clique no botão Settings (Configurações ) e, em seguida, clique em Company Profile (Perfil da empresa ).
2. Na seção Settings (Configurações ), selecione Enable Multi Currency (Ativar várias moedas ).

   Observação: Se você quiser mudar a exibição dos valores monetários de um símbolo de moeda para um código de moeda ISO de três letras, selecione Show ISO Currency Codes (Mostrar códigos de moeda ISO) em vez de Symbols (Símbolos ). Por exemplo, um valor de moeda CA$30.68M, pode ser exibido como 30.68M CAD. Isso esclarece as organizações e os usuários que trabalham com uma variedade de moedas.
3. Selecione Salvar e sair.

Atenção: Depois que os recursos de várias moedas forem ativados, conclua as seguintes tarefas:

- [Definir a moeda comumDefinir](set-common-currency.html "Uma moeda única e comum é usada para todas as conversões de moeda. A moeda comum geralmente é a moeda de registro da organização. Todas as taxas de conversão de moeda são definidas em relação a essa moeda e, a menos que outra seja especificada, essa é a moeda de exibição padrão por centro de custo.") a moeda comum para sua organização
- [Requisito de dados de referênciaImportar](import-publish-currency.html "As tarefas abaixo só podem ser realizadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.") e publicar taxas de câmbio
- [Insira ou exiba valores de itens de linha em moedas diferentes](enter-display-line.html "Quando o suporte a várias moedas está ativado, uma lista de moedas no canto superior direito da página permite exibir valores financeiros de previsão ou plano de orçamento de itens de linha em um valor de moeda diferente da moeda da empresa.") Insira ou exiba valores de itens de linha em moedas diferentes
