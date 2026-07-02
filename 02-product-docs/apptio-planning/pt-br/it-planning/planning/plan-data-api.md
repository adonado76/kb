---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "Plan APIs"
breadcrumb:
  - "Planning"
  - "APIs"
  - "Visão geral do planejamento de APIs REST"
source_path: "it-planning/planning/plan-data-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Plan APIs

**As APIs de** planos permitem que você identifique os planos disponíveis e gerencie os dados de despesas por plano por meio de operações de importação e exportação. Essas APIs constituem a base da maioria das integrações de dados de planejamento com o Microsoft Apptio Planning.

Usando as APIs de planos, você pode recuperar identificadores de planos, exportar dados detalhados de despesas em vários tipos de custo e importar dados atualizados dos planos usando arquivos do tipo “ CSV ”. Opções flexíveis de formatação e validação permitem fluxos de trabalho repetíveis, atualizações em massa e integração com sistemas externos.

## ACESSE /planning/api/v1/plans

**Descrição**

Recupera os nomes e os IDs de todos os planos acessíveis ao usuário no ambiente especificado.

**Solicitação**

```
GET https://app.apptio.com/planning/api/v1/plans
```

Observação: Certifique-se de que o endereço URL corresponda à sua região (por exemplo, app-eu.apptio.com, app-au.apptio.com ).

**Cabeçalhos**

|  |  |  |
| --- | --- | --- |
| **Cabeçalho** | **Valor** | **Descrição** |
| apptio-opentoken | <open-token> | Token de autenticação gerado na etapa 2 dos pré-requisitos |
| apptio-ambiente-atual | <environment-id> | Contexto de ambiente necessário da etapa 3 dos pré-requisitos |

**Resposta**

```
[ 
 { 
 "id": "0DD868B85BD445EFBDB9F20066F1C7CA", 
 "name": "FY2025 Budget" 
 }, 
 { 
 "id": "1841D23C513444B19B9F1743C5D90445", 
 "name": "FY2024 Budget Final" 
 }, 
 { 
 "id": "29A92951F2F94A5AB9D9556613A4CA6E", 
 "name": "FY2024 October Forecast" 
 } 
]
```

Retorna um objeto JSON com as seguintes propriedades:

- ***id*** : Identificador único do plano
- ***nome*** : Nome de exibição do plano

## POST /planning/api/v1/plans/< ID do plano >/despesas/exportar

**Descrição**

Exporta os dados de despesas de um plano específico. A exportação é gerada como um arquivo do tipo ` CSV `, com base nos parâmetros fornecidos.

**Solicitação**

```
POST https://app.apptio.com/planning/api/v1/plans/<planId>/expenses/export
```

Observação: use a API GET de planos para obter o ID do plano a ser exportado

**Cabeçalhos**

|  |  |  |
| --- | --- | --- |
| **Cabeçalho** | **Valor** | **Descrição** |
| apptio-opentoken | <open-token> | Token de autenticação gerado na etapa 2 dos pré-requisitos |
| apptio-ambiente-atual | <environment-id> | Contexto de ambiente necessário, conforme a etapa 3 dos pré-requisitos |

**Parâmetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Valores permitidos** | **Necessário** | **Descrição** |
| tipo | Resumo  TRABALHO\_EXISTENTE  TRABALHO\_PLANEJADO  ATIVIDADE LABORAL  Contrato  ASSET\_EXISTING  ASSET\_PLANNED  Outro | TRUE | Tipo de dados do plano a exportar |
| departmentCode | <code> ou em branco | falso | Filtra os resultados por um departamento específico; se deixado em branco, exporta todos os departamentos |
| basePercentage | ONE  CEM | falso | Controla como os valores percentuais são formatados:  - UM – Exporta porcentagens como valores decimais. - CEM – Exibe as porcentagens de exportação como números inteiros.   Valor padrão: UM |
| characterEncoding | UTF\_8 SHIFT\_JIS | falso | Codificação do arquivo de saída Valor padrão: UTF\_8 |
| columnDelimiter | COMMA ponto e vírgula  TAB | falso | CSV delimitador Valor padrão: VÍRGULA |
| dateFormat | Formatos de data compatíveis: aaaa-MM-dd  aaaa/MM/dd  yyyy.MM.dd  dd-mm-aa  dd/mm/aa  yy.MM.dd  dd-m-a  dd/M/a  yy.M.d  mm-dd-aaaa  mm/dd/aaaa  MM.dd.yyyy  dd-mm-aa  dd/MM/aa  MM.dd.yy  m-d-aaaa  M/d/aaaa  M.d.yyyy  dd-mm-aa  M/d/aa  M.d.yy  dd-MM-aaaa  dd/MM/aaaa  dd.MM.yyyy  dd-MM-aa  dd/MM/aa  dd.MM.yy  d-M-aa  d/M/aa  d.M.yy  d-M-aaaa  d/M/aaaa  d.M.yyyy | falso | Formato dos campos de data na saída Valor padrão: aaaa-MM-dd |
| decimalPrecision | ZERO ONE  TWO  THREE  FOUR  Cinco  SEIS  SETE  OITO  QUINZE | falso | Número de casas decimais aplicado aos valores numéricos Valor padrão: QUINZE |
| decimalSymbol | PERÍODO COMMA | falso | Separador decimal Valor padrão: PERIOD |
| laborDisplayType | ETC HORA | falso | Este parâmetro está disponível apenas se o parâmetro de tipo for LABOR\_ACTIVITY  Valor padrão: HORA |
| isForReimport | TRUE falso | falso | Exporta os dados em um formato adequado para reimportação, se definido como TRUE  Valor padrão: FALSE |
| layoutId |  | falso | ID do layout a ser exportado |
| moeda | MOEDA\_ORIGINAL MOEDA\_DA\_EMPRESA | falso | Aplicável apenas quando a função Multimoeda estiver ativada.  - ORIGINAL\_CURRENCY (padrão): Exporta dados financeiros na moeda especificada para cada item de linha. - COMPANY\_CURRENCY: Exporta dados financeiros na moeda padrão da empresa, com os valores convertidos automaticamente quando necessário.   Valor padrão: ORIGINAL\_CURRENCY |

**Resposta**

Um arquivo em formato XML ( CSV ) para download contendo os detalhes das despesas do plano selecionado. A exportação inclui o esquema completo do plano para o tipo de plano selecionado.

É gerado um erro de solicitação inválida ao usar tanto **isForReimport** quanto **layoutId**. Esses dois parâmetros não são compatíveis para serem usados ao mesmo tempo.

## Lançar /planning/api/v1/plans/< ID do plano >/despesas/importar

**Descrição**

Importa dados de despesas de um plano específico usando um arquivo de entrada do tipo “ CSV ”. Retorna uma resposta JSON com detalhes sobre o sucesso ou a falha do upload, o número de departamentos atualizados, as linhas adicionadas, modificadas ou omitidas e quaisquer problemas encontrados durante o upload. A resposta também inclui opções para tentar novamente o upload ignorando os problemas ou para baixar um arquivo de ajuda para análise dos problemas.

**Solicitação**

```
POST https://app.apptio.com/planning/api/v1/plans/<planId>/expenses/import
```

Observação: Certifique-se de que o endereço URL corresponda à sua região (por exemplo, app-eu.apptio.com, app-au.apptio.com ).

**Cabeçalhos**

|  |  |  |
| --- | --- | --- |
| **Cabeçalho** | **Valor** | **Descrição** |
| apptio-opentoken | <open-token> | Token de autenticação gerado na etapa 2 dos pré-requisitos |
| apptio-ambiente-atual | <environment-id> | Contexto de ambiente necessário, conforme a etapa 3 dos pré-requisitos |
| Tipo de Conteúdo | multipart/form-data |  |

**Parâmetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Valores permitidos** | **Necessário** | **Descrição** |
| tipo | Resumo TRABALHO\_EXISTENTE  TRABALHO\_PLANEJADO  ATIVIDADE LABORAL  Contrato  ASSET\_EXISTING  ASSET\_PLANNED  Outro | TRUE | Tipo de dados do plano a importar |
| uploadOperationType | SUBSTITUIR\_TODOS\_OS\_ITENS\_DE\_LINHA UPDATE | TRUE | Tipo de envio de dados:  - A função REPLACE\_ALL\_LINE\_ITEMS exclui todos os dados existentes e os substitui pelos dados do arquivo enviado. - A opção ATUALIZAR atualiza os dados existentes apenas para as linhas com um Código de Item de Linha correspondente. |
| departmentCode | <code> ou em branco | falso | O código do departamento para o qual os dados do plano devem ser importados. Padrão: Deixe em branco para importar dados para todos os departamentos. |
| commitWithIssues | TRUE falso | falso | VERDADEIRO — Carrega o arquivo ` CSV ` mesmo que haja erros. Os detalhes do erro são retornados na resposta. FALSO — Impede que o arquivo de configuração do servidor ( CSV ) seja carregado caso sejam detectados erros.  Padrão: FALSE |
| externalItems | TRUE falso | falso | VERDADEIRO – Importa como itens de linha externos. Padrão: FALSE |
| basePercentage | ONE CEM | falso | Controla como os valores percentuais são formatados:  - UM – Importa porcentagens como valores decimais. - CEM – Importa porcentagens como números inteiros.   Padrão: UM |
| characterEncoding | UTF\_8 SHIFT\_JIS | falso | Codificação do arquivo de entrada Padrão: UTF\_8 |
| columnDelimiter | COMMA ponto e vírgula  TAB | falso | CSV delimitador Padrão: VÍRGULA |
| dateFormat | *Formatos de data compatíveis:* *aaaa-MM-dd*  *aaaa/MM/dd*  *yyyy.MM.dd*  *dd-mm-aa*  *dd/mm/aa*  *yy.MM.dd*  *dd-m-a*  *dd/M/a*  *yy.M.d*  *mm-dd-aaaa*  *mm/dd/aaaa*  *MM.dd.yyyy*  *dd-mm-aa*  *dd/MM/aa*  *MM.dd.yy*  *m-d-aaaa*  *M/d/aaaa*  *M.d.yyyy*  *dd-mm-aa*  *M/d/aa*  *M.d.yy*  *dd-MM-aaaa*  *dd/MM/aaaa*  *dd.MM.yyyy*  *dd-MM-aa*  *dd/MM/aa*  *dd.MM.yy*  *d-M-aa*  *d/M/aa*  *d.M.yy*  *d-M-aaaa*  *d/M/aaaa*  *d.M.yyyy* | falso | Formato dos campos de data no arquivo de importação. Padrão: aaaa-MM-dd |
| decimalPrecision | ZERO ONE  TWO  THREE  FOUR  Cinco  SEIS  SETE  OITO | falso | Número de casas decimais aplicado aos valores numéricos Padrão: OITO |
| decimalSymbol | PERÍODO COMMA | falso | Separador decimal Padrão: PERIOD |

**Corpo**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Valor** | **Necessário** | **Descrição** |
| Arquivo | <arquivo CSV a importar> | TRUE | O arquivo ` CSV ` a ser importado |

**Resposta**

```
{ 
  "committed": false, 
  "totalRows": 157, 
  "modifiedRows": 0, 
  "omittedRows": 157, 
  "additionalRows": 0, 
  "updatedCostObjects": 0, 
  "hasChanges": false, 
  "helpFileKey": "BAD29F5238994EFFBA9DB8204A1B4226", 
  "displayName": "Financials", 
  "status": "CANCELLED", 
  "issues": { 
    "OMIT": [ 
      { 
        "type": "noMatchingCostObjectCostCenterFound", 
        "isIncludedInHelpFile": true, 
        "column": "Cost Object", 
	        "count": 157, 
        "errorMessage": "No values found for Cost Object and Cost Center: Cost Object", 
        "instances": [] 
      }, 
      { 
        "type": "invalidBuildCostType", 
        "isIncludedInHelpFile": true, 
        "column": "Cost Type", 
        "count": 155, 
        "errorMessage": "One or more rows in uploaded lines has invalid Cost Type: Build, please include Project Code to consider Build Cost Type: Cost Type", 
        "instances": [] 
      } 
    ], 
    "ADDITION": [], 
    "MODIFY": [ 
      { 
        "type": " 
        ", 
        "isIncludedInHelpFile": false, 
        "column": "unknownColumn", 
        "count": 112, 
        "errorMessage": "Uploaded file contains one or more unknown columns which will be ignored: unknown column", 
        "instances": [ 
          "Project: Invest Type", 
          "Project: Sponsor BU", 
          "Project: Initiative", 
          "Project: Priority", 
          "Project: Project Owner", 
          "Project: Project Group", 
          "Project: Code", 
          "Project Cost Center", 
          "Project Cost Center: Cost Center Owner", 
          "Project Cost Center: Cost Center Owner Title" 
        ] 
      }, 
      { 
        "type": "invalidPrefix", 
        "isIncludedInHelpFile": true, 
        "column": "Line Item Code", 
        "count": 157, 
        "errorMessage": "Invalid prefix format: Line Item Code", 
        "instances": [ 
          "LAP-156", 
          "LAP-2", 
          "LAP-95", 
          "LAP-133", 
          "LAP-132", 
          "LAP-150", 
          "LAP-115", 
          "LAP-33", 
          "LAP-141", 
          "LAP-6" 
        ] 
      } 
    ], 
    "CANCEL": [] 
  }, 
  "uploadId": "4361C20A391A4DA39AF61DD11655ACC8", 
  "totalIssues": 581, 
  "_links": [ 
    { 
      "href": "https://app.apptio.com/planning/api/v1/plans/C66E072F4E9745D29D541236FD28592A/expenses/import?type=SUMMARY&uploadOperationType=REPLACE_ALL_LINE_ITEMS&commitWithIssues=true&externalItems=false", 
      "rel": "commitWithIssues", 
      "method": "POST", 
      "type": "multipart/form-data" 
    }, 
    { 
      "href": "https://app.apptio.com/planning/api/v1/plans/expenses/import/helpfile/BAD29F5238994EFFBA9DB8204A1B4226?filename=response-exportall-oas.csv", 
      "rel": "downloadHelpFile", 
      "method": "GET", 
      "type": "text/csv" 
    } 
  ]
```

A resposta retorna um objeto JSON com as seguintes propriedades:

**Propriedades do objeto JSON da resposta**

|  |  |  |  |
| --- | --- | --- | --- |
| **Propriedade** | **Tipo** | **Valores** | **Descrição** |
| comprometido | BOOLEAN | TRUE falso | VERDADEIRO - o envio do arquivo foi bem-sucedido. FALSO — o usuário pode continuar o upload usando commitWithIssue=TRUE ou baixar o arquivo de ajuda na seção [Links](#plndataapi__links). |
| totalRows | NUMBER |  | Número total de linhas no arquivo de importação. |
| modifiedRows | NUMBER |  | Número de linhas que serão modificadas após o processamento do upload. Os motivos das modificações nas linhas podem ser encontrados na resposta, na seção issues.MODIFY. |
| omittedRows | NUMBER |  | Número de linhas que serão omitidas após o processamento do upload. Os motivos para a omissão de linhas podem ser encontrados na seção “ issues.OMIT ” da resposta. |
| additionalRows | NUMBER |  | Número de linhas que serão adicionadas assim que o upload for processado. Os motivos para a inclusão de linhas podem ser encontrados na resposta, em issues.ADDITION. |
| updatedDepartments | NUMBER |  | Número de departamentos atualizado. |
| hasChanges | BOOLEAN | TRUE falso | VERDADEIRO – se houver alguma alteração nas partidas individuais após o envio. FALSO caso contrário. |
| helpFileKey | UUID |  | ID exclusivo do arquivo de ajuda que contém problemas relacionados ao upload |
| status | STRING | Concluído CANCELADO | Status do upload |
| issues.OMIT | MATRIZ | [Problemas](#plndataapi__issues) | Detalhes dos problemas que levaram à omissão de linhas. |
| issues.ADDITION | MATRIZ | [Problemas](#plndataapi__issues) | Detalhes dos problemas que levaram à adição de linhas. |
| issues.MODIFY | MATRIZ | [Problemas](#plndataapi__issues) | Detalhes dos problemas que levaram à modificação das linhas. |
| issues.CANCEL | MATRIZ | [Problemas](#plndataapi__issues) | Detalhes dos problemas que causaram o cancelamento do upload. |
| uploadId | UUID |  | ID exclusivo para a ação de importação. |
| totalIssues | NUMBER |  | Número total de edições. |
| \_links | MATRIZ | [Links](#plndataapi__links) | Incluído quando ocorrem erros de importação, fornecendo solicitações de API de acompanhamento para baixar o arquivo de ajuda ou tentar novamente a importação, ignorando os problemas identificados. |

**Problemas**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Tipo** | **Valores** | **Descrição** |
| tipo | STRING | Exemplos de edições: noMatchingCostObjectCostCenterFound  invalidBuildCostType  illegalCostCenterCostObjectMapping  referenceNotFound  missingEmployee  uploadContainsUnknownColumn | Identificador do tipo de erro. |
| isIncludedInHelpFile | BOOLEAN | TRUE falso | VERDADEIRO – Os detalhes do problema estão incluídos no arquivo de ajuda FALSO – Os detalhes do problema não estão incluídos no arquivo de ajuda |
| coluna | STRING |  | O nome da coluna em que o problema foi detectado |
| errorMessage | STRING |  | Detalhes do problema. |
| instâncias | MATRIZ |  | Todas as ocorrências do tipo de erro especificado no arquivo de importação. Exemplo: Se o tipo de problema for “ uploadContainsUnknownColumn, ”, as instâncias listarão todas as colunas desconhecidas encontradas no arquivo de importação. |

**Links**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Tipo** | **Valores** | **Descrição** |
| href | STRING |  | Ponto final do recurso vinculado |
| rel | STRING | commitWithIssues downloadHelpFile | commitWithIssue - acessar o link para enviar o processo e ignorar os problemas detectados downloadHelpFile – link para baixar o arquivo de ajuda com os detalhes dos problemas |
| método | STRING | GET POST  PUT  PATCH  EXCLUIR | HTTP método a ser usado para o link |
| tipo | STRING |  | É necessário um cabeçalho Content-Type para a solicitação |

## ACESSE /planning/api/v1/plans/expenses/import/helpfile/<helpfileid>

**Descrição**

Baixa um arquivo de ajuda com informações detalhadas sobre os problemas encontrados durante o upload.

Observação: Use o objeto ` helpFileId ` obtido na resposta da API de importação

**Solicitação**

```
GET https://app.apptio.com/planning/api/v1/plans/expenses/import/helpfile/<helpfileid>
```

Observação: Certifique-se de que o endereço URL corresponda à sua região (por exemplo, app-eu.apptio.com, app-au.apptio.com ).

**Parâmetros**

|  |  |  |
| --- | --- | --- |
| **Nome** | **Valor** | **Descrição** |
| nome do arquivo | <nome do arquivo dos dados exportados> | Se definido, o nome do arquivo exportado seria filename\_HelpFile.csv. Se não for definido, o nome do arquivo exportado será helpfileid\_HelpFile.csv. |

**Resposta**

Um arquivo ` CSV ` para download que inclui os dados importados do plano e detalhes embutidos sobre os problemas de upload para cada linha afetada.

## POST /planning/api/v1/plans/<planId>/expenses/import/async

**Descrição**

Inicia uma importação assíncrona de dados de despesas para um plano especificado, utilizando um arquivo do tipo “ CSV ”. Retorna uma resposta JSON contendo um UUID exclusivo da solicitação de importação e um link para consultar o status e os resultados da importação.

**Solicitação**

POST [https://app.apptio.com/planning/api/v1/plans/<planId>/expenses/import/async](https://app.apptio.com/planning/api/v1/plans/%3cplanId%3e/expenses/import/async "(Abre em uma nova guia ou janela)")

Observação: Certifique-se de que o endereço URL corresponda à sua região (por exemplo, app-eu.apptio.com, app-au.apptio.com ).

**Cabeçalhos**

|  |  |  |
| --- | --- | --- |
| **Cabeçalho** | **Valor** | **Descrição** |
| apptio-opentoken | <open-token> | Token de autenticação gerado na etapa 2 dos pré-requisitos |
| apptio-ambiente-atual | <environment-id> | Contexto de ambiente necessário, conforme a etapa 3 dos pré-requisitos |
| Tipo de Conteúdo | multipart/form-data |  |

**Parâmetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Valores permitidos** | **Necessário** | **Descrição** |
| tipo | Resumo TRABALHO\_EXISTENTE  TRABALHO\_PLANEJADO  ATIVIDADE LABORAL  Contrato  ASSET\_EXISTING  ASSET\_PLANNED  Outro | TRUE | Tipo de dados do plano a importar |
| uploadOperationType | SUBSTITUIR\_TODOS\_OS\_ITENS\_DE\_LINHA UPDATE | TRUE | Tipo de envio de dados:  - A função REPLACE\_ALL\_LINE\_ITEMS exclui todos os dados existentes e os substitui pelos dados do arquivo enviado. - A opção ATUALIZAR atualiza os dados existentes apenas para as linhas com um Código de Item de Linha correspondente. |
| departmentCode | <code> ou em branco | falso | O código do departamento para o qual os dados do plano devem ser importados. Padrão: Deixe em branco para importar dados para todos os departamentos. |
| commitWithIssues | TRUE falso | falso | VERDADEIRO — Carrega o arquivo ` CSV ` mesmo que haja erros. Os detalhes do erro são retornados na resposta. FALSO — Impede que o arquivo de configuração do servidor ( CSV ) seja carregado caso sejam detectados erros.  Padrão: FALSE |
| externalItems | TRUE falso | falso | VERDADEIRO – Importa como itens de linha externos. Padrão: FALSE |
| basePercentage | ONE CEM | falso | Controla como os valores percentuais são formatados:  - UM – Importa porcentagens como valores decimais. - CEM – Importa porcentagens como números inteiros.   Padrão: UM |
| characterEncoding | UTF\_8 SHIFT\_JIS | falso | Codificação do arquivo de entrada Padrão: UTF\_8 |
| columnDelimiter | COMMA ponto e vírgula  TAB | falso | CSV delimitador Padrão: VÍRGULA |
| dateFormat | *Formatos de data compatíveis:* *aaaa-MM-dd*  *aaaa/MM/dd*  *yyyy.MM.dd*  *dd-mm-aa*  *dd/mm/aa*  *yy.MM.dd*  *dd-m-a*  *dd/M/a*  *yy.M.d*  *mm-dd-aaaa*  *mm/dd/aaaa*  *MM.dd.yyyy*  *dd-mm-aa*  *dd/MM/aa*  *MM.dd.yy*  *m-d-aaaa*  *M/d/aaaa*  *M.d.yyyy*  *dd-mm-aa*  *M/d/aa*  *M.d.yy*  *dd-MM-aaaa*  *dd/MM/aaaa*  *dd.MM.yyyy*  *dd-MM-aa*  *dd/MM/aa*  *dd.MM.yy*  *d-M-aa*  *d/M/aa*  *d.M.yy*  *d-M-aaaa*  *d/M/aaaa*  *d.M.yyyy* | falso | Formato dos campos de data no arquivo de importação. Padrão: aaaa-MM-dd |
| decimalPrecision | ZERO  ONE  TWO  THREE  FOUR  Cinco  SEIS  SETE  OITO | falso | Número de casas decimais aplicado aos valores numéricos Padrão: OITO |
| decimalSymbol | PERÍODO COMMA | falso | Separador decimal Padrão: PERIOD |

**Corpo**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Valor** | **Necessário** | **Descrição** |
| Arquivo | <arquivo CSV a importar> | TRUE | O arquivo ` CSV ` a ser importado |

**Resposta**

```
{ 
      "importId": "11F160D23B68D2A697BDD658E768322C", 
      "_link": 
      { 
            "href":"https://app.apptio.com/planning/api/v1/plans/expenses/import/async/11F160D23B68D2A697BDD658E768322C", 
            "rel": "getStatus", "method": "GET", "type": "application/json"
      } 
}
```

**Propriedades do objeto JSON da resposta**

|  |  |  |  |
| --- | --- | --- | --- |
| **Propriedade** | **Tipo** | **Valores** | **Descrição** |
| importId | UUID |  | Identificador único gerado para a solicitação de importação. |
| \_link |  | [:NONE.](#plndataapi__asynclink) | URL para consultar o status e o resultado da solicitação de importação. |

**Links**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Tipo** | **Valores** | **Descrição** |
| href | STRING |  | URL do recurso vinculado. do recurso vinculado |
| rel | STRING | getStatus | Define o tipo de relação do link. Indica que este link é usado para consultar o status e o resultado da importação. |
| método | STRING | GET POST  PUT  PATCH  EXCLUIR | HTTP método a ser utilizado ao acessar o link. |
| tipo | STRING |  | Cabeçalho Content-Type esperado para a solicitação. |

**Erros**

|  |  |  |
| --- | --- | --- |
| 400 | Solicitação inválida | Falta um parâmetro obrigatório, ou já há uma importação em andamento para o plano especificado. |
| 403 | Desautorizado | O usuário não está autorizado a realizar esta operação. |
| 404 | Não localizadas | Não foi encontrado nenhum plano ou departamento para o ID do plano fornecido. |

## ACESSE /planning/api/v1/plans/expenses/import/async/<importId>

**Descrição**

Recupera o status atual de uma solicitação de importação. Se a importação tiver atingido um estado final ( **SUCCESS**, **WARNING** ou **FAIL** ), a resposta também inclui os resultados da importação e quaisquer detalhes associados.

**Solicitação**

[https://app.apptio.com/planning/api/v1/plans/expenses/import/async/%3CimportId%3E](https://app.apptio.com/planning/api/v1/plans/expenses/import/async/%3CimportId%3E "(Abre em uma nova guia ou janela)")

Observação: Certifique-se de que o endereço URL corresponda à sua região (por exemplo, app-eu.apptio.com, app-au.apptio.com ).

**Cabeçalhos**

|  |  |  |
| --- | --- | --- |
| **Cabeçalho** | **Valor** | **Descrição** |
| apptio-opentoken | <open-token> | Token de autenticação gerado na etapa 2 dos pré-requisitos |
| apptio-ambiente-atual | <environment-id> | Contexto de ambiente necessário, conforme a etapa 3 dos pré-requisitos |
| Tipo de Conteúdo | multipart/form-data |  |

**Resposta**

```
{
  "importId": "11F160D23B68D2A697BDD658E768322C",
  "status": "FAIL",
  "result": {
    "committed": false,
    "totalRows": 2,
    "modifiedRows": 0,
    "omittedRows": 2,
    "additionalRows": 0,
    "updatedDepartments": 0,
    "hasChanges": false,
    "helpFileKey": "E7915BDAF037483994D6FABD7564E174",
    "status": "CANCELLED",
    "issues": {
      "OMIT": [
        {
          "type": "noMatchingCostObjectCostCenterFound",
          "isIncludedInHelpFile": true,
          "column": "Cost Object",
          "count": 2,
          "errorMessage": "No values found for Cost Object and Cost Center: Cost Object",
          "instances": []
        }
      ],
      "ADDITION": [],
      "MODIFY": [
        {
          "type": "uploadContainsUnknownColumn",
          "isIncludedInHelpFile": false,
          "column": "unknownColumn",
          "count": 16,
          "errorMessage": "Uploaded file contains one or more unknown columns which will be ignored: unknown column",
          "instances": [
            "Event ID",
            "Timestamp",
            "User ID",
            "Event Type",
            "Container ID",
            "Area",
            "Container",
            "Item ID",
            "Item Type",
            "Item"
          ]
        }
      ],
      "CANCEL": []
    },
    "uploadId": "14B68FF8F91E412185D04B1CD52BA323",
    "totalIssues": 18
    "_links": [ { "href": "https://app.apptio.com/planning/api/v1/plans/E581EDF2752C434AAF62A63DF4F4B777/expenses/import/async?commitWithIssues=true&basePercentage=ONE&characterEncoding=UTF_8&columnDelimiter=COMMA&dateFormat=yyyy-MM-dd&decimalPrecision=EIGHT&decimalSymbol=PERIOD&type=SUMMARY&departmentCode=AllDept_6DC740A85A9C11E69E6CCC52AF3F6215&externalItems=false&uploadOperationType=UPDATE", 
    "rel": "commitWithIssues", 
    "method": "POST", 
    "type": "multipart/form-data" 
    }, 
    { 
        "href":"https://app.apptio.com/planning/api/v1/plans/expenses/import/helpfile/E7915BDAF037483994D6FABD7564E174?filename=response-export-filter.csv", 
        "rel": "downloadHelpFile", 
        "method": "GET", 
        "type": "text/csv" 
        } 
     ] 
  } 
}
```

**Propriedades do objeto JSON da resposta**

|  |  |  |  |
| --- | --- | --- | --- |
| **Propriedade** | **Tipo** | **Valores** | **Descrição** |
| importId | UUID |  | Identificador único gerado para a solicitação de importação. |
| status | STRING | ENFILEIRADO EM EXECUÇÃO  SUCESSO  AVISO  Falha | Status atual da solicitação de importação. |
| Resultado | Objeto JSON | [Resposta da API do Plano](#plndataapi__importjson) | Contém o resultado da importação quando a solicitação atinge um status final (SUCCESS, WARNING ou FAIL). Retorna null enquanto a solicitação ainda estiver em andamento (QUEUED ou RUNNING). |

**Erros**

|  |  |  |
| --- | --- | --- |
| 403 | Desautorizado | O usuário não está autorizado a acessar a importação solicitada. |
| 404 | Não localizadas | Não foi encontrada nenhuma solicitação de importação com o ID <importId> para o usuário <user>. |

**Tópico principal:** [Visão geral do planejamento de APIs REST](../../it-planning/planning/plan-api.html "As APIs REST do Planning do Apptio oferecem acesso programático e seguro a planos, dados de planejamento, metadados e artefatos relacionados no Planning d Apptio. Essas APIs foram projetadas para oferecer suporte à automação e às integrações de sistemas em casos de uso relacionados a planejamento, previsão, análise, governança e troca de dados.")
