---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Gráficos de tendências do legado"
breadcrumb: []
source_path: "studio/reports/legacy-trend-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de tendências do legado

**Aplica-se a** : TBM Studio 12.0 e posterior

Para gráficos antigos, há uma guia **Trend** na caixa de diálogo **Properties (Propriedades** ). As propriedades controlam a aparência do gráfico e os dados exibidos. Incluído nos controles está a capacidade de projetar valores em um número específico de períodos com base em dados históricos. Você pode adicionar projeções futuras a gráficos de tendências, nos quais as projeções se baseiam em um número específico de meses anteriores.

A guia **Trend** está disponível apenas para gráficos antigos criados com versões mais antigas do aplicativo. Se você converter um gráfico de tendências em um gráfico legado, a guia não estará disponível.

As propriedades padrão do gráfico também estão disponíveis nas outras guias da caixa de diálogo **Properties (Propriedades** ). Para obter informações sobre as propriedades padrão, consulte [Definir propriedades do gráfico](set-chart-properties.htm "(Abre em uma nova guia ou janela)").

**Descrições de campo** :

Os campos **Trend** são descritos abaixo:

- Trend Value (Valor de tendência) - A coluna usada para fornecer os valores traçados.
- Chave de tendência - A coluna do identificador da unidade. Esse valor deve ser o mesmo que o do campo **X Axis Tag** na guia **Chart (Gráfico** ).
- Trend Past Range (Intervalo de tendência passada) - Quanto tempo atrás do período atual você deseja que o gráfico vá? O número inserido será aplicado ao período selecionado no momento: meses, trimestres, anos. Por exemplo, se o período selecionado for meses e você inserir 6 no campo, o gráfico mostrará o mês atual mais os cinco meses anteriores.
- Trend Future Range (Intervalo futuro da tendência) - Até que ponto você deseja que o gráfico avance em relação ao período atual? O número inserido será aplicado ao período selecionado no momento: meses, trimestres, anos. Por exemplo, se o período selecionado for meses e você inserir 6 no campo, o gráfico mostrará o mês atual mais os próximos seis meses.
- Ordem inversa da tendência - Por padrão, o tempo no eixo X vai do passado para o futuro, da esquerda para a direita. Se você selecionar essa opção, o tempo será executado do futuro para o passado. Por exemplo, se o gráfico exibir dados de janeiro de 2010 a dezembro de 2010, a ordem inversa exibiria os dados de dezembro de 2010 a janeiro de 2010.
- Coluna Trend Add Total - Esse campo se aplica somente a tabelas de tendências, não a gráficos de tendências. Deixe esse campo em branco.
- Coluna Trend Add Average - Esse campo se aplica somente a tabelas de tendências, não a gráficos de tendências. Deixe esse campo em branco.
- Intervalo futuro da projeção - O número de períodos de tempo a serem projetados no futuro com base no período de tempo selecionado no momento. Por exemplo, se o período de tempo atual for de meses, a projeção será de seis meses no futuro.
- Intervalo passado a ser usado para projeções - O número de períodos de tempo retrocedendo no tempo a ser usado para fazer os cálculos de projeção. Esse valor deve ser igual ou superior a dois. Se você inserir 0 ou 1, o aplicativo usará o valor do campo **Trend Past Range**.
- Unidades a serem projetadas - As unidades do gráfico a serem projetadas. Por exemplo, se as unidades exibidas no gráfico forem divisões chamadas Eastern, Central e Western, você poderá optar por projetar somente a divisão Eastern.
- Projection Algorithm (Algoritmo de projeção) - Selecione o algoritmo de projeção que deseja usar. Os algoritmos são os algoritmos padrão usados na análise estatística. O algoritmo padrão é **Regressão**.
- Projeção e tendência do grupo - Esse campo se aplica somente a tabelas de tendências. Deixe esse campo em branco.
- Strip Leading and Trailing Zero Values (Remover valores zero à esquerda e à direita) - Remove qualquer valor zero no início ou no final do gráfico. Isso evita que a linha de tendência desça até o eixo X no início e no final do gráfico.

## Adicionar projeções diretamente de um gráfico de tendências

Se você tiver criado um gráfico de tendências herdado e quiser projetar valores no futuro com base nos dados existentes no gráfico, poderá adicionar uma projeção. Para adicionar uma projeção, clique com o botão direito do mouse no gráfico e selecione **Project Trend** no menu pop-up. O aplicativo adicionará uma projeção de regressão para um período de tempo equivalente ao período de tempo que está sendo analisado.

Para remover a projeção do gráfico, clique com o botão direito do mouse no gráfico e selecione **Remove Projection (Remover projeção** ) no menu pop-up.

Observação: As projeções não estão disponíveis para gráficos Ad Hoc Query.
