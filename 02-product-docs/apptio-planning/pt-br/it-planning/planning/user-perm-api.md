---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "APIs de permissões de usuário"
breadcrumb:
  - "Planning"
  - "APIs"
  - "Visão geral do planejamento de APIs REST"
source_path: "it-planning/planning/user-perm-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# APIs de permissões de usuário

**As APIs de permissões do** usuário permitem a exportação e a importação de dados de permissões globais e no nível do plano. Essas APIs oferecem suporte ao gerenciamento automatizado de acesso e à validação de permissões de usuário no Apptio Planning.

Usando essas APIs, você pode gerenciar permissões em massa por meio de arquivos do tipo ` CSV `, revisar as configurações de acesso existentes e solucionar problemas relacionados a permissões usando arquivos de ajuda detalhados gerados durante as operações de importação.

## POST planning/api/v1/userpermissions/export

**Descrição**

Exporta os dados de permissões de usuário no nível do plano. A exportação é gerada como um arquivo do tipo ` CSV `, com base nos parâmetros fornecidos.

**Solicitação**

```
POST https://app.apptio.com/planning/api/v1/userpermissions/export
```

Observação: Certifique-se de que o endereço URL corresponda à sua região (por exemplo, app-eu.apptio.com, app-au.apptio.com ). Use a API GET de planos para obter o ID do plano a ser exportado.

**Parâmetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Valores permitidos** | **Necessário** | **Descrição** |
| planId | planID da resposta da API do GET Plans | falso | O ID do plano cujas permissões de usuário devem ser exportadas. Se não for especificado, a exportação incluirá permissões globais de dados de referência. |
| basePercentage | ONE CEM | falso | Formato no qual a porcentagem deve ser exibida. Padrão: UM |
| characterEncoding | UTF\_8 SHIFT\_JIS | falso | Codificação do arquivo de entrada Padrão: UTF\_8 |
| columnDelimiter | COMMA ponto e vírgula  TAB | falso | CSV delimitador Padrão: VÍRGULA |
| dateFormat | *Formatos de data compatíveis:* *aaaa-MM-dd*  *aaaa/MM/dd*  *yyyy.MM.dd*  *dd-mm-aa*  *dd/mm/aa*  *yy.MM.dd*  *dd-m-a*  *dd/M/a*  *yy.M.d*  *mm-dd-aaaa*  *mm/dd/aaaa*  *MM.dd.yyyy*  *dd-mm-aa*  *dd/MM/aa*  *MM.dd.yy*  *m-d-aaaa*  *M/d/aaaa*  *M.d.yyyy*  *dd-mm-aa*  *M/d/aa*  *M.d.yy*  *dd-MM-aaaa*  *dd/MM/aaaa*  *dd.MM.yyyy*  *dd-MM-aa*  *dd/MM/aa*  *dd.MM.yy*  *d-M-aa*  *d/M/aa*  *d.M.yy*  *d-M-aaaa*  *d/M/aaaa*  *d.M.yyyy* | falso | Formato dos campos de data no arquivo de importação. Padrão: aaaa-MM-dd |
| decimalPrecision | ZERO ONE  TWO  THREE  FOUR  Cinco  SEIS  SETE  OITO | falso | Número de casas decimais aplicado aos valores numéricos Padrão: OITO |
| decimalSymbol | PERÍODO COMMA | falso | Separador decimal Padrão: PERIOD |

**Resposta**

Um arquivo do tipo “ CSV ” para download contendo os detalhes da análise de variação do plano selecionado.

## POST /planning/api/v1/userpermissions/import

**Descrição**

Importa permissões de usuário no nível do plano ou permissões globais de objeto de custo.

**Solicitação**

```
POST https://app.apptio.com/planning/api/v1/userpermissions/import
```

Observação: Certifique-se de que o endereço URL corresponda à sua região (por exemplo, app-eu.apptio.com, app-au.apptio.com ). Use a API GET de planos para obter o ID do plano a ser exportado.

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
| planId | planID da resposta da API do GET Plans | falso | O ID do plano cujas permissões de usuário devem ser importadas. Se não for especificado, importar as permissões globais de dados de referência. |
| commitWithIssues | TRUE falso | falso | VERDADEIRO — Carrega o arquivo ` CSV ` mesmo que haja erros. Os detalhes do erro são retornados na resposta. FALSO — Impede que o arquivo de configuração do servidor ( CSV ) seja carregado caso sejam detectados erros.  Padrão: FALSE |
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
"totalRows": 0, 
"modifiedRows": 0, 
"omittedRows": 0, 
"additionalRows": 0, 
"updatedDepartments": -1, 
"hasChanges": false, 
"helpFileKey": null, 
"status": "CANCELLED", 
"issues": { 
"OMIT": [], 
"ADDITION": [], 
"MODIFY": [ {
"type": "uploadContainsUnknownColumn",
"isIncludedInHelpFile": false, 
"column": "unknownColumn", 
"count": 35, 
"errorMessage": "Uploaded file contains one or more unknown columns which will be ignored: unknown column", 
"instances": [ "Account", "Cost Center", "Project Code", "Cost Type", "Location", "Location Name", "Vendor", "Vendor Name", "Description", "Transaction ID"] 
} ], 
"CANCEL": [] }, 
"uploadId": "F74974DEB2974B7E94D3351C73CACD80", 
"totalIssues": 35, 
"_links": [ {
"href":"http://app.apptio.com/planning/api/v1/userpermissionsimportcommitWithIssues=true&planId=D7BAC53A969D49EE836DB41D51EB746&basePercentage=ONE&columnDelimiter=COMMA&dateFormat=yyy-MM-dd", 
"rel": "commitWithIssues", 
"method": "POST", 
"type": "multipart/form-data" 
} ] 
}
```

**Propriedades do objeto JSON da resposta**

|  |  |  |  |
| --- | --- | --- | --- |
| **Propriedade** | **Tipo** | **Valores** | **Descrição** |
| comprometido | BOOLEAN | TRUE falso | VERDADEIRO - o envio do arquivo foi bem-sucedido. FALSO — o usuário pode continuar o upload usando commitWithIssue=TRUE ou baixar o arquivo de ajuda nos links anexados. |
| totalRows | NUMBER |  | Número total de linhas no arquivo de importação. |
| modifiedRows | NUMBER |  | Número de linhas que serão modificadas após o processamento do upload. Os motivos das alterações nas linhas podem ser encontrados na resposta em issues.MODIFY. |
| omittedRows | NUMBER |  | Número de linhas que serão omitidas após o processamento do upload. As razões para a omissão de linhas podem ser encontradas na resposta em issues.OMIT. |
| additionalRows | NUMBER |  | Número de linhas que serão adicionadas assim que o upload for processado. Os motivos para a inclusão de linhas podem ser encontrados na resposta, em issues.ADDITION. |
| hasChanges | BOOLEAN | TRUE falso | VERDADEIRO – se houver alguma alteração nas partidas individuais após o envio.  FALSO caso contrário. |
| helpFileKey | UUID |  | ID exclusivo do arquivo de ajuda que contém problemas relacionados ao upload |
| status | STRING | Concluído CANCELADO | Status do upload |
| issues.OMIT | MATRIZ | [Problemas](#upapi__upimpli) | Detalhes dos problemas que levaram à omissão de linhas. |
| issues.ADDITION | MATRIZ | [Problemas](#upapi__upimpli) | Detalhes dos problemas que levaram à adição de linhas. |
| issues.MODIFY | MATRIZ | [Problemas](#upapi__upimpli) | Detalhes dos problemas que levaram à modificação das linhas. |
| issues.CANCEL | MATRIZ | [Problemas](#upapi__upimpli) | Detalhes dos problemas que causaram o cancelamento do upload. |
| uploadId | UUID |  | ID exclusivo para a ação de importação. |
| totalIssues | NUMBER |  | Número total de edições. |
| \_links | MATRIZ | [Links](#upapi__issues) | Incluído quando ocorrem erros de importação, fornecendo solicitações de API de acompanhamento para baixar o arquivo de ajuda ou tentar novamente a importação, ignorando os problemas identificados. |

**Problemas**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Tipo** | **Valores** | **Descrição** |
| tipo | STRING | *Exemplos de edições:* *noMatchingCostObjectCostCenterFound*  *invalidBuildCostType*  *illegalCostCenterCostObjectMappingreferenceNotFound*  *missingEmployee*  *UploadContainsUnknownColumn* | Identificador do tipo de erro. |
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

## ACESSE /planning/api/v1/userpermissions/import/helpfile/<helpfileId>

**Descrição**

Baixa um arquivo de ajuda com informações detalhadas sobre os problemas encontrados durante o envio das permissões.

Observação: Use o objeto ` helpFileId ` obtido na resposta da API de importação

**Solicitação**

```
https://app.apptio.com/planning/api/v1/userpermissions/import/helpfile/%3ChelpfileId
```

Observação: Certifique-se de que o endereço URL corresponda à sua região (por exemplo, app-eu.apptio.com, app-au.apptio.com ).

**Parâmetros**

|  |  |  |
| --- | --- | --- |
| **Nome** | **Valor** | **Descrição** |
| nome do arquivo | <nome do arquivo dos dados exportados> | Se definido, o nome do arquivo exportado seria filename\_HelpFile.csv.  Se não for definido, o nome do arquivo exportado será helpfileid\_HelpFile.csv. |

**Resposta**

Um arquivo ` CSV ` para download que inclui dados de importação de permissões de usuário e detalhes embutidos sobre problemas de upload para cada linha afetada.

**Tópico principal:** [Visão geral do planejamento de APIs REST](../../it-planning/planning/plan-api.html "As APIs REST do Planning do Apptio oferecem acesso programático e seguro a planos, dados de planejamento, metadados e artefatos relacionados no Planning d Apptio. Essas APIs foram projetadas para oferecer suporte à automação e às integrações de sistemas em casos de uso relacionados a planejamento, previsão, análise, governança e troca de dados.")
