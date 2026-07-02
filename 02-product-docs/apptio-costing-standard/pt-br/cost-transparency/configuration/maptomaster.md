---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Mapear dados para uma tabela de dados mestre"
breadcrumb: []
source_path: "cost-transparency/configuration/maptomaster.html"
images:
  - "resources/images/ct_images/6875_1.png"
  - "resources/images/ct_images/6875_2.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Mapear dados para uma tabela de dados mestre

Depois de fazer upload de uma tabela de dados de origem e transformá-la, se necessário, você pode mapeá-la para uma tabela de dados mestre. Use as instruções a seguir para mapear dados para uma tabela de dados mestre.

Aplica-se a: Costing Standard em TBM Studio 12.0 e posterior

## Sobre esta tarefa

O método principal (e preferido) para mapear dados é usar Map Columns em vez das instruções nas informações abaixo. O recurso Map Columns tem o objetivo de transformar seu conjunto de dados de origem. Se os dados forem reutilizados em vários conjuntos de dados mestre, crie uma nova tabela usando Origem da tabela existente para cada conjunto de dados mestre e, em seguida, adicione Colunas de mapa. Para obter instruções completas, consulte [Colunas do mapa](https://community.apptio.com/docs/DOC-11750 "(Abre em uma nova guia ou janela)").

As informações abaixo explicam o método menos preferido para mapear dados usando a etapa Append no conjunto de dados mestre. Esse método é menos preferido porque personaliza o conjunto de dados mestre, o que aumenta o tempo de atualizações para receber novos conteúdos. Para obter mais informações, consulte [Anexar dados](https://community.apptio.com/docs/DOC-4980 "(Abre em uma nova guia ou janela)").

## Procedimento

1. No **Project Explorer**, clique na tabela de dados mestre desejada.
2. Dê uma olhada na tabela.
3. No pipeline de transformação, clique na etapa **Append**.
4. Clique em Append **Table (Anexar tabela** ) na área de detalhes.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6875_1.png)
5. Selecione uma tabela de dados de origem e clique em **Next.**
6. Mapeie as colunas de origem para as colunas do conjunto de dados mestre usando o seguinte **Append to...** Imagem de dados mestre.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6875_2.png)

   Observação: Um asterisco (\*) na coluna Dados mestre indica que o campo é obrigatório para preencher totalmente os relatórios relacionados a esse conjunto de dados. O mapeamento parcial é permitido. Se você não tiver todos os dados necessários, poderá mapear um subconjunto dos campos obrigatórios, embora isso possa resultar na falta de dados em um ou mais relatórios.
7. Clique em Save.
