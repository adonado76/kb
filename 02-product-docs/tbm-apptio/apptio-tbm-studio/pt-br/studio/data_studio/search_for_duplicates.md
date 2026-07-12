---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Pesquisar entradas duplicadas em uma tabela"
breadcrumb: []
source_path: "studio/data_studio/search_for_duplicates.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Pesquisar entradas duplicadas em uma tabela

**Aplica-se a** : TBM Studio 12.0 e posterior

Pode haver ocasiões em que você queira pesquisar entradas duplicadas em uma coluna da tabela. Por exemplo, você pode ter criado uma coluna que servirá como um identificador exclusivo e quer ter certeza de que não há chaves duplicadas.

Para pesquisar entradas duplicadas em uma tabela:

1. Clique na etapa **Table (Tabela** ) no pipeline de transformação, clique com o botão direito do mouse no cabeçalho da coluna e, em seguida, clique em **Show Values (Mostrar valores** ).
2. Na coluna Contagem, na seção **Valores em...** digite **!=1**. Isso procurará linhas que não tenham um valor de 1, o que indicará entradas duplicadas.
