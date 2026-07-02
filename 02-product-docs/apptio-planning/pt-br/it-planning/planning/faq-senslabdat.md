---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "PERGUNTAS FREQUENTES: Ocultar dados trabalhistas confidenciais"
breadcrumb:
  - "Planning"
  - "Solução de problemas e perguntas frequentes"
source_path: "it-planning/planning/faq-senslabdat.html"
images:
  - "resources/images/it_planning_images/cost_object_permissions.jpg"
  - "resources/images/it_planning_images/edit-sys-attr-dialog.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# PERGUNTAS FREQUENTES: Ocultar dados trabalhistas confidenciais

Esta é uma lista de perguntas frequentes sobre as funções Hide Sensitive Labor Data (Ocultar dados confidenciais de mão de obra), que foi introduzida na versão Planning 2.81.

## P. O que faz a ativação de Can View Sensitive Columns?

R. Se você ativar a opção Can view Sensitive Columns (Pode visualizar colunas confidenciais), o usuário poderá ver as colunas marcadas como confidenciais no esquema da tabela de itens de linha do Labor. Isso se aplica tanto à guia Trabalho quanto à guia Resumo.

Se o usuário não tiver a opção Can View Sensitive Columns ativada para um objeto de custo, ele não poderá visualizar colunas confidenciais para esse objeto ou para qualquer um dos objetos de custo pai ou filho desse objeto de custo.

## P. O que faz a ativação do Can View Sensitive Financials?

R. Se você ativar a opção Can view Sensitive Financials, o usuário poderá visualizar os dados financeiros gerados pela linha de trabalho. Na guia Resumo, eles podem ver os itens de linha de mão de obra gerados somente para leitura para o objeto de custo.

Se o usuário não tiver a opção Can View Sensitive Financials ativada para um objeto de custo, ele não poderá visualizar nenhum relatório financeiro gerado por mão de obra para esse objeto de custo. Isso significa que os valores estão faltando nos KPIs, gráficos, tabelas, exportações e em qualquer operação que extraia dados do banco de dados.

## P. O que acontece se eu ativar o Can View Sensitive Columns, mas não o Can View Sensitive Financials?

R. Se um usuário tiver permissão para visualizar colunas confidenciais, mas não tiver permissão para visualizar finanças confidenciais, ele poderá visualizar as linhas na guia Trabalho, mas não poderá ver os itens de linha de trabalho gerados na guia Resumo.

![permissões de objeto de custo](../../../../../03-media/apptio-planning/resources/images/it_planning_images/cost_object_permissions.jpg)

Figura 1: Conceder a um usuário acesso a dados trabalhistas confidenciais

## P. Um usuário pode exportar valores de colunas confidenciais se não tiver permissão para visualizá-los?

R. Nº Se um usuário exportar os valores de um objeto de custo e não tiver permissão para visualizar colunas confidenciais desse objeto de custo, o site IT Planning exportará apenas as colunas que ele tiver permissão para visualizar.

## P. Um usuário pode importar valores para colunas confidenciais se não tiver permissão para visualizá-los?

R. Nº Se um usuário tentar importar valores para um objeto de custo usando a opção Substituir tudo, a importação falhará e uma mensagem de erro será exibida.

Para importar valores para as colunas que ele tem permissão para visualizar, o usuário ainda pode usar a opção Append.

## P. Como faço para definir uma coluna como Dados confidenciais ou Obrigatório para entrada de dados?

R. Faça o seguinte:

1. Navegue até Configuração > Esquema > Itens de linha > Trabalho e selecione a coluna Atributo.

   ![editar atributos](../../../../../03-media/apptio-planning/resources/images/it_planning_images/edit-sys-attr-dialog.jpg)
2. Na caixa de diálogo Edit System Attribute (Editar atributo do sistema), selecione Mandatory for Data Entry (Obrigatório para entrada de dados) ou Sensitive Data (Dados sensíveis) e, em seguida, selecione Save (Salvar).

## P. É possível definir uma coluna como “Obrigatória para preenchimento” e, ao mesmo tempo, como “Dados confidenciais”?

R. Nº Se uma coluna for definida como Obrigatória para entrada de dados ou Dados confidenciais, ela não poderá ser definida como a outra.

## P. Se um layout público incluir uma coluna sensível, a coluna poderá ser visualizada no layout por um usuário que não tenha permissão para visualizar essa coluna?

R. Nº As permissões de dados confidenciais são aplicadas em todos os layouts, de modo que o usuário não poderá ver a coluna confidencial quando visualizar o layout.

## P. Se um filtro ou agrupamento for aplicado a uma coluna sensível e um usuário não puder visualizar colunas sensíveis, isso afetará o que o usuário pode ver?

R. Se um usuário não tiver permissão para visualizar uma coluna, todos os filtros ou agrupamentos aplicados a essa coluna serão removidos.

## P. Se um usuário tiver uma função de administrador ou de proprietário do processo orçamentário, ele verá automaticamente os dados confidenciais?

R. Sim, independentemente das permissões definidas em “Permissões de objeto de custo”, os usuários com a função de Administrador ou Responsável pelo processo orçamentário terão acesso a dados confidenciais, independentemente das permissões definidas em “Permissões de objeto de custo”. Além disso, qualquer usuário ao qual tenha sido atribuída uma função personalizada com a permissão “ “ManagePlans” ” também poderá visualizar dados confidenciais.

## P. Se o proprietário de um centro de custo tiver acesso a um projeto e a um departamento, ele poderá ter permissões para visualizar as colunas de dados confidenciais de um, mas não do outro?

R. Sim. Por exemplo, se o proprietário do centro de custo tiver permissão para visualizar dados confidenciais no projeto, mas não no departamento, ele poderá visualizar uma coluna confidencial no lado do projeto, mas não no lado do departamento.

## P. Se um administrador não tiver permissão para visualizar colunas de dados confidenciais, ele poderá publicar dados de colunas confidenciais em Costing Standard?

R. Nº Um administrador só pode publicar dados de Colunas de dados confidenciais em Costing Standard se tiver permissão para visualizar Colunas de dados confidenciais.

## P: Se um administrador não tiver permissão para visualizar os dados financeiros gerados para um objeto de custo de departamento, o que acontecerá quando ele publicar em Costing Standard?

R: Os dados financeiros gerados aos quais eles não têm acesso serão omitidos da publicação da Transparência de custos.

## P: Se um administrador não tiver permissão para visualizar as colunas de dados confidenciais de um objeto de custo de departamento de folha, o que acontecerá quando ele publicar em Costing Standard em um nível de todos os departamentos?

R: Nenhum dos dados nas colunas confidenciais será publicado em Costing Standard.

Por exemplo, um usuário está visualizando um objeto de custo (Objeto de custo A). O usuário não tem permissão para visualizar Colunas de dados confidenciais e um Objeto de custo filho do Objeto de custo A (Objeto de custo A1 ) tem uma coluna definida como Coluna de dados confidenciais. Planning oculta essa coluna do usuário quando ele visualiza o Objeto de custo A. Isso ocorre porque o site Planning só pode ocultar uma coluna inteira; ele não pode ocultar as células específicas pertencentes a um Objeto de custo filho.

Se um usuário não tiver permissão para visualizar uma coluna, ele não poderá exportá-la para CSV nem publicá-la em Costing Standard.

## Q. Se a opção Enforce View Permissions (Aplicar permissões de visualização) estiver desativada, as restrições em Colunas de dados confidenciais ainda se aplicam?

R. Sim. Se um objeto de custo tiver permissões de colunas de dados confidenciais configuradas, essas restrições serão aplicadas independentemente de a opção Aplicar permissões de visualização estar ativada ou desativada.

## P. Uma coluna Delegação pode ser marcada como sensível?

R. Nº Uma coluna Delegação sempre pode ser visualizada por todos os usuários.

## P. O uso de permissões de dados confidenciais reduz sensivelmente o desempenho?

R. Nº Embora a aplicação de permissões a dados confidenciais exija a execução de uma consulta na hierarquia de objetos de custo, essa é uma consulta única e não deve ser percebida pelos usuários.

## P. O usuário pode saber se os dados que está vendo ocultam colunas confidenciais ou financeiras?

R. Nº O usuário não pode saber se há dados adicionais que ele não tem permissão para ver.

## P. O que acontece se a remuneração base for marcada como dados confidenciais?

A. Se a Remuneração base estiver marcada como Dados confidenciais, um usuário que não tenha permissão para visualizar as Colunas de dados confidenciais não poderá visualizar nenhum item financeiro do Objeto de custo, inclusive os Totais do ano fiscal (FY).

## P. Se um usuário tiver permissões diferentes para um objeto de custo pai e um filho, qual conjunto de permissões será aplicado?

R. Se um usuário não tiver permissões para visualizar dados confidenciais de um objeto de custo filho, ele não poderá visualizar a coluna ou o Financial no objeto pai. Isso se deve ao fato de que as colunas sensíveis e os dados financeiros nos objetos de custo pai agregam dados de objetos filhos, e não é possível exibir os dados com precisão no objeto pai se os dados de um objeto filho forem excluídos.

## P. Se um usuário tiver permissões de dados confidenciais diferentes para níveis mais altos e mais baixos de objetos de custo, qual conjunto de permissões será aplicado?

R. Um usuário de centro de custo pode ter acesso para visualizar dados confidenciais de despesas com mão de obra em um nível de objeto de custo inferior, no qual o usuário tem acesso para visualizar/editar o objeto de custo, ao mesmo tempo em que impede o acesso do mesmo usuário para visualizar dados confidenciais de despesas com mão de obra em um nível de objeto de custo superior, mesmo que o usuário tenha acesso para visualizar/editar o objeto de custo em um nível de objeto de custo superior.
