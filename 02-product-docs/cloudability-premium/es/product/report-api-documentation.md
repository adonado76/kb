---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Documentación de la API de informes"
breadcrumb:
  - "Cloudability Premium"
  - "Cloudability API"
  - "Contenedores Puntos finales"
source_path: "product/report-api-documentation.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Documentación de la API de informes

Resumen

El punto final del informe está destinado a sustituir muchas funciones que anteriormente estaban divididas en una variedad de API de contenedores y está destinado a proporcionar una visión más singular de los datos que alimentan la función de información de los contenedores.

Este endpoint permite el análisis de datos mediante la especificación de métricas específicas a agregar que pueden combinarse con grupos y filtros para recopilar costes.

Punto final

`/v3/containers/report`

Parámetros de consulta:

| Parámetro | Obligatorio | Descripción | Valor predeterminado | Permitido |
| --- | --- | --- | --- | --- |
| viewId | No | Cloudability identificador de vista que se puede pasar para permitir el filtrado por identificadores de cuenta | Identificador de vista por defecto de la organización | 0 (todo si está permitido), cualquier valor numérico configurado |

Cuerpo de la solicitud

El cuerpo de la solicitud de informe es un objeto json compuesto por los siguientes atributos clave:

| Parámetro | Obligatorio | Tipo | Ejemplo | Valores admitidos |
| --- | --- | --- | --- | --- |
| iniciar | Sí | fecha | 01-06-2024 | Cualquier fecha posterior a 2022-01-01 |
| final | Sí | fecha | 2 de junio de 2024 | Cualquier fecha posterior a 2022-01-01, debe ser mayor o igual a la fecha de inicio |
| costType | Sí | serie | ajustado | Véase: Tipos de costes admitidos |
| métricas | Sí | lista de cadenas | ["coste\_total", "eficiencia\_coste\_total"] | Véase: Valores métricos admitidos |
| Límite | Sí | entero | 10 | 1-1000 |
| widgetType | Tipo | serie | superior | Ver: Tipos de widgets compatibles |
| recuento | No | lista de cadenas | ["grupo"] | Ver: Valores de grupo, recuento y filtro admitidos |
| grupo | No | lista de cadenas | ["grupo"] | Ver: Valores de grupo, recuento y filtro admitidos |
| filtros | No | lista de cadenas | ["cluster== {cluster\_uuid} "] | Ver: Valores de grupo, recuento y filtro admitidos |
| Clasificar | No | lista de configuraciones | [{"sortMetric":"total\_cost","sortOrder":" desc"}] | Ver: Configuraciones de clasificación admitidas |
| paginationToken | No | serie | � | Ver: Paginación |

Tipos de costes admitidos

| Tipo de orden | Relación con la interfaz de usuario de los contenedores |
| --- | --- |
| ajustado | Efectivo |
| total\_amortizado\_ajustado | Ajustado amortizado |

Valores métricos admitidos

| Métrica | Métrica de costes estándar | Uso estándar Métrico | Notas |
| --- | --- | --- | --- |
| cpu/reservado | Sí | Sí | Se evalúa en función del máximo de recursos solicitados y utilizados |
| memoria/reserva | Sí | Sí | Se evalúa en función del máximo de recursos solicitados y utilizados |
| red/rx | Sí | Sí | Los valores de reparto equitativo siempre serán iguales a los valores asignados |
| red/tx | Sí | Sí | Los valores de reparto equitativo siempre serán iguales a los valores asignados |
| sistema de archivos/uso | Sí | Sí | � |
| volumen\_persistente/uso | Sí | Sí | El uso se determina en función del tamaño solicitado del PV, y es 1:1 con un PVC |
| gpu/reservado | Sí | Sí | Los valores de reparto equitativo siempre serán iguales a los valores asignados |
| varios | Sí | No | Se trata de una métrica basada únicamente en los costes |

Campos que se pueden solicitar

| Nombre de campo | Tipo de campo | Métricas admitidas | Significado |
| --- | --- | --- | --- |
| reparto\_coste\_total | Agregado | N/A | Coste total compartido de todos los tipos de métricas: representa los costes subyacentes agregados de todos los recursos que contribuyen a la consulta |
| coste\_total\_asignado | Agregado | N/A | El coste total asignado a todos los tipos de métricas representa el coste utilizado de todos los recursos aportados a la consulta |
| coste\_total\_inactivo | Agregado | N/A | Coste ocioso total en todos los tipos de métricas, calculado mediante total\_cost\_fairshare - total\_cost\_allocated |
| eficiencia\_coste\_total | Agregado | N/A | Eficiencia total de costes en todos los tipos de métricas, calculada mediante total\_cost\_allocated / total\_cost\_fairshare |
| uso\_coste\_eficacia | Agregado | N/A | Eficacia del coste de utilización en todos los tipos de métricas, calculada mediante una relación entre el coste de utilización y el coste total asignado |
| {metric} /uso\_coste\_asignado | Por unidad métrica | cpu, memoria | Coste de utilización por métrica |
| {metric} /eficiencia\_de\_coste\_de\_uso | Por unidad métrica | cpu, memoria | Eficacia del coste de utilización por métrica, calculada mediante un cociente de coste de utilización / coste\_total\_asignado |
| {metric} /solicitud | Por unidad métrica | cpu, memoria, gpu | Importe de los recursos solicitados |
| {metric} /uso | Por unidad métrica | cpu, memoria, gpu | Cantidad de recursos utilizados |
| {metric} /límite | Por unidad métrica | cpu, memoria, gpu | Límite de recursos, 0 en este caso indica que no se ha establecido ningún límite |
| {métrico}\_coste\_parte\_proporcional | Por unidad métrica | Métricas de costes estándar | Representación del coste justo de la utilización de la métrica |
| {métrico}\_coste\_asignado | Por unidad métrica | Métricas de costes estándar | Representación del coste imputado de la utilización de la métrica |
| {métrico}\_coste\_inactivo | Por unidad métrica | Métricas de costes estándar | Fairshare - Representación del coste asignado de la métrica |
| {métrica}\_rentabilidad | Por unidad métrica | Métricas de costes estándar | Valor de los costes asignados/compartidos |
| {metric} utilización\_compartida | Por unidad métrica | Métricas de costes estándar | Valor de utilización del Fairshare |
| {metric} utilización\_asignada | Por unidad métrica | Métricas de costes estándar | Valor de utilización asignado |
| {métrica}\_utilización\_inactivo | Por unidad métrica | Métricas de costes estándar | Fairshare - Utilización asignada |
| {metric} eficiencia\_de\_utilización | Por unidad métrica | Métricas de costes estándar | Valor de utilización asignado/compartido |

Tipos de widgets compatibles

| Tipo de widget | Relación con la interfaz de usuario de los contenedores | Significado | Requisitos | Restricciones |
| --- | --- | --- | --- | --- |
| superior | Datos de la tabla | Se trata de la representación más habitual de los datos de los contenedores, que devuelve datos agregados a lo largo del periodo de tiempo especificado | � | El grupo no debe contener un período de tiempo |
| icr | Widgets KPI | Esto devuelve un valor singular | � | Resultado único  Grupo no disponible Paginación no disponible |
| bar | Gráficos de barras | Esto proporciona un conjunto de valores superior/inferior sin respetar la generación de series continuas de datos a lo largo del periodo de tiempo | Debe fijarse un grupo horario (por ejemplo: día) | La paginación no está disponible |
| línea | Gráficos de líneas | Esto devuelve la serie continua superior/inferior de datos a lo largo del periodo de tiempo | Debe fijarse un grupo horario (por ejemplo: día) | La paginación no está disponible |

Valores de grupo, recuento y filtro admitidos

Grupos, Recuentos y Filtros comparten un conjunto superpuesto de datos accesibles, que pueden utilizarse de las siguientes maneras:

Grupos

Los grupos devuelven resultados agregados por valores únicos en ese campo.

Por ejemplo, la agrupación por clúster devolvería un conjunto de resultados aislados por clúster.

Cuenta

Los recuentos devuelven una sección de resultados que identifica el número de entradas únicas para ese aspecto.

Por ejemplo, un recuento de espacios de nombres devolvería el número total de espacios de nombres dentro de la selección.

Filtros

Los filtros permiten al usuario restringir el conjunto de resultados a sólo un subconjunto de ellos.

Por ejemplo, si se proporciona un filtro de tipo\_carga\_trabajo==implantación, sólo se obtendrán resultados de las cargas de trabajo identificadas como propiedad de una implantación.

| Valor | Significado | Ejemplo de valores devueltos | Soportes Filtro | Grupo de apoyo | Soportes Recuento |
| --- | --- | --- | --- | --- | --- |
| clúster | Identificador único del clúster, se puede recuperar un conjunto completo de estos con asignaciones de nombres desde el punto final de los clústeres | XXXXXXX-XXXX-XXXX-XXXXXXXXXXXX | Sí | Sí | Sí |
| día | Permite agrupar los datos por días, debe utilizarse con un widgetType compatible (barra/línea) | 01-06-2024 | No | No | No |
| tipo\_carga\_trabajo | Tipo de propietario de mayor nivel de la carga de trabajo | despliegue, cronjob, statefulset, etc | Sí | Sí | Sí |
| nombre\_carga\_trabajo | Nombre del propietario de más alto nivel de la carga de trabajo | mi-nombre-de-servicio | Sí | Sí | Sí |
| espacio de nombres | Espacio de nombres en el que están presentes las cargas de trabajo | nombre de mi espacio de nombres | Sí | Sí | Sí |
| container | Nombre del contenedor que se está ejecutando en el clúster | mi-nombre-de-contenedor | Sí | Sí | Sí |
| pod | Nombre del pod que se está ejecutando en el clúster | mi-nombre-de-pod | Sí | Sí | Sí |
| nodo | Nombre de nodo asignado | ip-1.2.3.4.region.compute.internal | Sí | Sí | Sí |
| nodo\_id | Identificador del nodo proveedor | aws:///region/i-1234 | Sí | Sí | Sí |
| familia\_de\_instancias | Familia de instancias del nodo subyacente | t2 | Sí | Sí | Sí |
| categoría\_de\_instancia | Categoría de instancia del nodo subyacente | Uso general | Sí | Sí | Sí |
| tipo\_instancia | Tipo de instancia del nodo subyacente | t2.micro | Sí | Sí | Sí |
| plan\_ahorro | Tipo de plan de ahorro aplicado al nodo subyacente | ComputeSavingsPlan | Sí | Sí | Sí |
| tipo\_arrendamiento | Método de arrendamiento del nodo subyacente | Bajo demanda | Sí | Sí | Sí |
| instancia\_reservada | Si el nodo subyacente se está ejecutando como parte de un compromiso de instancia reservada | S, N | Sí | Sí | Sí |
| CPU asignable | CPU (en micronúcleos) disponibles en el nodo subyacente | 48000000 | Sí | Sí | Sí |
| memoria\_asignable | Memoria (en bytes) disponible en el nodo subyacente | 1000000000 | Sí | Sí | Sí |
| gpu\_asignable | Unidades GPU (en microgpu), disponibles en el nodo subyacente | 1000000 | Sí | Sí | Sí |
| región | Región en la que se ejecuta el nodo subyacente | us-west-2 | Sí | Sí | Sí |
| zona | Zona de disponibilidad en la que se ejecuta el nodo subyacente | us-west-2a | Sí | Sí | Sí |
| grupo\_nodo | Grupo de nodos (si es detectable) del que forma parte el nodo subyacente | mi-nodo-grupo | Sí | Sí | Sí |
| proveedor | Proveedor de la nube en la que se ejecuta el clúster | AWS, Azure, etc | Sí | No | No |
| tipo\_grupo | Tipo de clúster que se está ejecutando | eks, gke, openshift, etc | Sí | No | No |

Uso de filtros

Los filtros pueden configurarse suministrando los:

- Atributo filtrado
  - Cualquier valor indicado como filtrable en la lista anterior

- Operador
  - ==

    - Iguales (distingue mayúsculas de minúsculas)
  - []=

    - Uno de (distingue mayúsculas de minúsculas)

- Valor filtrado
  - Cualquier valor que el usuario quiera filtrar

Ejemplos:

- namespace==sistema-kube
  - Filtrará los resultados para mostrar sólo los datos de kube-system

- workload\_type[]=cronjob,job
  - Filtrará los resultados para mostrar sólo datos de cronjobs o trabajos

Configuraciones de clasificación admitidas

Si no se establece, la función de ordenación ordena por defecto por la primera columna métrica especificada en orden descendente. Se configura para garantizar que la paginación sea siempre posible.

Los valores de ordenación deben pasarse en el orden en que el autor de la llamada desea que se produzcan, y pueden especificarse para cualquier valor métrico solicitado.

El ejemplo siguiente ordenaría las filas por eficiencia en orden descendente y, a continuación, por coste\_total en orden descendente.

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

Paginación

| Campo | Tipo | Descripción |
| --- | --- | --- |
| result.pagination.hasNext | booleano | Indica si hay una página siguiente |
| result.pagination.nextToken | serie | Proporciona un valor de cadena que puede devolverse a la API para obtener el siguiente conjunto de resultados |

Si los datos anteriores para la paginación indican que otra página está disponible para su consumo, entonces el valor en "nextToken" puede ser pasado de nuevo a la api a través del parámetro "paginationToken".

Nota:

La solicitud no debe modificarse en ningún otro aspecto, y hacerlo puede provocar errores o que se devuelvan resultados incoherentes.

Ejemplo de EE.UU. (punto final de la API): https://api.cloudability.com/v3/containers/report

Ejemplos de solicitudes

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

Ejemplo de respuesta, incluyendo el token de paginación que puede ser devuelto a la API.

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

Este cuerpo de respuesta se divide en la siguiente sección:

| Campo | Tipo | Significado |
| --- | --- | --- |
| result.data | []objeto | Se trata del cuerpo principal de la respuesta que contiene una serie de elementos identificados por los valores de grupo solicitados |
| result.data [N].count | []mapa [cadena] cadena | Representa un conjunto de objetos que contienen el recuento único de valores solicitado |
| result.data [N].dimensiones | map[string] cadena | Representa los atributos agrupados de forma única determinados por los atributos agrupados |
| result.data [N].métricas | map[string] objeto | Representa los valores métricos agregados. Al agrupar por tiempo, cada unidad de tiempo estará representada por un índice en la matriz "valores" |
| result.data [N].métrica. {metric}.unit | serie | La unidad específica para ese tipo de métrica, los valores posibles son: moneda, bytes, microcpu, microgpu, eficiencia |
| result.data [N].métricas. {metric}.valores | []float64 | Conjunto de valores que representan los recursos utilizados durante el periodo de tiempo. Al agrupar por días, por ejemplo, cada entrada de la matriz representa un único día |

**Tema principal:** [Contenedores Puntos finales](../api-v3/containers_endpoints.html)
