---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Nenhum identificador no objeto de modelo grande"
breadcrumb: []
source_path: "studio/troubleshooting/studio-troubleshooting-large-identifier.html"
images:
  - "resources/images/studio_images/troubleshooting/large-identifier-solution.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Nenhum identificador no objeto de modelo grande

Para melhorar o desempenho, os objetos do modelo com um grande número de linhas devem ter um identificador.

[Criar um identificador de tabela personalizado](../model_studio/create-custom-table-identifier.html "Aplica-se a: TBM Studio 12.0 e posterior. O ambiente de modelagem Apptio oferece uma estrutura flexível para manipular dados em agrupamentos que formam a base para alocações e relatórios. A seguir, serão explicadas as práticas recomendadas para escolher o identificador correto para uma determinada tabela de modelos.")

## Recomendação de configuração para o erro No identifier on large model object

Para resolver esse erro:

1. Verifique o objeto afetado.
2. No menu suspenso Rows (Linhas), selecione Use object identifier (Usar identificador de objeto) e, em seguida, selecione as colunas necessárias para o identificador.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/large-identifier-solution.png)

Dica: As colunas a seguir são normalmente necessárias no identificador:

- Tendências por
- Alocação por
- Cortando por
- Pivotando em
- Agrupamento por
- Relatórios

A menos que sejam usados para as colunas acima, os identificadores não precisam ser exclusivos.
