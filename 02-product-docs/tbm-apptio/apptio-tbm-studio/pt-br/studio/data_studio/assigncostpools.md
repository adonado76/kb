---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Atribuir pools de custos com aprendizado de máquina"
breadcrumb: []
source_path: "studio/data_studio/assigncostpools.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Atribuir pools de custos com aprendizado de máquina

**Aplica-se a** : TBM Studio 12.7 e posterior. TBM Studio 12.7 e, posteriormente, pode usar o aprendizado de máquina para acelerar a configuração do Costing Standard . Anteriormente, o mapeamento de contas para pools de custos exigia a criação manual de arquivos de mapeamento com atribuição um a um para alcançar os pools de custos padrão da taxonomia. Agora, o aprendizado de máquina mapeia a maioria das contas para você em milissegundos.

Assista a este vídeo de demonstração do Apptio Education Services: [Machine Learning em 12.7](https://community.apptio.com/videos/2375 "(Abre em uma nova guia ou janela)"). Ou navegue por [todos os vídeos do site Apptio](https://community.apptio.com/docs/DOC-7714 "(Abre em uma nova guia ou janela)").

Apptio coleta informações e desenvolve modelos de previsão. À medida que mais dados são classificados, esses modelos aprendem com o tempo.

Aqui está uma visão geral de como funciona o aprendizado de máquina em Apptio.

1. As informações existentes que o Apptio possui são classificadas de acordo com o resultado desejado, como o pool de custos, e são colocadas no serviço de treinamento (hospedado em AWS ).
2. Apptio identifica os algoritmos adequados, determina os melhores parâmetros e estabelece um modelo de previsão. O modelo é publicado no catálogo.
3. Em seguida, você pode acessar esse modelo, aplicá-lo aos seus dados e analisar os resultados diretamente no site Apptio. Quando as previsões tiverem sido revisadas como parte do seu processo de configuração, os dados agora classificados serão enviados ao nosso serviço de treinamento.
4. Os novos dados acionam o serviço de treinamento para tornar anônimo e gerar um novo modelo. Apptio rastreia e ajusta os modelos ao longo do tempo para melhorar a qualidade e a quantidade de nossas previsões.
5. Quando um modelo atende à nossa análise de qualidade, ele é publicado no catálogo.
6. Você pode atualizar para o modelo mais recente conforme desejar.

Aqui está um diagrama do processo:

![](../../resources/images/studio_images/studioimages/studio_diagram_download%20model.png)

**VEJA TAMBÉM** :

- [Colunas do mapa](mapcolumns.htm "(Abre em uma nova guia ou janela)")
- [Configurar o aprendizado de máquina para pools de custos](configuremachinelearning.htm "(Abre em uma nova guia ou janela)")
- [Perguntas frequentes sobre Map Columns](faqmapcolumns.htm "(Abre em uma nova guia ou janela)")
