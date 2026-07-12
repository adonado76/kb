---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Importação real"
breadcrumb: []
source_path: "it-planning/planning/import-publish-actuals.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Importação real

Para ajudar a gerenciar as despesas, você compara o plano orçamentário ou a previsão com os dados reais históricos. A fonte de dados reais pode ser seu sistema de gerenciamento financeiro, TBM Studio, ou Costing Standard.

## Preencher o arquivo.csv de dados reais

Importe os dados reais um mês de cada vez. Para importar todo mês:

1. No menu de navegação, selecione Gerenciamento de despesas > Transações.

   Nota:

   O recurso Enforce View Permissions (Aplicar permissões de visualização ) pode ser ativado no Company Profile (Perfil da empresa). Consulte [Editar o perfil da empresa](edit-company-profile.html "O Company Profile permite que os usuários Admin e Budget Process Owner definam as configurações de todo o aplicativo que personalizam a exibição, ativam ou desativam recursos e definem o comportamento do fluxo de trabalho em Apptio Planning."). Se o recurso estiver ativado, a página Gerenciamento de despesas ficará visível somente para as seguintes pessoas:
   - Proprietários do processo orçamentário
   - Administradores
   - Proprietários do orçamento (que podem visualizar apenas as transações de seus objetos de custo permitidos)
2. Selecione Actions > Export Template (Ações > Exportar modelo) para fazer o download de um modelo que pode ser preenchido com seus dados reais. Seu aplicativo Apptio Planning faz o download do modelo de itens de transação no formato.csv.
3. Abra o arquivo.csv baixado.
   - Não renomeie os cabeçalhos das colunas nesse modelo. O aplicativo Apptio Planning requer essa estrutura de dados.
   - Os cabeçalhos de coluna no modelo devem estar em seus arquivos para que a importação seja feita. Os cabeçalhos das colunas podem ser reordenados.
   - Opcionalmente, adicione cabeçalhos de coluna de dimensão personalizados ao modelo (consulte [Adicionar e gerenciar atributos personalizados de dimensões](manage_schema.html "Os esquemas definem a estrutura dos dados no Apptio Planning. Eles especificam as tabelas, os campos e os relacionamentos que determinam como as informações são armazenadas, vinculadas e exibidas nas guias Despesas, como Trabalho, Contratos, Ativos e Finanças.")).
4. Cole os dados reais do mês no modelo, garantindo que você corresponda à estrutura exata mostrada no modelo. Adicione informações sobre o centro de custo e o objeto de custo. Os objetos de custo sem centros de custo não receberão dados reais.
5. Salve o modelo no formato.csv em sua unidade local.

## Importar o arquivo.csv de dados reais

1. No menu de navegação, selecione Gerenciamento de despesas > Transações.
2. Selecione um ano e um mês para receber os dados reais.
3. Selecione Ações e, em seguida, selecione uma das seguintes opções:
   - Import Actuals (Importar dados reais) - Importe um arquivo.csv contendo seus dados reais.
   - Importar de Costing Standard - Importar dados reais de Costing Standard (consulte [Integrar com transparência de custos](integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados.") ).
4. Navegue até o arquivo.csv desejado e clique em Importar.

## Abrir e visualizar os dados reais

1. No menu de navegação, selecione Gerenciamento de despesas e, em seguida, selecione um mês para visualizar
2. Selecione o mês de abertura.

Quando os valores reais são importados, os valores reais e planejados aparecem em dois itens de linha separados na página Resumo ou Ledger. Consulte [Analisar um plano ou previsão](analyze-plan-forecast.html). Observe que:

- Os proprietários do orçamento podem editar atributos de itens de linha de previsão e, ao mesmo tempo, alinhar o real ao planejado. É possível agrupar itens de linha para visualizar valores reais e planejados em um único item de linha e salvar essas configurações em uma visualização usando o recurso Layouts personalizados (consulte [Personalizar, salvar e compartilhar layouts de tabela](customize-save-share.html)).
- Você pode adicionar atributos personalizados à tabela, o que pode ajudar a capturar informações suplementares para aprimorar a análise e os relatórios (consulte [Adicionar e gerenciar atributos personalizados de dimensões](manage_schema.html "Os esquemas definem a estrutura dos dados no Apptio Planning. Eles especificam as tabelas, os campos e os relacionamentos que determinam como as informações são armazenadas, vinculadas e exibidas nas guias Despesas, como Trabalho, Contratos, Ativos e Finanças.")).
- Ao inserir dados em uma tabela, você pode inserir um valor trimestral ou anual e esse valor será distribuído proporcionalmente entre os meses.
- Se a sua organização executa tanto o Planning quanto o Apptio Costing Standard, você pode integrar os dois para compartilhar dados (consulte [Integrar com transparência de custos](integrate-ct.html "Se a sua organização executa o Apptio Costing Standard e um aplicativo Apptio Planning, é possível integrá-los para compartilhar dados.")).
