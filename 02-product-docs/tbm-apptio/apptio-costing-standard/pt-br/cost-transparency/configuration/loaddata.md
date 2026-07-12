---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Carregar dados no aplicativo Costing Standard"
breadcrumb: []
source_path: "cost-transparency/configuration/loaddata.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Carregar dados no aplicativo Costing Standard

As tabelas de dados mestre fornecem uma maneira de mapear seus dados para os dados exigidos pelo aplicativo CT. As informações abaixo descrevem como carregar dados no aplicativo.

## Introdução

Cada componente do Costing Standard (CT) tem uma tabela de dados mestre. A tabela de dados mestre fornece estrutura para os dados relacionados. Relatórios, alocações e outros itens de configuração estão vinculados à estrutura da tabela de dados mestre. Você não edita diretamente as tabelas de dados mestre. Em vez disso, você anexa e mapeia dados às tabelas. Isso garante que a estrutura das tabelas de dados mestre não seja alterada.

As informações abaixo descrevem como carregar dados no aplicativo. Consulte este tópico quando precisar fazer upload de uma tabela de dados. O procedimento de upload não está descrito em nenhum outro lugar do Guia de Configuração.

## Faça upload de seus dados de origem

Você deve carregar seus dados de origem no aplicativo. Depois de carregar os dados, você pode mapeá-los para a tabela de dados mestre de um componente. As tabelas de dados que você carregar devem conter campos que possam ser mapeados para os campos necessários nas tabelas de dados mestre. As tabelas de dados não precisam conter todos os campos das tabelas de dados mestre.

O procedimento geral para fazer upload de uma tabela de origem é apresentado a seguir:

1. Clique na guia **Home** na faixa de opções.
2. Clique no menu **New (Novo** ) e depois em **Table (Tabela** ).
3. Na caixa de diálogo Criar tabela, digite um nome para a tabela.
4. Insira uma categoria. Quando você começar a digitar, serão exibidos os nomes correspondentes das categorias que já existem. Além disso, você pode inserir um novo nome de categoria. As categorias são usadas para organizar as tabelas no Project Explorer.
5. Clique em **OK**. O aplicativo cria a tabela e exibe a etapa Source no pipeline de transformação, conforme mostrado abaixo.
6. Clique na opção **File Upload**.
7. Execute uma das seguintes ações para adicionar uma etapa de importação ao pipeline:
   - Clique no painel **Detalhes** e navegue até o arquivo que deseja carregar.
   - Arraste um arquivo para o painel **Detalhes**.Uma etapa de importação é adicionada ao pipeline.
8. Clique na etapa **Importar** no pipeline e revise as configurações:
   - Iniciar importação na linha - Indique a primeira linha da tabela a ser incluída na importação.
   - Columns to Exclude (Colunas a serem excluídas) - Indique se há colunas que você deseja excluir.
   - Text Encoding (Codificação de texto) - Se o arquivo de dados usar uma codificação de caracteres específica, selecione o esquema de codificação na lista. Se você não tiver certeza sobre a codificação, selecione a opção Autodetect encoding (Detectar codificação automaticamente).
   - Delimitado -Selecione o caractere que separa os campos de dados no arquivo. Na maioria das vezes, será uma vírgula.
   - Qualificador de texto - Se houver caracteres de texto especiais nos dados, indique o qualificador de texto que é usado para envolver esses caracteres.
   - Colunas - Revise as colunas listadas à direita e, se desejar, altere os tipos de coluna. Para filtrar por tipo de coluna (chave, texto, número, data), clique em um ícone de tipo no campo de pesquisa da coluna Tipo.
9. Para revisar a tabela carregada, clique na etapa **Tabela** no pipeline.
10. Se a tabela for aceitável, clique em **Save (Salvar** ) na faixa de opções.
11. Se você terminar de fazer as edições, clique em **Check In** na faixa de opções.

## Informações relacionadas

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentários sobre a Central de Ajuda](productfeedback@apptio.com "(Abre em uma nova guia ou janela)")
