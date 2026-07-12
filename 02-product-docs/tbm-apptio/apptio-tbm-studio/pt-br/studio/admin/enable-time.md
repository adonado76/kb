---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Ativar o tempo para um projeto"
breadcrumb: []
source_path: "studio/admin/enable-time.html"
images:
  - "resources/images/studio_images/studio_admin_enable_time_sui.png"
  - "resources/images/studio_images/studioimages/studio/stu040_sui.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Ativar o tempo para um projeto

**Aplica-se a** : TBM Studio 12.0 e posterior. Um dos conceitos mais importantes do aplicativo são os projetos que permitem o tempo. Em um projeto ativado por tempo, as datas de início e término são definidas para os dados e o ano fiscal é definido. Em um projeto com tempo habilitado, você pode:

- Inserir dados regularmente
- Alocá-lo em um período de tempo específico
- Veja as tendências ao longo da duração do projeto
- Visualizar os dados do relatório para o mês ou período atual, ou para períodos de um trimestre, semestre ou ano inteiro
- O aplicativo suporta calendários gregorianos e de período. No entanto, o mesmo tipo de calendário deve ser usado em todos os projetos.

Não há regras definidas sobre quando você deve reservar tempo para um projeto. No entanto, permitir o tempo em um projeto cria um ambiente mais complexo. Por esse motivo, você deve identificar as tabelas principais, criar o modelo básico e definir as principais alocações antes de ativar o tempo. Você pode ativar o tempo apenas uma vez para um projeto, e a ação é irreversível. Depois de ativar o tempo em um projeto, não é possível desativá-lo.

O tempo de habilitação de um projeto afeta algumas, mas não todas, as áreas do aplicativo. A tabela abaixo mostra as áreas afetadas e não afetadas.

| Áreas afetadas | Áreas não afetadas |
| --- | --- |
| Conjuntos de dados  - Modelos - Notas - Dados exibidos em relatórios | - Métricas - Definições de relatórios |

## Para permitir tempo para um projeto

Observação: para ativar o tempo, você deve ser atribuído a uma função que inclua a permissão **Configure Time Settings**.

1. Na guia **Projeto**, selecione **Configurações de tempo**. A janela **Configurar definições de tempo do projeto** é exibida. As opções de campo na janela dependem do tipo de calendário que você selecionar. Para obter uma descrição dos campos, consulte [Configurar as definições de tempo do projeto](configure-project-time.htm "(Abre em uma nova guia ou janela)").

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu040_sui.png)
2. Selecione os valores desejados e selecione **Configure Time (Configurar hora** ). A data é exibida no cabeçalho.

## Novos projetos não são ativados por tempo

Quando você cria um novo projeto pela primeira vez, ele não é ativado por tempo. Você pode alterar seus conjuntos de dados, transformações e modelos, e cada alteração substitui as informações atuais do projeto. Isso é representado pelo lado Não ativado por tempo desse diagrama:

![](../../resources/images/studio_images/studioimages/visio%20diagrams/time-enabling_597x336.png)

Quando você ativa o tempo em um projeto, todas as alterações feitas na estrutura das tabelas de dados criam um novo estado para os dados no projeto. No aplicativo, os estados são conhecidos como Versões. O novo estado se aplica do período atualmente selecionado em diante até que outro estado para os dados seja encontrado. No diagrama acima, isso é representado pelo lado Time-Enabled.

## Determinar se o tempo foi ativado

Você pode saber se o tempo foi ativado em um projeto observando o cabeçalho Global. Antes que o tempo tenha sido ativado, se você tiver privilégios de ativação de tempo, o cabeçalho Global exibirá Configure Dates (Configurar datas). Se você não tiver privilégios de ativação de tempo, o cabeçalho Global não exibirá Configure Dates (Configurar datas).

Quando o tempo tiver sido ativado em um projeto, o cabeçalho Global exibirá o período atualmente selecionado, conforme mostrado na imagem a seguir:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_admin_enable_time_sui.png)

## Práticas recomendadas para projetos com tempo limitado

Trabalhar com projetos habilitados por tempo pode, às vezes, ter resultados inesperados. Observe o seguinte:

- Se você fizer uma alteração em um modelo ou em uma tabela, certifique-se de que está no mês desejado ou period.For exemplo, se quiser fazer uma alteração que entre em vigor a partir do primeiro mês/período do seu projeto, certifique-se de selecionar esse mês/período no seletor de datas antes de fazer a alteração. Se você quiser fazer uma alteração que entre em vigor a partir do mês/período atual, certifique-se de que o mês/período atual esteja selecionado.
- O aplicativo é compatível com os seguintes tipos de calendário para projetos personalizados e projetos de aplicativos. Para aplicativos que não sejam personalizados e Costing Standard, somente o calendário gregoriano é compatível.
  - Gregoriano
  - 445, 454 e 544
  - 13 período

Observação: O mesmo tipo de calendário deve ser usado em todos os projetos.

## Visualizar dados em diferentes períodos de tempo

Se o tempo estiver ativado para um projeto, você poderá visualizar tabelas e modelos para diferentes períodos e relatórios para meses e outros períodos de tempo. Por exemplo, se você carregou dados de janeiro de 2016 a dezembro de 2016, poderá selecionar qualquer período e examinar as métricas do seu modelo com os dados do período selecionado. Você também pode selecionar Fiscal Q1 de 2016 e ver seus relatórios com os dados do trimestre.

Para visualizar dados em diferentes períodos de tempo:

1. No cabeçalho Global, clique no período de tempo exibido no momento. O seletor de datas é exibido. Os períodos de tempo no seletor de datas refletem o ano fiscal definido para o projeto.
2. Use o seletor de datas para selecionar um mês ou período, trimestre, semestre ou ano inteiro.
3. Clique no mês ou período que deseja visualizar.
4. Você pode selecionar os botões Q1 - Q4 no lado esquerdo da caixa de diálogo, os botões H1 e H2 no lado direito da caixa de diálogo e o botão FY (Fiscal Year, ano fiscal) na parte inferior da caixa de diálogo.
   - Para retroceder ou avançar nos anos, clique nas setas à esquerda e à direita dos anos na parte superior da caixa de diálogo e, em seguida, selecione uma das datas exibidas. Se uma seta estiver esmaecida e não puder ser clicada, você atingiu a data de início ou de término do projeto.
   - Se o seletor de datas exibir períodos em vez de meses, você poderá apontar para um dos períodos e será exibida uma dica de ferramenta que mostra as datas de início e término do período.
5. O período de tempo que você selecionou é exibido na parte superior da janela do navegador. Os dados exibidos em um relatório são referentes ao período de tempo selecionado.
