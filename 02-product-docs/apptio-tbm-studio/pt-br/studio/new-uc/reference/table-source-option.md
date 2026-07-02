---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Opções de fonte da tabela"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Data Studio Referência"
  - "Tabelas"
source_path: "studio/new-uc/reference/table-source-option.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Opções de fonte da tabela

Ao criar uma tabela, é necessário selecionar um tipo de fonte que determine como os dados são inseridos na tabela.

**Upload de arquivo**

**Descrição:** Importar dados de arquivos locais ou da rede

**Formatos compatíveis:**

|  |  |  |
| --- | --- | --- |
| **Formato** | **Extensões** | **Notas** |
| Excel | .xls,.xlsx | Apenas um ponto no nome do arquivo |
| CSV | .csv | Valores separados por vírgulas |
| Texto delimitado | .txt | Tabulação, barra vertical, til, dois pontos, ponto-e-vírgula |
| XML | .xml | Dados estruturados |
| ZIP | .zip | Arquivos compactados |

**Regra de nomenclatura de arquivos:** Os nomes dos arquivos devem conter apenas um ponto (.) antes da extensão.

- example\_data.xlsx - Correto
- example.data.xlsx - Incorreto (gera um erro de extensão de arquivo não suportada)

**Etapas do fluxo de trabalho criadas:** Origem > Carregar > Importar > Tabela

**Tabela existente**

**Descrição:** Criar uma nova tabela com base nos dados de saída de outra tabela, mantendo uma ligação

**Casos de uso:**

- Criação de subconjuntos filtrados de dados mestre
- Criação de tabelas de relatórios especializadas
- Aplicação de transformações adicionais aos dados processados

**Opções:**

|  |  |
| --- | --- |
| **Opção** | **Descrição** |
| Dados de origem | Utiliza os dados brutos da tabela de origem |
| Tabela de saída | Utiliza os dados após a aplicação de todas as etapas de transformação |

**Tópico principal:** [Tabelas](../../../studio/new-uc/reference/tables.html)
