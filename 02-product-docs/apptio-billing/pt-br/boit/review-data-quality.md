---
source_system: "apptio-billing"
practice: "tbm"
language: "pt-br"
doc_type: "boit"
title: "Revisar a qualidade dos dados"
breadcrumb: []
source_path: "boit/review-data-quality.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Revisar a qualidade dos dados

Dados de qualidade são importantes quando você envia às unidades de negócios um resumo dos serviços que elas utilizaram. Billing Standard vem com um conjunto de relatórios de qualidade de dados que você deve revisar regularmente para garantir que seus dados sejam precisos.

Para acessar os relatórios de Qualidade de dados de faturamento:

1. No menu **Aplicativo**, clique em **Billing Standard** (consulte [o menu Billing Standard](getting_started/boit-menu.html)  ).
2. No menu **de coleta de relatórios**, clique em **Billing Data Quality (Qualidade dos dados de faturamento** ).
3. Na barra na parte superior da página, selecione um relatório na coleção. As opções de relatório incluem:
   - Relatório de resumo de configuração
   - Relatório de atualização de dados
   - Relatórios de qualidade de dados
     - Relatório de qualidade do consumo de ração
     - Relatório de qualidade da biblioteca de serviços
     - Relatório de qualidade do modelo

**Relatório de resumo de configuração**

O relatório **Resumo da configuração** inclui métricas importantes para a qualidade dos dados.

**Relatório de atualização de dados**

O relatório Data Freshness exibe informações sobre as tabelas de dados que foram carregadas no.

As regras de atualização de dados são definidas quando você carrega uma tabela no aplicativo pela primeira vez. Você pode escolher entre uma variedade de opções. As regras de atualização de dados são usadas para determinar se os dados foram atualizados dentro do período de tempo especificado. Eles não programam nem realizam uploads de dados. Para obter uma descrição das opções, consulte "Ciclos de atualização de dados" em [Carregar um arquivo de dados](../studio/data_studio/upload-data-file.html "Aplica-se a: TBM Studio 12.0 e posterior. O TBM Studio aceita dados de arquivos simples nos formatos separados por vírgula, tabulação, pipe, til, dois pontos e ponto e vírgula. Antes de fazer upload de dados, você deve criar uma tabela na qual os dados serão carregados, caso ela ainda não exista.").

**Relatórios de qualidade de dados**

Os relatórios de qualidade de dados (Qualidade do feed de consumo, Qualidade da biblioteca de serviços e Qualidade do modelo) exibem informações sobre a qualidade dos dados no aplicativo.

Embora a qualidade dos dados possa variar, você deve buscar dados que estejam em conformidade com as seguintes diretrizes.

- **Qualidade da alimentação do consumo** :
  - A contagem de linhas deve estar dentro do intervalo esperado. Quaisquer mudanças significativas devem ser explicáveis.
  - A unidade de medida deve corresponder ao serviço.
- **Atualização de dados** - Os dados devem ter sido atualizados com base nos uploads programados.
- **Qualidade do modelo** - A alteração na conta maior deve ser relativamente pequena e as cobranças não alocadas devem estar dentro de limites aceitáveis com base nas alocações definidas no modelo.
- **Distribuição** - Os destinatários adequados da fatura devem ser definidos.

**Relatório de qualidade do consumo de ração**

O relatório Consumption Feed Quality exibe informações sobre contagens de registros, unidades de medida e campos publicados para cada tabela de dados-chave no aplicativo.

**Relatório de qualidade da biblioteca de serviços**

O relatório Qualidade da biblioteca de serviços exibe informações detalhadas de relacionamento e registro sobre as entradas da biblioteca de serviços.

**Validar relações de ID de serviço**

Use a seção superior do relatório para verificar se os relacionamentos são válidos. Use a guia **ID do serviço** para verificar se cada ID do serviço é exclusiva.

**Garantir que os nomes dos serviços sejam exclusivos**

Use a guia **Nome do serviço** para verificar se cada combinação de Nome do serviço/Oferta de serviço é exclusiva.

Se houver duplicatas, o número de duplicatas será exibido na coluna **Total Error Count (Contagem total de erros** ).

**Verificar detalhes do registro**

Use a seção inferior do relatório para verificar se há valores em branco nas entradas da Biblioteca de serviços. Você pode filtrar a tabela por campos obrigatórios e opcionais.

**Relatório de qualidade do modelo**

O relatório Model Quality (Qualidade do modelo) exibe informações sobre as alocações do modelo nas seções **Allocation Overview/Allocation Details (Visão geral da alocação/Detalhes** da alocação) e **Configured Allocations (Alocações configuradas** ) e a variação mês a mês das ofertas de serviço na seção **Variance (Variação** ). Você pode filtrar o relatório para cada uma das métricas do modelo: Cobrança, Unidades faturáveis, Custo, Orçamento, Previsão, Orçamento comercial, Previsão comercial e Unidades faturáveis planejadas. O conteúdo do relatório varia de acordo com a métrica selecionada.

**Revisar detalhes da alocação**

O que procurar:

- As alocações devem ser relativamente consistentes ao longo do tempo.
- Determine a causa de quaisquer variações significativas de alocação examinando a tabela Alocação por objeto e pesquisando os Detalhes de alocação de um objeto.

**Variação de revisão**

O que procurar:

- As variações devem ser consistentes e estar dentro de uma faixa aceitável.
- Investigue quaisquer valores discrepantes.
