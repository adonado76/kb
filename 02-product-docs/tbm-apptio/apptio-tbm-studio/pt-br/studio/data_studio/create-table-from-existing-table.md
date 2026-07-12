---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Criar uma tabela a partir de uma tabela existente"
breadcrumb: []
source_path: "studio/data_studio/create-table-from-existing-table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Criar uma tabela a partir de uma tabela existente

**Aplica-se a** : TBM Studio 12.0 e posterior

Pode haver ocasiões em que você queira criar uma nova tabela a partir de uma tabela existente. Por exemplo, você pode ter uma tabela que contém uma grande quantidade de informações em várias colunas e deseja criar um conjunto de dados com apenas algumas colunas para fins de relatório.

Quando você cria uma nova tabela a partir de uma tabela existente, a nova tabela é vinculada à tabela de origem. Você pode usar os dados de origem ou a tabela de saída. Os dados de origem usam os dados brutos carregados no aplicativo. A tabela de saída usa os dados após a aplicação de todas as etapas do pipeline de transformação.

Há muitos motivos pelos quais você pode querer criar uma transformação:

- Limpando os dados
- Criar o nível adequado de granularidade nos dados
- Validação dos dados
- Realização de uniões complexas
- Realização de cálculos

Há duas maneiras de criar uma nova tabela a partir de uma tabela existente:

- Crie uma nova tabela e use a opção de origem **Tabela existente**.
- Clique com o botão direito do mouse na etapa **Importar** ou na etapa **Tabela** no pipeline de transformação de uma tabela existente e clique em **Criar nova tabela a partir desta etapa**.

Depois de criar a tabela, clique na etapa **Tabela existente** no pipeline de transformação da nova tabela e clique na opção **Dados de origem** ou **Tabela de saída**.
