---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Dados do grupo"
breadcrumb: []
source_path: "studio/data_studio/group-data.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu505.png"
  - "resources/images/studio_images/studioimages/studio/stu506.png"
  - "resources/images/studio_images/studioimages/studio_steps_group.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Dados do grupo

**Aplica-se a** : TBM Studio 12.0 e posterior

Se uma tabela tiver várias linhas com os mesmos valores em uma coluna, você poderá agrupar a tabela por essa coluna. Os dados são agregados com base nas entradas da coluna. Isso pode ser útil ao criar gráficos e tabelas em relatórios.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_steps_group.png)

Para agrupar dados:

1. Adicione uma etapa **de Grupo** à transformação de dados.
2. Selecione uma ou mais colunas para agrupar.

Assista a este vídeo de demonstração do Apptio Education Services: [Solução de problemas da mensagem "Various over Time"](https://community.apptio.com/videos/1902 "(Abre em uma nova guia ou janela)"). Ou navegue por [todos os vídeos do site Apptio](https://community.apptio.com/docs/DOC-7714 "(Abre em uma nova guia ou janela)").

## Exemplo

Suponha que você tenha a tabela mostrada abaixo:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu505.png)

Você agrupa a tabela pela coluna **Vendor** para obter a tabela mostrada abaixo:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu506.png)

A tabela agora está organizada por **fornecedor**, e um novo campo**.Count** foi adicionado. O campo**.Count** mostra quantas entradas existem em cada linha agregada. Como os fornecedores de AGI/LENI e LENI têm valores diferentes na coluna **Equipamento**, a coluna exibe os três pontos.

Se houver campos vazios na coluna pela qual você fez o agrupamento, será exibida uma linha na parte inferior da tabela com os seguintes valores:

|  |  |
| --- | --- |
| Nesta coluna: | Esse valor é exibido: |
| A coluna Agrupar por | Em Branco |
| .Contagem | Número de linhas em branco |
| Colunas numéricas | Soma de todas as linhas com espaços em branco na coluna Group By |
