---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Adicionar uma tabela a um relatório"
breadcrumb: []
source_path: "studio/reports/tables/add-table.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep281.png"
  - "resources/images/studio_images/studioimages/studio/aug391.png"
  - "resources/images/studio_images/studioimages/studio/aug448_588x346.png"
  - "resources/images/studio_images/studioimages/studio/stu617.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adicionar uma tabela a um relatório

**Aplica-se a** : TBM Studio 12.0 e posterior

Adicione uma tabela a um relatório clicando na guia Página **inicial**, clicando em **Novo** e em **Tabela**. Adicione uma tabela editável a um relatório copiando a tabela para a Área de transferência do relatório e colando-a no relatório.

1. Abra o relatório e dê uma olhada nele.
2. Na guia **Relatório**, clique em **Tabela**. O aplicativo adiciona um espaço reservado ao relatório e abre o painel **Ad Hoc Component Configuration**, conforme mostrado na imagem a seguir:

   ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu617.png)
3. Use o painel **Ad Hoc Component Configuration** para criar a tabela.
4. Para criar a tabela, abra as seções no **Project Explorer** e arraste os campos para as quatro áreas do painel **Configuração**.

## Exemplo

Descrevemos como construir a tabela mostrada abaixo.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug391.png)

A tabela é baseada em:

- Uma tabela chamada Data Centers
- Duas métricas: Custo e Custo YTD

Quando você terminar de criar a tabela, o painel **Ad Hoc Component Configuration** se parecerá com o painel mostrado abaixo:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep281.png)

Para montar a mesa:

1. Abra um relatório.
2. Na guia **Home (Página inicial** ), clique em **New (Novo** ) e, em seguida, clique em **Table (Tabela** ). Um espaço reservado de tabela é adicionado ao relatório e o painel **Ad Hoc Component Configuration (Configuração de componente ad hoc** ) é exibido.
3. No **Project Explorer**, clique na seção **Tables (Tabelas** ), clique em **Data Centers Info (Informações sobre centros de dados** ) e arraste **Data Center** para a seção **Rows (Linhas)** do painel **Configuration (Configuração** ), conforme mostrado na imagem a seguir:

   ![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug448_588x346.png)
4. No **Project Explorer**, clique na seção **Metrics**.
5. Arraste a métrica Custo para a seção **Valores** do painel **Configuração**.
6. Arraste a métrica YTD Cost para a seção **Values (Valores** ) do painel **Configuration (Configuração** ).
