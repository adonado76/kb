---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Solução de problemas: não é possível importar ou exportar arquivos do Excel"
breadcrumb: []
source_path: "it-planning/planning/ts_unable_imp_exp_xsl.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Solução de problemas: não é possível importar ou exportar arquivos do Excel

## Antes de começar

Não é possível fazer upload de dados de arquivos do Microsoft Excel na ferramenta Planning ou exportar dados de arquivos do Excel de Planning.

## Sobre esta tarefa

Planning usa o formato de arquivo.CSV para os dados carregados e não é compatível com os formatos de arquivo padrão do Excel, como.XLS e.XLSX.

Adote.CSV como seu formato de arquivo de dados padrão ao usar a ferramenta Planning . Você pode exportar seu orçamento.CSV para o computador, fazer alterações no arquivo.CSV no Excel e, em seguida, importar o novo arquivo.CSV de volta para Apptio.

## Procedimento

- **Salvando arquivos do Excel como.CSV**
  1. Abra o Microsoft Excel e abra o arquivo que você deseja carregar em Apptio. Faça os ajustes necessários.
  2. Clique em Salvar como e selecione o formato de arquivo ( \*.csv ).

     Um novo arquivo.CSV é criado. Você pode editar arquivos.CSV no Excel, o que lhe permite fazer os ajustes necessários antes de fazer o upload dos arquivos.
- **Importar arquivos.CSV para Planning**

  Ao importar arquivos.CSV, você está substituindo todos os dados atuais do item de linha pelos do arquivo importado. Não há mesclagem ou adição de dados ao importar arquivos para o site Planning.

  Para obter mais informações, consulteSaiba [mais sobre como entrar ou importar dados de partidas individuais no Planning.](enter-import-line.html)
- **Exportar arquivos.CSV de Planning**

  Os arquivos exportados do site Planning para o seu computador estarão no formato.CSV por padrão.

  Para obter mais informações, consulteSaiba [mais sobre como exportar e preencher tabelas de partidas individuais ou layouts no Planning.](export-populate-line.html)
