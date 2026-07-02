---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Dimensões personalizadas"
breadcrumb: []
source_path: "it-planning/planning/manage-custom-reference.html"
images:
  - "resources/images/icons/3-dots.png"
  - "resources/planning_images/itp-expenses-menu-bar.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Dimensões personalizadas

As tarefas abaixo só podem ser executadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.

Apptio Planning os aplicativos suportam dimensões personalizadas, listas personalizadas e edição do esquema de tabelas de itens de linha. Você pode fazer o seguinte:

- Crie até 13 dimensões personalizadas para ampliar as dimensões integradas (consulte [Aplicativos de planejamento: Gerenciar dados de referência](manage-reference-data.html) ). Use dimensões personalizadas para definir os conjuntos de categorias de dados que ampliam e aprimoram seu planejamento e análise financeiros. Por exemplo, crie uma dimensão personalizada para associar vários atributos, como Iniciativa Empresarial, ao Código WBS.
- Crie listas personalizadas para definir os valores permitidos de um único atributo. Por exemplo, você pode criar uma lista de status com valores como Triado, Entrevistado e Contratado para ser adicionada à tabela de itens de linha de mão de obra. Consulte [Listas personalizadas](custom-lists.html) para obter mais informações.
- Personalize o esquema das tabelas de itens de linha que mapeiam para as guias da visualização Despesas:

  ![imagem](../../../../../03-media/apptio-planning/resources/planning_images/itp-expenses-menu-bar.png)

Para acessar dimensões e dados personalizados:

No menu de navegação, selecione Configuração > Esquema.

## Qual é a diferença entre Custom Dimensions e Custom Lists?

| Dimensões personalizadas | Listas personalizadas |
| --- | --- |
| Use dimensões personalizadas para definir os conjuntos de categorias de dados que ampliam e aprimoram seu planejamento e análise financeiros. | Use listas personalizadas para definir os valores permitidos de um único atributo. |
| As dimensões personalizadas podem incluir atributos personalizados, que contêm informações suplementares que estão intimamente relacionadas à dimensão. | As listas personalizadas não incluem atributos personalizados. |
| Para criar uma dimensão personalizada, você pode importar valores usando a integração Costing Standard . | Para criar uma lista personalizada, você deve inserir os valores manualmente. |
| Você pode renomear colunas nos Dados de referência.  [Saiba mais sobre como renomear uma coluna](manage_schema.html "Os esquemas definem a estrutura dos dados no Apptio Planning. Eles especificam as tabelas, os campos e os relacionamentos que determinam como as informações são armazenadas, vinculadas e exibidas nas guias Despesas, como Trabalho, Contratos, Ativos e Finanças.").  - Quando a coluna é renomeada, os usuários veem o novo nome nos cabeçalhos das colunas da tabela de itens de linha. | Não é possível renomear a coluna em listas personalizadas. |
| Você pode filtrar uma dimensão personalizada em uma tabela de itens de linha. | Não é possível filtrar uma lista personalizada em uma tabela de itens de linha. |
| Você pode criar um máximo de 13 dimensões personalizadas. | Você pode criar um número ilimitado de listas personalizadas. |

Observação: os dados das dimensões personalizadas excluídas são removidos de todos os planos e não podem ser recuperados.

## Gerenciar dimensões personalizadas

Dica: Para criar uma nova dimensão personalizada ou adicionar um atributo a uma dimensão, consulte [Adicionar e gerenciar atributos personalizados de dimensões](manage_schema.html "Os esquemas definem a estrutura dos dados no Apptio Planning. Eles especificam as tabelas, os campos e os relacionamentos que determinam como as informações são armazenadas, vinculadas e exibidas nas guias Despesas, como Trabalho, Contratos, Ativos e Finanças.").

## Faça o download e preencha os modelos de tabela de dimensões personalizadas

Você pode importar dados de referência do site Costing Standard. Quando você importa dados de referência, o site Planning importa o conjunto de dados de referência mais recente, independentemente da configuração da data ativa em Costing Standard. Consulte [Integrar com transparência de custos](integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados.").

1. No menu de navegação, selecione Configuration > Reference Data (Configuração > Dados de referência ).
2. Selecione a guia Custom Dimensions (Dimensões personalizadas ).
3. Selecione uma tabela e, em seguida, selecione ![mais ícone](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) > Exportar.
4. Na janela Exportar arquivo, em Opções de formato, você pode alterar o formato dos dados exportados.
5. Selecione Exportar. Os dados de referência são exportados como um arquivo.csv.
6. Abra o arquivo de modelo.csv baixado e adicione os atributos adicionais desejados.

   OBSERVAÇÃO : não altere os títulos das colunas ou a estrutura desse modelo, pois ele representa uma estrutura de dados obrigatória.
7. Salve o modelo no formato.csv para importá-lo em seu aplicativo Apptio Planning .

## Criar, importar e publicar uma nova dimensão personalizada

Depois de criar o arquivo.csv com os valores de dimensão desejados, você pode criar a dimensão personalizada e, em seguida, carregar os valores do arquivo.csv na dimensão.

1. Para criar uma nova dimensão personalizada, consulte [Adicionar e gerenciar atributos personalizados de dimensões](manage_schema.html "Os esquemas definem a estrutura dos dados no Apptio Planning. Eles especificam as tabelas, os campos e os relacionamentos que determinam como as informações são armazenadas, vinculadas e exibidas nas guias Despesas, como Trabalho, Contratos, Ativos e Finanças.").
2. Ao lado da nova dimensão personalizada, clique em Import New (Importar novo ).
3. Siga as instruções na tela para concluir o processo de importação de dados. Examine e verifique seus dados importados:
   - Se seus dados estiverem corretos e você quiser disponibilizá-los nos planos, clique em Publish.
   - Se você encontrar problemas com seus dados e precisar solucioná-los antes de publicar, clique em Reverter.

## Excluir uma dimensão personalizada

Para excluir uma dimensão personalizada, consulte [Excluir uma coluna da tabela de dados de referência](manage_schema.html "Os esquemas definem a estrutura dos dados no Apptio Planning. Eles especificam as tabelas, os campos e os relacionamentos que determinam como as informações são armazenadas, vinculadas e exibidas nas guias Despesas, como Trabalho, Contratos, Ativos e Finanças.")

CUIDADO:

Os dados de dimensões personalizadas excluídas são removidos de todos os planos e não podem ser recuperados.

**Tópico pai:** [Visão geral dos dados de referência](../../it-planning/planning/edit-publish-reference.html "As tarefas abaixo só podem ser executadas por usuários atribuídos às funções Admin ou Budget Process Owner. Para obter mais informações sobre funções, consulte Permissões e funções do Frontdoor.")
