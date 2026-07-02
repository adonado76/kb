---
source_system: "cloudability-premium"
practice: "finops"
language: "pt-br"
doc_type: "product"
title: "Documentação da API de relatórios"
breadcrumb:
  - "Cloudability Premium"
  - "Cloudability API"
  - "Pontos finais de contêineres"
source_path: "product/report-api-documentation.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Documentação da API de relatórios

Resumo

O ponto de extremidade do relatório tem o objetivo de substituir muitas funções que antes eram divididas em várias APIs de contêineres e fornecer uma visão mais singular dos dados que alimentam o recurso de insights de contêineres.

Esse ponto de extremidade permite a análise de dados por meio da especificação de métricas específicas a serem agregadas, que podem ser combinadas com grupos e filtros para reunir custos.

Ponto final

`/v3/containers/report`

Parâmetros de consulta:

| Parâmetro | Necessário | Descrição | Padrão | Permitido |
| --- | --- | --- | --- | --- |
| viewId | Não | Cloudability identificador de visualização que pode ser passado para permitir a filtragem por identificadores de conta | Identificador de visualização padrão da organização | 0 (todos, se permitido), qualquer valor numérico configurado |

Corpo da solicitação

O corpo da solicitação do relatório é um objeto json composto pelos seguintes atributos principais:

| Parâmetro | Necessário | Tipo | Exemplo | Valores suportados |
| --- | --- | --- | --- | --- |
| início | Sim | data | 01/06/2024 | Qualquer data após 2022-01-01 |
| terminar | Sim | data | 02/06/2024 | Qualquer data após 2022-01-01 deve ser maior ou igual à data de início |
| costType | Sim | sequência | ajustado | Veja: Tipos de custos suportados |
| métricas | Sim | lista de cadeias de caracteres | ["custo\_total", "eficiência\_custo\_total"] | Veja: Valores de métrica suportados |
| limite | Sim | número inteiro | 22 | 1-1.000 |
| widgetType | Tipo | sequência | top | Veja: Tipos de widgets suportados |
| count | Não | lista de cadeias de caracteres | ["cluster"] | Veja: Valores de grupo, contagem e filtro suportados |
| Grupo | Não | lista de cadeias de caracteres | ["cluster"] | Veja: Valores de grupo, contagem e filtro suportados |
| filtros | Não | lista de cadeias de caracteres | ["cluster== {cluster\_uuid} "] | Veja: Valores de grupo, contagem e filtro suportados |
| ordenar | Não | lista de configurações | [{"sortMetric":"total\_cost","sortOrder":" desc"}] | Veja: Configurações de classificação suportadas |
| paginationToken | Não | sequência | � | Veja: Paginação |

Tipos de custos suportados

| Tipo de classificação | Relação com a interface do usuário de contêineres |
| --- | --- |
| ajustado | Dinheiro |
| total\_ajustado\_amortizado | Amortizado Ajustado |

Valores de métrica suportados

| Métrica | Métrica de custo padrão | Uso padrão Métrico | Notas |
| --- | --- | --- | --- |
| cpu/reservado | Sim | Sim | Avaliado com base no máximo de recursos solicitados e utilizados |
| memória/reservada | Sim | Sim | Avaliado com base no máximo de recursos solicitados e utilizados |
| rede/rx | Sim | Sim | Os valores de fairshare sempre serão iguais aos valores alocados |
| rede/tx | Sim | Sim | Os valores de fairshare sempre serão iguais aos valores alocados |
| sistema de arquivos/utilização | Sim | Sim | � |
| volume\_persistente/utilização | Sim | Sim | O uso é determinado com base no tamanho solicitado do PV, e é 1:1 com um PVC |
| gpu/reservado | Sim | Sim | Os valores de fairshare sempre serão iguais aos valores alocados |
| diversos | Sim | Não | Essa é uma métrica somente de custo |

Campos que podem ser solicitados

| Nome do Campo | Tipo de Campo | Métricas suportadas | Significado |
| --- | --- | --- | --- |
| custo\_total\_justa\_parte | Agregado | N/A | Custo total de fairshare em todos os tipos de métricas, o que representa os custos subjacentes agregados de todos os recursos que contribuem para a consulta |
| custo\_total\_alocado | Agregado | N/A | O custo total alocado em todos os tipos de métricas representa o custo utilizado de todos os recursos que contribuíram para a consulta |
| custo\_total\_inativo | Agregado | N/A | Custo ocioso total em todos os tipos de métricas, calculado por meio de total\_cost\_fairshare - total\_cost\_allocated |
| eficiência\_custo\_total | Agregado | N/A | Eficiência de custo total em todos os tipos de métricas, calculada por meio de total\_cost\_allocated / total\_cost\_fairshare |
| eficiência de custo de uso | Agregado | N/A | Eficiência de custo de uso em todos os tipos de métricas, calculada por meio de uma proporção de custo de uso / total\_cost\_allocated |
| {metric} /custo\_de\_uso\_alocado | Por métrica | cPU, memória | Custo de uso por métrica |
| {metric} /eficiência\_de\_custo\_de\_uso | Por métrica | cPU, memória | Eficiência de custo de uso por métrica, calculada por meio de uma proporção de custo de uso / total\_cost\_allocated |
| {metric} /pedido | Por métrica | cPU, memória, gpu | Quantidade de recursos solicitados |
| {metric} /uso | Por métrica | cPU, memória, gpu | Quantidade de recursos utilizados |
| {metric} /limite | Por métrica | cPU, memória, gpu | Limite de recursos, 0 nesse caso indica que nenhum limite foi definido |
| {métrico}\_custo\_participação\_equitativa | Por métrica | Métricas de custo padrão | Representação do custo de fairshare do uso da métrica |
| custo\_atribuído\_métrico | Por métrica | Métricas de custo padrão | Representação do custo alocado do uso da métrica |
| {métrico}\_custo\_inativo | Por métrica | Métricas de custo padrão | Fairshare - Representação do custo alocado da métrica |
| {métrica}\_custo\_eficiência | Por métrica | Métricas de custo padrão | Valor de custo alocado/airshare |
| {metric} utilização\_fairshare | Por métrica | Métricas de custo padrão | Valor de utilização do Fairshare |
| {metric} utilização\_alocada | Por métrica | Métricas de custo padrão | Valor de utilização alocado |
| {métrica}\_utilização\_inativo | Por métrica | Métricas de custo padrão | Fairshare - Utilização alocada |
| {metric} \_utilização\_eficiência | Por métrica | Métricas de custo padrão | Valor de utilização alocado/fairshare |

Tipos de widgets compatíveis

| Tipo de widget | Relação com a interface do usuário de contêineres | Significado | Requisitos | Restrições |
| --- | --- | --- | --- | --- |
| top | Dados da tabela | Essa é a representação mais comum de dados de contêineres que retorna dados agregados durante o período de tempo especificado | � | O grupo não deve conter um período de tempo |
| kpi | Widgets de KPI | Isso fornece um valor singular de volta | � | Somente resultado único  O grupo não está disponível A paginação não está disponível |
| barras | Gráficos de barras | Isso fornece um conjunto de valores superiores/inferiores sem respeitar a geração de séries contínuas de dados ao longo do período de tempo | Um grupo de tempo deve ser definido (por exemplo, dia) | A paginação não está disponível |
| linha | Gráficos de linhas | Isso retorna a série contínua superior/inferior de dados no período de tempo | Um grupo de tempo deve ser definido (por exemplo, dia) | A paginação não está disponível |

Valores de grupo, contagem e filtro suportados

Grupos, contagens e filtros compartilham um conjunto sobreposto de dados acessíveis, que podem ser utilizados das seguintes maneiras:

Grupos

Os grupos retornam resultados agregados por valores exclusivos nesse campo.

Por exemplo, o agrupamento por cluster retornaria um conjunto de resultados isolado por cluster.

Contagens

Counts retorna uma seção de resultados que identifica o número de entradas exclusivas para esse aspecto.

Por exemplo, uma contagem de namespaces retornaria o número total de namespaces dentro da seleção.

Filtros

Os filtros permitem que um usuário restrinja o conjunto de resultados a apenas um subconjunto de resultados.

Por exemplo, o fornecimento de um filtro do tipo workload\_type==deployment só retornaria resultados para cargas de trabalho identificadas como pertencentes a uma implantação.

| Valor | Significado | Exemplo de valores retornados | Filtro de suporte | Grupo de suporte | Contagem de suportes |
| --- | --- | --- | --- | --- | --- |
| cluster | Identificador exclusivo do cluster; um conjunto completo desses identificadores com mapeamentos de nomes pode ser recuperado no endpoint de clusters | XXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXXXXXXXX | Sim | Sim | Sim |
| dia | Permite o agrupamento de dados por dia; deve ser usado com um site compatível widgetType (bar/line) | 01/06/2024 | Não | Não | Não |
| tipo de carga de trabalho | Tipo de carga de trabalho do proprietário de nível mais alto | implantação, cronjob, statefulset, etc | Sim | Sim | Sim |
| nome\_da\_carga\_de\_trabalho | Nome do proprietário de nível mais alto da carga de trabalho | nome do meu serviço | Sim | Sim | Sim |
| namespace | Namespace onde as cargas de trabalho estão presentes | nome do meu espaço de nome | Sim | Sim | Sim |
| contêiner | Nome do contêiner que está sendo executado no cluster | nome do meu contêiner | Sim | Sim | Sim |
| conjunto | Nome do pod que está sendo executado no cluster | nome do meu pod | Sim | Sim | Sim |
| nós | Nome do nó que é atribuído | ip-1.2.3.4.region.compute.internal | Sim | Sim | Sim |
| ID do nó | Identificador de nó do provedor | aws:///region/i-1234 | Sim | Sim | Sim |
| família\_de\_instâncias | Família de instâncias do nó subjacente | t2 | Sim | Sim | Sim |
| categoria\_instância | Categoria de instância do nó subjacente | Finalidade geral | Sim | Sim | Sim |
| tipo\_de\_instância | Tipo de instância do nó subjacente | t2.micro | Sim | Sim | Sim |
| plano de poupança | Tipo de plano de poupança aplicado ao nó subjacente | ComputeSavingsPlan | Sim | Sim | Sim |
| tipo de arrendamento | Método de leasing do nó subjacente | On-Demand | Sim | Sim | Sim |
| instância\_reservada | Se o nó subjacente estiver sendo executado como parte de um compromisso de instância reservada | S, N | Sim | Sim | Sim |
| cpu\_allocatable | Unidades de CPU (em microcore), disponíveis no nó subjacente | 48000000 | Sim | Sim | Sim |
| memória\_alocável | Memória (em bytes) disponível no nó subjacente | 1000000000 | Sim | Sim | Sim |
| gpu\_allocatable | Unidades de GPU (em microgpu), disponíveis no nó subjacente | 1000000 | Sim | Sim | Sim |
| região | Região na qual o nó subjacente está sendo executado | us-west-2 | Sim | Sim | Sim |
| zona | Zona de disponibilidade na qual o nó subjacente está sendo executado | us-west-2a | Sim | Sim | Sim |
| grupo de nós | Grupo de nós (se detectável), do qual o nó subjacente faz parte | meu grupo de nós | Sim | Sim | Sim |
| fornecedor | Provedor de nuvem no qual o cluster está sendo executado | AWS, Azure, etc | Sim | Não | Não |
| tipo de cluster | Tipo de cluster que está em execução | eks, gke, openshift, etc | Sim | Não | Não |

Uso de filtros

Os filtros podem ser configurados fornecendo o:

- Atributo filtrado
  - Qualquer valor indicado como filtrável na lista acima

- Operador
  - ==

    - Equals (diferencia maiúsculas de minúsculas)
  - []=

    - Um de (diferencia maiúsculas de minúsculas)

- Valor filtrado
  - Qualquer valor que o usuário queira filtrar

Exemplos:

- namespace==kube-system
  - Filtrará os resultados para mostrar apenas os dados do kube-system

- workload\_type[]=cronjob,job
  - Filtrará os resultados para mostrar apenas os dados de cronjobs ou trabalhos

Configurações de classificação suportadas

Se não for definido, o recurso de classificação tem como padrão a classificação pela primeira coluna métrica especificada em ordem decrescente. Isso é configurado para garantir que a paginação seja sempre possível.

Os valores de classificação devem ser passados na ordem em que o chamador deseja que eles ocorram e podem ser especificados para qualquer valor de métrica solicitado.

O exemplo abaixo classificaria as linhas por eficiência em ordem decrescente e, em seguida, por total\_cost em ordem decrescente.

```
[
  {
    "sortMetric": "total_cost_efficiency",
    "sortOrder": "desc"
   },
   {
     "sortMetric": "total_cost",
     "sortOrder": "desc"
   }
 ]
```

Paginação

| Campo | Tipo | Descrição |
| --- | --- | --- |
| result.pagination.hasNext | booleano | Indica se há uma página seguinte |
| result.pagination.nextToken | sequência | Fornece um valor de cadeia de caracteres que pode ser passado de volta à API para obter o próximo conjunto de resultados |

Se os dados acima para paginação indicarem que outra página está disponível para consumo, o valor em "nextToken" poderá ser passado de volta para a API por meio do parâmetro "paginationToken".

Nota:

A solicitação não deve ser alterada em nenhum outro aspecto, e isso pode causar erros ou resultados inconsistentes.

Exemplo dos EUA (ponto de extremidade da API): https://api.cloudability.com/v3/containers/report

Exemplos de solicitações

```
curl --location 'https://api.cloudability.com/v3/containers/report' \
--header 'apptio-opentoken: {token}' \
--header 'apptio-environmentid: {env_id}' \
--header 'Content-Type: application/json' \
--data '{
    "start": "2024-06-10",
    "end": "2024-06-10",
    "costType": "adjusted",
    "metrics": [
	"total_cost"
    ],
    "group": [
	"namespace"
    ],
    "count": [
	"workload_name"
    ],
	"filters": [
		"cluster==XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX"
	],
    "sort": [
	{
	     "sortMetric": "total_cost",
	     "sortOrder": "desc"
	}
    ],
    "widgetType": "top",
    "limit": 1
}'
```

Exemplo de resposta, incluindo o token de paginação que pode ser passado de volta para a API.

```
{
    "result": {
	"data": [
	   {
		"count": [
		    {
			"key": "workload_name",
			"value": "20"
		    }
		],
		"dimensions": {
		    "namespace": "my-namespace"
		},
		"metrics": {
		    "total_cost": {
			"unit": "currency",
			"values": [
				100.00
			]
		    }
		}
	    }
	 ],
	"pagination": {
	    "hasNext": true,
	    "nextToken": "veryLongPaginationToken"
	}
   }
}
```

Esse corpo de resposta é dividido na seção a seguir:

| Campo | Tipo | Significado |
| --- | --- | --- |
| result.data | []objeto | Esse é o corpo da resposta principal que contém uma série de elementos identificados pelos valores de grupo solicitados |
| result.data [N].count | []mapa [string] string | Isso representa um conjunto de objetos que contém a contagem exclusiva de valores solicitada |
| result.data [N].dimensions | mapa[string] string | Isso representa os atributos exclusivamente agrupados determinados pelos atributos agrupados |
| result.data [N].metrics | objeto map[string] | Isso representa os valores de métrica agregados. Ao agrupar por tempo, cada unidade de tempo será representada por um índice na matriz "values" |
| result.data [N].metrics. {metric}.unidade | sequência | A unidade específica para esse tipo de métrica; os valores possíveis são: moeda, bytes, microcpu, microgpu, eficiência |
| result.data [N].metrics. {metric}.values | []float64 | Um conjunto de valores que representam os recursos utilizados durante o período de tempo. Ao agrupar por dia, por exemplo, cada entrada na matriz representa um único dia |

**Tópico pai:** [Pontos finais de contêineres](../api-v3/containers_endpoints.html)
