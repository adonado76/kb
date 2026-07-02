---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "pt-br"
doc_type: "cost-transparency"
title: "Carregar dados"
breadcrumb:
  - "Costing Standard"
  - "Configuração"
source_path: "cost-transparency/configuration/config-loaddata.html"
images:
  - "resources/images/studio_images/load4a.png"
  - "resources/images/studio_images/load6.png"
  - "resources/images/studio_images/load7.png"
  - "resources/images/studio_images/load9.png"
  - "resources/images/studio_images/lod2a.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Carregar dados

As tabelas de dados mestre oferecem uma maneira de mapear seus dados para os dados exigidos pelo aplicativo CT.

Cada componente do Padrão de Cálculo de Custos (CT) possui uma tabela de dados mestre. A tabela de dados mestre fornece estrutura aos dados relacionados. Relatórios, alocações e outros itens de configuração estão vinculados à estrutura da tabela de dados mestre. Você não carrega dados diretamente nas tabelas de dados mestre. Em vez disso, você anexa ou mapeia os dados (usando a etapa Mapear no pipeline de dados) às tabelas. Isso garante que a estrutura das tabelas de dados mestre não seja alterada.

Você deve carregar seus dados de origem no aplicativo. Depois de carregar os dados, você pode mapeá-los para a tabela de dados mestre de um componente. As tabelas de dados que você carregar devem conter campos que possam ser mapeados para os campos obrigatórios nas tabelas de dados mestre. As tabelas de dados não precisam conter todos os campos das tabelas de dados mestre.

Para obter mais detalhes sobre os tipos de dados que podem ser carregados e os diferentes métodos disponíveis para carregar dados, clique [aqui.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload "(Abre em uma nova guia ou janela)")

O procedimento geral para carregar uma tabela de origem é apresentado abaixo:

1. Clique na guia **Página inicial** na faixa de opções.
2. Clique no menu **Novo** e, em seguida, clique em **Tabela**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/lod2a.png)
3. Na caixa de diálogo Criar tabela, insira um nome para a tabela.
4. Insira uma categoria. À medida que você começa a digitar, os nomes das categorias correspondentes que já existem serão exibidos. Além disso, você pode inserir um novo nome de categoria. As categorias são usadas para organizar as tabelas no Explorador de Projetos.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load4a.png)
5. Clique em **OK**. O aplicativo cria a tabela e exibe a etapa Origem no pipeline de transformação, conforme mostrado abaixo.
6. Clique na opção “**Upload de arquivo** ”. Para obter mais informações sobre outras opções, clique [aqui](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload "(Abre em uma nova guia ou janela)").

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load6.png)
7. Será criada uma etapa de upload onde o usuário poderá clicar/arrastar o arquivo ou clicar com o botão direito do mouse para colar o arquivo.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load7.png)
8. Uma etapa de importação é adicionada ao pipeline.
9. Clique na etapa **Importar** no pipeline e revise as configurações:
   - Iniciar importação na linha - Indique a primeira linha da tabela a ser incluída na importação.
   - Colunas a excluir - Indique se há colunas que deseja excluir.
   - Codificação de texto - Se o arquivo de dados usar uma codificação de caracteres específica, selecione o esquema de codificação na lista. Se você não tiver certeza sobre a codificação, selecione a opção Detectar automaticamente a codificação.
   - Delimitado - Selecione o caractere que separa os campos de dados no arquivo. Na maioria das vezes, será uma vírgula.
   - Qualificador de texto - Se houver caracteres de texto especiais nos dados, indique o qualificador de texto usado para envolver esses caracteres.
   - Colunas - Revise as colunas listadas à direita e, se desejar, altere os tipos de coluna. Para filtrar por tipo de coluna (chave, texto, número, data), clique em um ícone de tipo no campo de pesquisa da coluna Tipo.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/load9.png)
10. Para revisar a tabela carregada, clique na etapa **Tabela** no pipeline.
11. Se a tabela estiver aceitável, clique em **Salvar** na faixa de opções.
12. Quando terminar as edições, clique em **Check-in** na faixa de opções. Para mais informações sobre check-in e check-out, clique [aqui.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-best-practices-check-out-check-in "(Abre em uma nova guia ou janela)")

Para obter mais detalhes sobre funcionalidades adicionais relacionadas ao upload de tabelas, clique [aqui.](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=data-upload-file "(Abre em uma nova guia ou janela)")

**Excluir uma tabela**

1. Confira a tabela.
2. Na guia **Página inicial**, no grupo **Documento**, clique em **Excluir**.
3. Verifique na tabela.
