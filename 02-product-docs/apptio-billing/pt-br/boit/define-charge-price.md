---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Definir a relação Preço de cobrança x Quantidade"
breadcrumb: []
source_path: "boit/define-charge-price.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Definir a relação Preço de cobrança x Quantidade

No modelo Charge, você deve primeiro definir os drivers para o objeto Consumption Feed e, em seguida, definir as alocações para a tabela modelada Business Services e a tabela modelada Business Unit Allocation.

**Definir os drivers para o objeto Feed de consumo**

Há três tipos básicos de drivers: cobranças baseadas em custo, cobranças baseadas em orçamento e cobranças baseadas em preço.

**Tarifas baseadas em custos**

As cobranças baseadas em custos repassam o custo para o usuário corporativo. Os custos por serviço são determinados no aplicativo Transparência de custos. As cobranças baseadas em custos podem ter informações adicionais fornecidas por meio do Feed de consumo.

1. Se você ainda não tiver adicionado dados ao Feed de consumo, vá para [Adicionar dados de consumo para cálculos de Preço x Quantidade](add-consumption-data.html "(Abre em uma nova guia ou janela)"). Se você não pretende fornecer quantidades, anexe uma lista de suas IDs de serviço usando as mesmas etapas.
2. Siga as etapas em [Definir as alocações do modelo de custo](define-cost-model1.html "(Abre em uma nova guia ou janela)") para alocar o custo ao feed de consumo.
3. Na tabela Biblioteca de serviços, defina a **Metodologia de preços** como **Custo** para todos os serviços que usarão Custo para determinar a cobrança.
4. No **Project Explorer**, clique na etapa **Model** na tabela Business Services.
5. Certifique-se de que a métrica **Charge** esteja selecionada.
6. Valide se o driver fornecido agora mostra valores.

**Taxas baseadas em orçamento**

As cobranças baseadas em orçamento passam para o usuário comercial uma cobrança orçada determinada por serviço. As cobranças baseadas em orçamento podem ter informações adicionais fornecidas por meio do Feed de consumo.

1. Siga as etapas em [Adicionar os dados de consumo](add-consumption-data.html "(Abre em uma nova guia ou janela)").
2. Na tabela Biblioteca de serviços, defina a **Metodologia de preços** como **Orçamento** para todos os serviços que usarão Custo para determinar a cobrança.
3. No **Project Explorer**, clique na etapa **Model** na tabela Business Services.
4. Certifique-se de que a métrica **Charge** esteja selecionada.
5. Valide se o driver fornecido agora mostra valores.

**Tarifas baseadas em preço**

As cobranças baseadas em preço multiplicam um preço determinado pelo serviço e as unidades do serviço que foram consumidas. Os serviços baseados em preço devem ter feeds de consumo com as unidades fornecidas por meio do Feed de consumo.

1. Siga as etapas em [Adicionar os dados de consumo](add-consumption-data.html "(Abre em uma nova guia ou janela)").
2. Siga as etapas em [Definir as alocações do modelo de unidades faturáveis](define-billable-model.html "(Abre em uma nova guia ou janela)").
3. Na tabela Service Library (Biblioteca de serviços), defina a **Metodologia de precificação** como **Preço** para todos os serviços que usarão (Preço x Quantidade) para determinar a cobrança.
4. No **Project Explorer**, clique na etapa **Modelo** na tabela Alimentação de consumo.
5. Certifique-se de que a métrica **Charge** esteja selecionada.
6. Valide se o driver fornecido agora mostra valores.

**Definir as alocações**

No modelo Charge, você deve definir a alocação do objeto do modelo Consumption Feed para o objeto do modelo Business Services e do objeto do modelo Business Services para o objeto do modelo Business Unit Allocation. Use as configurações mostradas nas imagens a seguir.

Alocação de consumo para serviços comerciais

Serviços de negócios para alocação de alocação de unidade de negócios

Se você não tiver nenhum consumo ou serviço totalmente atribuível a uma unidade de negócios, use uma alocação semelhante à seguinte:

Caso contrário, use essa alocação:
