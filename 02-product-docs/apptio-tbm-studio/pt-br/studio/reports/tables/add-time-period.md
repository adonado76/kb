---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Adicionar um período de tempo às colunas em uma tabela"
breadcrumb: []
source_path: "studio/reports/tables/add-time-period.html"
images:
  - "resources/images/studio_images/12-month.png"
  - "resources/images/studio_images/studioimages/reports/rep059.png"
  - "resources/images/studio_images/studioimages/reports/rep181.png"
  - "resources/images/studio_images/studioimages/reports/rep285.png"
  - "resources/images/studio_images/studioimages/studio/aug371.png"
  - "resources/images/studio_images/studioimages/studio/aug480.png"
  - "resources/images/studio_images/studioimages/studio/stu616.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adicionar um período de tempo às colunas em uma tabela

**Aplica-se a** : TBM Studioo 12.0 e posterior

Se quiser adicionar períodos de tempo, como meses ou trimestres, a uma tabela, selecione a perspectiva **Tempo** e arraste um período de tempo para a área **Colunas** ou **Linhas**. Na imagem a seguir, os meses foram adicionados à tabela. O aplicativo suporta períodos, meses, trimestres e anos. Você pode usar mais de um período de tempo por tabela. A tabela da imagem a seguir foi criada usando as configurações da imagem a seguir. Você pode adicionar um período de tempo às tabelas baseadas em objetos e de transformação.

![adicionar tempo à coluna](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug371.png)

![adicionar tempo à coluna](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep059.png)

Você pode arrastar mais de um período de tempo para a área **Axis (Eixo** ) de um gráfico ou para a área **Columns (Colunas** ) de uma tabela. Por exemplo, você pode arrastar janeiro, fevereiro e março e, em seguida, arrastar o primeiro trimestre.

Você pode converter a tabela da Figura A em um gráfico de linhas de tendência selecionando o ícone **Linha** na guia **Ad Hoc**.

## Adicionar tempo a uma coluna

Você pode adicionar períodos, meses, trimestres e anos a uma coluna adicionando os campos de tempo à área **Rows (Linhas** ) da caixa de diálogo, conforme mostrado na imagem a seguir:

![adicionar tempo à coluna](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu616.png)

Observação: O upload de arquivos não é possível para períodos de tempo fechados. Ele não exibirá o início do período do projeto, mas o período real em que ele foi carregado. Se for um período fechado, ele aparecerá como "<MMM FYYYYY (fechado)".

## Controle os períodos exibidos

Em uma tabela de tendências, você pode controlar os períodos exibidos clicando com o botão direito do mouse no campo **Tempo** na área **Colunas** do painel **Configuração de componentes** e selecionando uma das seguintes opções:

| Período de tempo | Funcionalidade |
| --- | --- |
| **Este trimestre** | Exibe os períodos no trimestre selecionado no seletor de datas. |
| **Esta metade** | Exibe os períodos na metade selecionada no seletor de datas. |
| **Este ano** | Exibe os períodos no ano selecionado no seletor de datas. |
| **Intervalo** | Digite o número de períodos a serem exibidos do passado para o futuro. |

**Adicionar colunas a uma tabela de tendências**

Para adicionar uma coluna a uma tabela de tendências, como a coluna Manager mostrada na imagem a seguir, arraste o campo para a área **Rows (Linhas** ) e desative os subtotais. Para desativar os subtotais, selecione a guia **Data (Dados)**, clique no ícone **Subtotal** e, em seguida, clique no botão **Clear (Limpar** ). A coluna Manager foi adicionada usando as configurações mostradas na imagem a seguir:

![adicionar colunas à tabela](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug480.png)

**Configurações para criar a tabela** :

![criar tabela](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep285.png)

## Meses, trimestres e períodos de compensação

Se você adicionar Current Month (Mês atual), Current Quarter (Trimestre atual) ou Current Period (Período atual) à área **Columns (Colunas** ), poderá compensar a data clicando com o botão direito do mouse no campo e selecionando **Shift (Deslocar** ). A caixa de diálogo **Time Shift** é exibida, conforme mostrado na imagem a seguir. Você pode inserir um número positivo ou negativo no campo **Offset** para exibir um período futuro ou anterior. Por exemplo, se o campo for **CurrentMonth** e você inserir *3* no campo **Offset**, a tabela exibirá dados de três meses no futuro. Se o seletor de datas do relatório estivesse definido para março, a tabela mostraria dados de junho.

![offset](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep181.png)

## Agregação de tempo dos últimos doze meses

**Aplica-se a** : 12.11.8 e posterior

Um novo recurso de agregação **Trailing Twiling Months** foi adicionado à seleção de tempo para dar suporte à automação de ativos sob gerenciamento.

A agregação de datas Trailing Twiling Months está disponível na seção Time (Tempo) do Project Explore e pode ser usada na seção Columns (Colunas) da Ad Hoc Component Configuration (Configuração de componente ad hoc) de um componente de relatório.

É útil analisar um total de 12 meses consecutivos, em vez da perspectiva do "calendário fiscal", conforme explicado abaixo:

- Soma os 12 meses anteriores (por exemplo, se o período atual for agosto de 2024, ele somará os valores de agosto de 2023 a julho de 2024)
- Se for um calendário fiscal de 13 períodos, ele somará os últimos 13 meses
- Se menos de 12 (ou 13) períodos estiverem disponíveis, o valor será anualizado

![doze meses](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/12-month.png)
