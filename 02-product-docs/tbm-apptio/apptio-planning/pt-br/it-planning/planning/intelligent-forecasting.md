---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Visão geral da previsão inteligente"
breadcrumb:
  - "Planning"
  - "Previsão inteligente"
source_path: "it-planning/planning/intelligent-forecasting.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Visão geral da previsão inteligente

A Previsão Inteligente introduz técnicas avançadas de previsão de séries temporais no Planejamento do Apptio, capacitando as equipes a produzir previsões mais precisas e consistentes com menos esforço manual. O recurso analisa padrões históricos de gastos e aplica automaticamente o modelo mais adequado para cada item.

**Principais recursos:**

- **Seleção automatizada de modelos com base em tendências históricas**

  A Previsão Inteligente analisa o padrão da série temporal de cada item e seleciona automaticamente o modelo de previsão mais adequado.
- **Detecção de valores atípicos para melhorar a precisão das previsões**

  Anomalias históricas são detectadas, permitindo que os usuários as ajustem, de modo que o modelo seja treinado com dados mais limpos e estáveis, levando a resultados de previsão mais confiáveis.
- **Previsões mais precisas e consistentes**

  A detecção automatizada de padrões (tendência, nível, sazonalidade), o ajuste de parâmetros e a suavização otimizada produzem maior precisão e reduzem a variação das previsões entre os planejadores.
- **Maior transparência e controle, com a capacidade de revisar e refinar os resultados**

  Os planejadores podem inspecionar as configurações do modelo, os parâmetros de suavização e as medidas de precisão padrão. As previsões são totalmente editáveis: os usuários podem aceitar, ajustar ou substituir valores conforme necessário.

## Habilite a previsão inteligente

Observação: as funções de administrador ou responsável pelo processo orçamentário são necessárias para realizar essas tarefas.

**Etapas para habilitar a previsão inteligente**

1. Navegue até **Configurações** **(ícone de engrenagem)** → **Perfil da empresa**.
2. Certifique-se de que **a Experiência da página Novas despesas (Beta)** esteja ativada primeiro — a Previsão inteligente não pode ser usada sem ela. Para ativar o recurso, siga estas etapas:
   - **Configuração geral** → **Acesso e permissões** → Selecione **Ativar nova experiência da página Despesas (Beta)**
3. Selecione **Previsão** → **Ativar previsão inteligente**
4. Clique no botão **Salvar e Sair**

## Aplique previsões inteligentes

Observação: é necessária a permissão “ *ITPPredictiveForecastingFeatureFullAccess* ” para usar o recurso “Intelligent Forecasting”. As funções de Administrador, Responsável pelo Processo Orçamentário e Responsável pelo Centro de Custos já possuem essa permissão.

Os usuários podem criar ou modificar previsões definindo os períodos de previsão e os dados históricos na caixa de diálogo **Previsão**.

1. Navegue até a página **Despesas** e ative a opção **Nova visualização**.
2. Selecione a guia Despesas (Resumo, Outros, Ativos, Contratos, Mão de obra ou Atividade de mão de obra).
3. Vá para a guia **Outros**.
4. Selecione um ou mais itens marcando a caixa ao lado de cada item.
5. Em seguida, selecione **Previsão** no menu do botão direito do mouse ou clicando no botão **Previsão**.
6. Na caixa de diálogo **Previsão**, selecione o **Intervalo de datas histórico**, escolhendo o **Período inicial** e **o Período final**. Esses dados serão usados para gerar a previsão.
7. *É necessário um mínimo de 3 meses de dados para executar a Previsão Inteligente.*
8. Na mesma caixa de diálogo, configure o **Período de previsão** selecionando o **Período inicial** e **o Período final**.
   - **O Período Inicial da** Previsão é automaticamente definido como o mês imediatamente após o Período Final Histórico, mas pode ser alterado.
   - **O Período de Fim da** Previsão pode ser qualquer mês entre o Período de Início da Previsão e o Período de Fim do Plano.
9. Para revisar a previsão gerada, clique em **Visualizar**.
10. Você pode alternar entre modelos de previsão para comparar resultados e detalhes estatísticos.
11. Quando estiver satisfeito com a previsão, selecione o modelo a ser aplicado e clique em **Aplicar modelo selecionado** para atualizar os itens de linha escolhidos.

## Tipos de despesas compatíveis com a previsão inteligente

**Outros e resumo**

- É possível fazer uma previsão das demais despesas na guia **“Outros”** ou na guia “**Resumo** ”.
- A aplicação de uma previsão atualiza automaticamente os valores financeiros correspondentes.

**Trabalho e atividade laboral**

- Compatível com **mão de obra** e **atividades laborais (horas)**.
- A pré-visualização da previsão exibe:
- **Número** de funcionários
- **Horário** de trabalho
- A aplicação de uma previsão atualiza automaticamente os dados financeiros relativos à mão de obra e às atividades de mão de obra.

**Contratos e ativos**

- Compatível com **contratos de amortização manual** e **ativos de depreciação manual**.
- A previsão está **desativada** para linhas de contratos e ativos não compatíveis.
- A aplicação de uma previsão gera dados financeiros atualizados tanto para contratos quanto para ativos.

**Observações importantes**

- A Previsão Inteligente **não** está disponível para:
- Linhas externas
- Dados financeiros gerados
- Despesas apresentadas
- Valores reais
- O suporte ao uso **de dados reais como dados históricos** para previsões está previsto para uma versão futura.
- O suporte à **previsão inteligente para despesas agrupadas** também está previsto para uma versão futura.

## Revisão e interpretação da previsão

Observação: é necessária a permissão “ *ITPPredictiveForecastingFeatureFullAccess* ” para usar o recurso “Intelligent Forecasting”. As funções de Administrador, Responsável pelo Processo Orçamentário e Responsável pelo Centro de Custos já possuem essa permissão.

A pré-visualização da previsão mostra como serão os resultados da previsão, com base nas informações fornecidas. Isso lhe dá a oportunidade de analisar e trabalhar com dados de previsão projetados antes de aplicá-los, ajudando-o a tomar decisões mais informadas.

1. A pré-visualização da previsão fica disponível após clicar no botão **Pré-visualizar** na caixa de diálogo **Previsão**.
2. O **Gráfico de Visualização** exibe a visualização dos dados históricos seguidos pelos dados previstos, representados por uma linha pontilhada.
3. O **Gráfico de Visualização** mostra os valores previstos, bem como um intervalo de confiança que indica os limites superior e inferior dentro de uma área sombreada.
4. A pontuação **de precisão da previsão** mostra a precisão geral da previsão, indicando o grau de correspondência entre as previsões do modelo e os dados históricos.
5. Clique na guia **Detalhes estatísticos** para revisar os detalhes da previsão.

Para saber mais sobre os modelos e os detalhes estatísticos, consulte [Modelos de previsão](forecasting-model.html "A previsão inteligente avalia automaticamente um conjunto diversificado de modelos estatísticos para identificar o mais adequado para seus dados. Esses modelos variam de métodos de suavização adaptativa a abordagens baseadas em linha de base e regressão. O objetivo é capturar diferentes comportamentos de dados — como tendências de crescimento, padrões sazonais repetitivos, volatilidade e relações lineares — para que o sistema possa gerar previsões precisas e explicáveis de forma consistente em vários cenários de negócios.")

## Identificação e ajuste de valores atípicos nas previsões

Observação: é necessária a permissão “ *ITPPredictiveForecastingFeatureFullAccess* ” para usar o recurso “Intelligent Forecasting”. As funções de Administrador, Responsável pelo Processo Orçamentário e Responsável pelo Centro de Custos já possuem essa permissão.

**Valores discrepantes**

Um outlier é qualquer ponto de dados dentro dos **últimos 20% dos seus valores históricos** que fica **fora do intervalo de confiança do modelo** para esse ponto no tempo. Esses pontos indicam momentos em que o valor real se desviou mais do que o esperado dos padrões típicos nos dados.

Durante a previsão, vários modelos são avaliados e comparados. Embora os intervalos de confiança do ajuste do modelo para pontos históricos não sejam exibidos, cada valor ajustado tem um intervalo de confiança estimado, semelhante aos intervalos mostrados para a previsão.

A maioria dos pontos históricos geralmente se alinha estreitamente com seus valores estimados pelo modelo. No entanto, quando um ponto fica visivelmente fora do intervalo de confiança esperado, ele é identificado como um outlier. Isso indica que o valor histórico foi excepcionalmente alto ou baixo em comparação com o previsto pelo modelo.

Os valores atípicos podem ocorrer devido a eventos pontuais, picos ou quedas incomuns nos gastos ou anomalias na entrada de dados. Destacá-los ajuda a entender quais valores históricos podem estar contribuindo para um comportamento inesperado do modelo ou para uma precisão reduzida da previsão.

**Ajustando valores atípicos**

1. Quando o Intelligent Forecasting identifica valores atípicos em seus dados históricos, você pode visualizá-los na Visualização da previsão e o botão Valores atípicos detectados é ativado.
2. Clique no botão **Outliers detectados** na pré-visualização. O painel **Detectados atípicos** é aberto.
3. Clique em **Ajustar valores atípicos** para atualizar a previsão e ver o impacto do ajuste.
4. Quando vários outliers são detectados, eles são ajustados sequencialmente desde o início do conjunto de dados. Isso significa que cada valor atípico ajustado é aplicado ao cálculo do ajuste para o valor atípico subsequente, resultando em uma previsão mais precisa.
5. Quando estiver satisfeito com a previsão, clique em **Aplicar modelo selecionado** para atualizar os itens de linha escolhidos.
