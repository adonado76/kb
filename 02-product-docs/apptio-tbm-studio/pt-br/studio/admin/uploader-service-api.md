---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "API do Serviço de Upload"
breadcrumb:
  - "TBM Studio"
  - "Guias práticos (baseados em tarefas)"
  - "Integrar e ampliar"
  - "Integração de API"
source_path: "studio/admin/uploader-service-api.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# API do Serviço de Upload

**Aplica-se a** : TBM Studio 12.0 e posterior

O Apptio Uploader Service (ULS) é um novo veículo para o upload de dados em projetos Apptio. O ULS aprimora o processo [da API Apptio](the-apptio-api.html "Aplica-se a: TBM Studio 12.0 e posterior") existente, oferecendo suporte a uploads de arquivos maiores e adicionando os seguintes recursos:

- Arquivos grandes individuais são carregados como várias partes.
- Os uploads podem ser cancelados.
- O status de um upload de várias partes está incluído na etapa final de incorporação.
- Vários uploads podem ser registrados como um único grupo no projeto Apptio de destino.
- Há suporte para o upload paralelo de várias peças.
- Há suporte para o processamento assíncrono de dados no projeto Apptio.
- Todo o transporte de dados é feito na região e está em conformidade com as leis de localização de dados.

Para obter um exemplo de implementação, consulte o [Tutorial da API do Uploader Service](https://community.apptio.com/viewdocument/uploader-service-api-tutorial "(Abre em uma nova guia ou janela)").

## Pontos de extremidade do Uploader Service

Para acessar o ULS, use um dos seguintes endereços UrLs,, dependendo da região em que o upload estiver ocorrendo

- América do Norte - [https://datalink.apptio.com/uls](https://datalink.apptio.com/uls "(Abre em uma nova guia ou janela)")
- UE - [https://datalink-eu.apptio.com/uls](https://datalink-eu.apptio.com/uls "(Abre em uma nova guia ou janela)")
- APAC - [https://datalink-au.apptio.com/uls](https://datalink-au.apptio.com/uls "(Abre em uma nova guia ou janela)")
- Oriente Médio - [https://datalink-me.apptio.com/uls](https://datalink-me.apptio.com/uls "(Abre em uma nova guia ou janela)")

## Sintaxe da API REST

A base URL para chamadas de API é a seguinte:

`<ULS_URL>/api/<VERSION>`

Atualmente, há um valor válido para **VERSION** : v1. Por exemplo, na América do Norte, a base URL seria: https://datalink.apptio.com/uls/v1. Os pontos de extremidade da API consomem e produzem JSON, exceto quando indicado de outra forma.

## Autenticação com Apptio opentoken

Para se autenticar, você deve primeiro obter um apptio-opentoken.

1. Acesse [Enhanced Access Administration APIs](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas?topic=apis-about-enhanced-access-administration-api "(Abre em uma nova guia ou janela)") para recuperar um Apptio opentoken.
2. Depois de obter o token, adicione os seguintes cabeçalhos à sua solicitação:

| Nome do cabeçalho | Conteúdo |
| --- | --- |
| tipo de aplicativo | "UploaderService" |
| versão do aplicativo | "1.00.0" |
| aplicação-opentoken | Um opentoken válido que representa o usuário conectado |
| ambiente atual do aplicativo | O ambiente FrontDoor para o qual essa solicitação está sendo feita |

## APIs REST

As APIs suportam as seguintes operações:

- upload de uma única parte
- upload de várias partes
- processamento de upload
- obter status de processamento

## Iniciar um upload de uma única parte

**Método** : `POST <ULS_URL>/v1/upload?partSize=<long>`

**Content-type** : multipart/form-data

**Corpo** :

Para formar o corpo de uma única peça, as seguintes peças precisam estar presentes:

```
"metadata": ( { "name": "<TABLE_NAME>" } )
"data": ()
```

**Códigos de retorno:**

200 - Sucesso

400 - Corpo JSON ruim

404 - API incorreta URL

415 - Tipo de mídia não suportado

500 - Erro interno de upload (entre em contato com o suporte)

**Resposta** :

N/A

## Iniciar um upload de várias partes

**Método** : `POST <ULS_URL>/v1/upload/multipart`

**Content-type** : application/json

**Corpo** :

```
{
	"name":"<TABLE_NAME>"
}
```

**Códigos de retorno:**

200 - Sucesso

400 - Corpo JSON ruim

404 - API incorreta URL

500 - Erro interno de upload (entre em contato com o suporte)

**Resposta (JSON)** :

```
{
	"uploadId":""<UPLOAD_ID>", 
	"multipartId":"<MULTIPART_ID>"
}
```

## Carregamento de peças

**Método** : `PUT
<ULS_URL>/v1/upload/multipart/<UPLOAD_ID>/part/<PART_ID>?lastPart=<Bool>&md5=<String>&partSize=<long>`

**Parâmetros** :

| Nome | Tipo | Descrição |
| --- | --- | --- |
| partId | Número Inteiro | Um número de sequência, por exemplo, 1, 2 ou 3 |
| lastPart | Booleano | **verdadeiro** : Esta é a última parte. O comprimento do fluxo de entrada da última parte pode ser menor que 5MB. **falso** : Não a última parte. O comprimento do fluxo de entrada que não é a última parte não pode ser menor que 5MB. |
| md5 | Sequência | O base64-encoded MD5 digest de 128 bits dos dados da peça |
| partSize | longo | O comprimento do fluxo de entrada em bytes. |

**Tipo de conteúdo** : Dependendo do tipo do fluxo do corpo, os seguintes tipos são suportados:

texto/simples

aplicativo/json

aplicativo/zip

aplicação/octeto-stream

**Corpo** :

O fluxo de entrada no corpo.

**Códigos de retorno** :

200 - Sucesso

204 - Sucesso

400 - Tamanho de peça inválido (deve estar entre 5MB e 5GB )

404 - API incorreta URL ou ID de upload incorreto

500 - Erro interno de upload (entre em contato com o suporte)

**Resposta (JSON)** :

Erros, se houver.

## Finalizar um upload de várias partes

**Método** : `POST
<ULS_URL>/v1/upload/multipart/<UPLOAD_ID>`

**Códigos de retorno** :

200 - Sucesso

404 - API incorreta URL

500 - Erro interno de upload (entre em contato com o suporte)

**Resposta (JSON** ):

Erros, se houver.

## Abortar um upload de várias partes

**Método** : `DELETE
<ULS_URL>/v1/upload/multipart/<UPLOAD_ID>`

**Códigos de retorno** :

200 - Sucesso

404 - API incorreta URL

500 - Erro interno de upload (entre em contato com o suporte)

**Resposta (JSON)** :

Erros, se houver.

## Iniciar o processamento final de um upload

**Método** :

```
POST <ULS_URL>/v1/process
```

**Content-type** : application/json

**Corpo** :

Os processos com upload ou uploads únicos têm os mesmos metadados:

```
{
	"metadata": {
		"period": "<Apptio time period e.g. Jan:FY2018>",
		"domain": "<Customer domain e.g. customer.apptio.com>",
		"name": "<File name e.g. file.tsv, file.zip, etc.>",
		"host": "<Apptio host name>",
		"format": "<File format e.g. tsv, csv, etc.>",
		"project": "<Project Name>",
		"source": "<Data source e.g. S3>",
		"category": "<Optional category name>",
		"branch": "<Optional branch name>",
		"overwrite": "<true or false to append>",
		"autoCheckin":"<true of false to check in BIIT>"
	},
	"uploadIds": [
		"<UPLOAD ID>"
	]
}
```

Para vários uploads com metadados diferentes:

```
{
	"metadata": {
		"period": "<Apptio time period e.g. Jan:FY2018>",
		"domain": "<Customer domain e.g. customer.apptio.com>",
		"name": "<File name e.g. file.tsv, file.zip, etc.>",
		"host": "<Apptio host name>",
		"format": "<File format e.g. tsv, csv, etc.>",
		"project": "<Project Name>",
		"source": "<Data source e.g. S3>",
		"category": "<Optional category name>",
		"branch": "<Optional branch name>",
		"overwrite": "<true or false to append>"
		"autoCheckin": "<true of false to check in BIIT>"
	},
	"uploadIds": [
		"<UPLOAD_ID1>",
		"<UPLOAD_ID2>"
	],
	"uploadTargetMapping": {
		"<UPLOAD_ID1>": {
			"period": "<Apptio time period e.g. Jan:FY2018>",
			"domain": "<Customer domain e.g. customer.apptio.com>",
			"name": "<File name e.g. file.tsv, file.zip, etc.>",
			"host": "<Apptio host name>",
			"format": "<File format e.g. tsv, csv, etc.>",
			"project": "<Project Name>",
			"source": "<Data source e.g. S3>",
			"category": "<Optional category name>",
			"branch": "<Optional branch name>",
			"overwrite": "<true or false to append>"g
			"autoCheckin": "<true of false to check in BIIT>"
		},
		"<UPLOAD_ID1>": {
			"period": "<Apptio time period e.g. Jan:FY2018>",
			"domain": "<Customer domain e.g. customer.apptio.com>",
			"name": "<File name e.g. file.tsv, file.zip, etc.>",
			"host": "<Apptio host name>",
			"format": "<File format e.g. tsv, csv, etc.>",
			"project": "<Project Name>",
			"source": "<Data source e.g. S3>",
			"category": "<Optional category name>",
			"branch": "<Optional branch name>",
			"overwrite": "<true or false to append>"
			"autoCheckin": "<true of false to check in BIIT>"
		}
	}
}
```

Observação: o host/domain/project/autoCheckin precisa ser fornecido para todos os metadados dentro e fora do uploadTargetMapping, e eles devem ser consistentes, caso contrário, a API lançará 400 bad request.

**Códigos de retorno** :

200 - Sucesso

400 - Solicitação incorreta

404 - API incorreta URL

500 - Erro interno de upload (entre em contato com o suporte)

**Resposta (JSON)** :

```
{
	"processId": "<PROCESS_ID>"
}
```

Ou erros, se houver.

## Obter o status de uma solicitação de processamento

Isso pode ser executado em qualquer ponto durante a fase de upload ou processamento.

**Método** : `GET <ULS_URL>/v1/status/<PROCESS_ID>`

**Códigos de retorno** :

200 - Sucesso

404 - API incorreta URL

500 - Erro interno de upload (entre em contato com o suporte)

**Resposta (JSON)** :

```
{
	"statuses": [
		{
			  "processId": "<PROCESS_ID>",
			  ...,
			  "statusMap": {
				   "<status map ID>": {
					    "statusCode": "<Status e.g. NotStarted, Finished, etc.>",
					    "errorCode": “<Error if any>”,
					    "detail": “<Details>”,
					    "tableName": "<Table name>",
					    "lastModified": "<Last modified date>"
				    }
			   }
		}
	]
}
```

Ou erros, se houver.

## Sessão em grupo statusCode

| **statusCode** | **Descrição** |
| --- | --- |
| Nulo | statusCode é nulo se não for uma sessão de grupo (se houver apenas um uploadId nos metadados do processo, então não é uma sessão de grupo) |
| Sucesso | A sessão de grupo é bem-sucedida |
| InProcess | A sessão de grupo está em andamento |
| IncompleteGroupSession | Se um upload em blocos falhar na sessão do grupo, o status do grupo será IncompleteGroupSession |
| FailedGroupCheckin | Se a chamada de sessão de grupo final falhar (a falha ocorre durante o check-in do grupo), o status do grupo será FailedGroupCheckin |

## Sessão individual statusCode

| **statusCode** | **Descrição** |
| --- | --- |
| NotStarted | Sessão não iniciada |
| Sucesso | Sucesso: A sessão foi bem-sucedida |
| Falhou | Falha na sessão |

## Diferenças com a API da plataforma legada

Quando você usa essa chamada de API para fazer upload em um projeto R12 em que a tabela de destino ainda não existe, o site Apptio cria a tabela e instala os dados no primeiro período de tempo, independentemente do período de tempo especificado na chamada de API. Isso se aplica somente ao primeiro upload para uma tabela que ainda não existe. Todas as chamadas subsequentes respeitam a data especificada. O motivo desse comportamento é garantir que as colunas estejam presentes no primeiro período de tempo. Se você não quiser ter dados presentes até um período específico, poderá criar a tabela manualmente ou, após o upload inicial, fazer o seguinte:

1. Faça o download dos dados inicialmente carregados por meio da interface do usuário Apptio.
2. Crie um arquivo que inclua apenas o cabeçalho.
3. Faça upload do cabeçalho para o primeiro período de tempo no projeto.
4. Faça o upload dos dados baixados na etapa 1 para o período de tempo desejado.

Para obter mais detalhes sobre essa API, consulte [API URL para fazer upload de uma tabela.](../studio/apis/studio_api_url_table.html "♦ Aplica-se a: v11.x, v12.0, v12.1, v12.2+")

**Tópico principal:** [Integração de API](../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
