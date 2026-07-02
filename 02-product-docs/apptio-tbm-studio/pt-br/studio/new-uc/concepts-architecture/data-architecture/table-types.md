---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Tabelas e tipos de tabelas"
breadcrumb:
  - "TBM Studio"
  - "Conceitos e Arquitetura"
  - "Arquitetura de dados"
source_path: "studio/new-uc/concepts-architecture/data-architecture/table-types.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tabelas e tipos de tabelas

As tabelas são os principais contêineres de dados no TBM Studio. Todos os dados que entram, transitam ou saem da plataforma fazem isso por meio de uma tabela. O TBM Studio oferece vários tipos de tabelas, cada uma projetada para uma função específica no ciclo de vida dos dados.

## Tabelas de fontes / arquivos

**Objetivo:** Importar dados externos para o TBM Studio a partir de arquivos ou conexões com bancos de dados.

Uma tabela de origem é o ponto de entrada para seus dados. Ao criar uma nova tabela e fazer o upload de um arquivo do tipo “ CSV ” ou Excel, o TBM Studio cria uma tabela de origem com um pipeline de transformação associado. A plataforma analisa seu arquivo, detecta automaticamente os tipos de coluna (Rótulo, Numérico ou Estado) e exibe uma pré-visualização para sua confirmação.

As tabelas de origem suportam vários métodos de importação de dados:

- **Upload de arquivos:** Arraste e solte ou selecione arquivos nos formatos CSV, TSV, XLS ou XLSX para fazer o upload. A plataforma analisa o arquivo e detecta automaticamente a linha de cabeçalho, as linhas de dados e os tipos de coluna.
- **DataLink (Clássico) Conector:** Importe dados usando um conector predefinido para extraí-los diretamente de bancos de dados ou sistemas externos.
- **Tabela gerada:** Crie uma nova tabela derivada de uma tabela existente no projeto. A nova tabela não estará vinculada à original.
- **Tabela existente (vinculada):** Crie uma nova tabela a partir de uma tabela existente, mantendo um vínculo para que a tabela derivada permaneça conectada à sua fonte.

Após o upload, seus dados passam por um pipeline de transformação, onde você pode adicionar etapas para limpá-los, filtrá-los, juntá-los e reestruturá-los antes de serem inseridos no modelo de custos.

Nota:

**Quando usar tabelas de origem**

Use tabelas de origem sempre que precisar importar dados externos para o TBM Studio. Isso inclui exportações do razão geral, arquivos de orçamento, planilhas de previsão, inventários de ativos e quaisquer outros dados originados fora da plataforma.

- **[Transformar tabelas](../../../../studio/new-uc/concepts-architecture/data-architecture/transform-tables.html)**
- **[Tabelas editáveis](../../../../studio/new-uc/concepts-architecture/data-architecture/editable-tables.html)**
- **[Como as tabelas editáveis se encaixam no fluxo de dados](../../../../studio/new-uc/concepts-architecture/data-architecture/editable-tables-fir-data-flow.html)**
- **[Tabelas publicadas](../../../../studio/new-uc/concepts-architecture/data-architecture/published-tables.html)**
- **[Matriz de decisão em forma de tabela](../../../../studio/new-uc/concepts-architecture/data-architecture/table-type-decission-matrix.html)**
