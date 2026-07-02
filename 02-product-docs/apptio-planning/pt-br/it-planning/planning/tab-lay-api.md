---
source_system: "apptio-planning"
practice: "tbm"
language: "pt-br"
doc_type: "it-planning"
title: "APIs de layout de tabelas"
breadcrumb:
  - "Planning"
  - "APIs"
  - "Visão geral do planejamento de APIs REST"
source_path: "it-planning/planning/tab-lay-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# APIs de layout de tabelas

**A API de layouts de tabela** fornece acesso aos metadados de layout utilizados para exibir e organizar dados de despesas no Apptio Planning. Os layouts definem como os dados do plano são estruturados e apresentados nos diferentes tipos de despesas.

Essa API permite recuperar layouts públicos e privados visíveis ao usuário autenticado, possibilitando integrações que dependem de definições de esquema consistentes ou de exportações e importações que levam em conta o layout.

## ACESSE /planning/api/v1/layouts

**Descrição**

Recupera todos os layouts (públicos e privados) visíveis por usuário para um tipo específico de despesa

**Solicitação**

```
POST https://app.apptio.com/planning/api/v1/layouts
```

Observação: Certifique-se de que o endereço URL corresponda à sua região (por exemplo, app-eu.apptio.com, app-au.apptio.com ).

**Cabeçalhos**

|  |  |  |
| --- | --- | --- |
| **Cabeçalho** | **Valor** | **Descrição** |
| apptio-opentoken | <open-token> | Token de autenticação gerado na etapa 2 dos pré-requisitos |
| apptio-ambiente-atual | <environment-id> | UUID do ambiente necessário obtido na etapa 3 dos pré-requisitos |

**Parâmetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nome** | **Valores permitidos** | **Necessário** | **Descrição** |
| tipo | Resumo  TRABALHO\_EXISTENTE  TRABALHO\_PLANEJADO  ATIVIDADE LABORAL  Contrato  ASSET\_EXISTING  ASSET\_PLANNED  Outro | TRUE | Tipo de despesa para a aquisição de layouts |

**Resposta**

```
[ 
		{ 
			"id": "_DEFAULT_VIEW_", 	
			"name": "Default Layout", 
			"isShared": true 	 
		}, 
		{ 	"id": "MyLayout", 
			  "name": "My Layout", 	
			  "isShared": false 
		}
	]
```

Retorna um objeto JSON com as seguintes propriedades:

- ***id*** : Identificador único do layout
- ***nome*** : Nome de exibição do layout
- **isShared** : true se o layout for público, false se for privado

**Tópico principal:** [Visão geral do planejamento de APIs REST](../../it-planning/planning/plan-api.html "As APIs REST do Planning do Apptio oferecem acesso programático e seguro a planos, dados de planejamento, metadados e artefatos relacionados no Planning d Apptio. Essas APIs foram projetadas para oferecer suporte à automação e às integrações de sistemas em casos de uso relacionados a planejamento, previsão, análise, governança e troca de dados.")
