---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Resolución de problemas"
breadcrumb:
  - "Billing"
  - "Resolución de problemas"
source_path: "boit/billing/troubleshooting/troubleshoot.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Resolución de problemas

Este apéndice es una guía práctica sobre «qué ha fallado y qué hay que comprobar primero». Úselo cuando los números no cuadren, los informes estén vacíos o los diarios no concuerden.

## Cómo utilizar este apéndice

Cada subsección está organizada por:

- **Síntoma** : Lo que ves.
- **Causas probables** : Las sospechosas habituales.
- **Qué comprobar** : Comprobaciones concretas en datos, configuración o procesos.
- **Quién actúa** : Normalmente, el administrador/analista, con la participación de otras personas según sea necesario.

## Las facturas parecen claramente erróneas o vacías

**Síntoma: Las facturas están casi o totalmente vacías.**

**Causas probables**

- No se han cargado datos de consumo para el periodo.
- Servicios no marcados como facturables.
- Tarifas que faltan o no son válidas para el período.
- Periodo incorrecto seleccionado en los informes.

**Qué hay que comprobar**

1. **Tabla de consumo** para el período:
   - ¿Hay filas para los servicios y consumidores previstos?
   - ¿Hay unidades distintas de cero donde se espera que haya uso?
2. **Tabla de servicios/ofertas** :
   - ¿Los servicios básicos están marcados como Activos y Facturables?
   - ¿Se ha cambiado algún código o llave recientemente?
3. **Tabla de tarifas** :
   - ¿Existen tarifas para todos los servicios facturables de ese periodo?
   - ¿Son correctas las fechas de vigencia (sin problemas de desviación de un mes)?
4. **Filtros del informe** :
   - Confirme que el informe está filtrado según el período y los consumidores deseados.

**Síntoma: Los cargos totales de facturación son mucho más bajos o más altos de lo esperado.**

**Causas probables**

- Alimentación parcial o tardía.
- Cambios en el modelo de cálculo de costes no tenidos en cuenta en las hipótesis de facturación.
- Tasas mal configuradas (decimal incorrecto, moneda incorrecta, unidad incorrecta).
- No se ha comunicado ningún cambio estructural importante (migración, jubilación).

**Qué hay que comprobar**

1. Compare **el total de unidades** por servicio con respecto al período anterior:
   - Busca cambios porcentuales importantes.
2. Comparar **valores de tasa** frente al período anterior:
   - Busque tasas que se hayan duplicado, reducido a la mitad o reducido a cero de forma repentina.
3. Verificar **los resultados del cálculo de costes** :
   - ¿El coste total de los servicios o dominios clave cambió de forma similar?
4. Pregunte a los propietarios de dominios:
   - ¿Algún evento tecnológico importante durante este periodo (migración, gran implementación, desmantelamiento)?

Si nada explica el cambio, considérelo un defecto y rastree los datos, las asignaciones y las tarifas.

## Consumidores/servicios ausentes o inesperados

**Síntoma: Falta una unidad de negocio, un proyecto o un producto conocidos en las facturas.**

**Causas probables**

- El consumidor no figura en el maestro de consumidores.
- El consumidor está presente, pero no se le ha asignado ningún consumo.
- Consumidor mapeado incorrectamente (por ejemplo, utilizando un ID o una jerarquía incorrectos).

**Qué hay que comprobar**

1. **Maestro de consumidores** :
   - Busca la entidad que falta por ID y nombre.
   - Confirme que está marcado como activo y asignado a la jerarquía correcta.
2. **Tablas de correspondencias** (si se utilizan):
   - Para los ID o etiquetas externos, verifica las asignaciones al consumidor esperado.
   - Comprueba si hay errores tipográficos, ID retirados o filas de mapeo duplicadas.
3. **Tabla de consumo** :
   - ¿Hay alguna fila para el consumidor que falta en este periodo?
   - Si no es así, ¿el sistema ascendente proporciona datos para ello?

**Síntoma: Aparecen servicios que deberían estar retirados o ser solo internos.**

**Causas probables**

- Servicio no marcado como retirado o no facturable.
- Códigos de servicio antiguos a los que aún hacen referencia las fuentes de consumo.
- Servicios internos de «fontanería» marcados accidentalmente como facturables.

**Qué hay que comprobar**

1. **Tabla de servicios/ofertas** :
   - Confirmar el estado del ciclo de vida (Activo/Retirada).
   - Confirmar facturable = No para servicios solo internos.
2. **Tabla de consumo** :
   - Comprueba las filas de uso con respecto a los servicios retirados.
   - Confirme que los sistemas ascendentes han dejado de enviar esos ID.
3. Si es necesario, diseñe una **regla de gestión de excepciones** :
   - Por ejemplo, desviar los códigos de servicio retirados a un servicio específico de «Excepción» durante un tiempo limitado mientras se limpian las fuentes.

## Unidades, tasas y anomalías en las tasas unitarias

**Síntoma: aumento o caída repentina de la tarifa unitaria durante un solo período.**

(La receta detallada se encuentra en la sección 15; esta es la versión resumida)

**Causas probables**

- Los costes fijos se reparten entre un número menor o mayor de unidades.
- Cambio en la asignación de costes.
- Cambio en la tarifa que no se entendió o no se comunicó.
- Falta el volumen o el coste de parte del periodo.

**Qué hay que comprobar**

1. **Informe** de tarifa unitaria para ese servicio en varios periodos:
   - Compare las unidades, el cargo, la tarifa por unidad y el coste por unidad, cuando estén disponibles.
2. **Tabla de tarifas** :
   - Confirme que la tarifa configurada para ese período no haya cambiado accidentalmente.
3. **Resultados del cálculo de costes** :
   - ¿El coste total de ese servicio cambió notablemente?
   - ¿Se actualizó algún factor determinante de la asignación?
4. **Datos de consumo** :
   - Comprueba que el volumen no esté truncado (por ejemplo, cobertura parcial del mes).

**Síntoma: Cargas cero o negativas donde no deberían existir.**

**Causas probables**

- Cero unidades o tarifas cero para un servicio que debería facturarse.
- Ajustes negativos cargados en las tablas de consumo o de costes.
- Convenciones de signos incorrectas en la lógica del modelo.

**Qué hay que comprobar**

1. **Informe de control de calidad/excepciones** para valores cero o negativos:
   - Identifique qué servicios y consumidores se ven afectados.
2. **Tabla de tarifas** :
   - Confirme que las tasas no sean cero y tengan el signo correcto.
3. **Tabla de consumo** :
   - Compruebe si se han cargado volúmenes negativos o nulos.
4. **Lógica de ajuste** :
   - Si se utilizan ajustes negativos de forma intencionada, confirme que solo se aplican a situaciones de corrección específicas.

## Cuestiones relacionadas con el entorno, la construcción y la promoción

**Síntoma: Los cambios probados en Desarrollo no aparecen en Preproducción.**

**Causas probables**

- Documentos retirados pero no devueltos.
- La compilación no se ha creado ni se ha promovido de «En desarrollo» a «En fase de pruebas».
- Mirando la compilación incorrecta en Staging.

**Qué hay que comprobar**

1. En desarrollo:
   - Comprueba si hay algún documento relacionado con la facturación que aún esté pendiente.
   - Asegúrese de que se registren después de la prueba.
2. Vista de compilaciones:
   - Confirmar que se ha creado una nueva compilación después del check-in.
   - Confirma que la compilación es la que utiliza Staging.
3. En preparación:
   - Verifique qué compilación está activa y que contiene los cambios esperados.

**Síntoma: La puesta en escena parece correcta, pero la producción no.**

**Causas probables**

- La compilación de ensayo nunca se promovió a producción.
- La promoción se ha completado, pero Producción sigue utilizando datos antiguos para ese periodo.
- Los usuarios están viendo informes almacenados en caché o marcados como favoritos de una compilación anterior.

**Qué hay que comprobar**

1. **Historial de promociones** :
   - Confirme que la compilación de ensayo prevista se ha promovido y ha tenido éxito.
2. **ID de compilación de producción** :
   - Verifica que la compilación activa de producción coincida con la compilación de ensayo validada.
3. **Informes** :
   - Confirme que los usuarios están abriendo los informes desde el punto final y la colección correctos.
   - Actualiza los filtros y, si es necesario, los marcadores.

## Informar sobre problemas

**Síntoma: Los informes se agotan o son extremadamente lentos.**

**Causas probables**

- Intervalos de tiempo muy amplios (varios años).
- Informes pesados con demasiadas dimensiones sin filtrar.
- Las consultas del modelo subyacente o del conjunto de datos no están optimizadas.

**Qué hay que comprobar**

1. Anime a los usuarios a **filtrar** por:
   - Un solo período o un intervalo de fechas corto.
   - Consumidores o servicios específicos.
2. Identificar informes con problemas de rendimiento recurrentes:
   - Considera rediseñarlos:
     - Agregando más.
     - Eliminar columnas que rara vez se utilizan.
3. Para problemas persistentes, considere la posibilidad de crear **informes resumidos** para un público amplio y reserve los informes con gran detalle para los analistas.

**Síntoma: Las columnas o los filtros han cambiado «inesperadamente».**

**Causas probables**

- Definición del informe actualizada en «En desarrollo» y promovida.
- Un informe local clonado tiene un aspecto similar, pero no es lo mismo.
- Vistas guardadas o filtros personales que anulan los valores predeterminados.

**Qué hay que comprobar**

1. Confirme el nombre y la ubicación **del informe canónico**.
2. Compare el diseño actual con el diseño documentado en el Apéndice B o con las especificaciones internas.
3. Si los cambios son legítimos, actualice la documentación y las capturas de pantalla de la formación.
4. Si los cambios son accidentales, restaura el diseño previsto en «En desarrollo» y vuelve a promocionarlo.

## Problemas de integración de diarios y finanzas

**Síntoma: Finanzas no puede cargar el archivo de diario.**

**Causas probables**

- El diseño del archivo no coincide con el formato de importación GL esperado.
- Faltan campos obligatorios (cuentas, centros de coste, códigos de empresa).
- Caracteres especiales o problemas de codificación.

**Qué hay que comprobar**

1. Compare la exportación actual con la **plantilla acordada** :
   - Orden de las columnas, nomenclatura, tipos de datos.
2. Utilice informes de control de calidad o validaciones:
   - Busque segmentos financieros que falten o no sean válidos.
3. Prueba con un **pequeño subconjunto** de líneas:
   - Ayuda a aislar los problemas de formato frente a los de contenido de datos.

**Síntoma: Se han contabilizado los diarios, pero los totales no coinciden con los informes de facturación.**

**Causas probables**

- Los filtros se aplican de forma diferente en Facturación y Finanzas.
- Contabilización en diferentes períodos (por ejemplo, mes de devengo frente a mes de uso).
- Diferencias por redondeo o conversión de divisas.
- Algunas líneas rechazadas durante la publicación.

**Qué hay que comprobar**

1. Vuelva a ejecutar **el informe de exportación del diario** para el período:
   - Confirmar el total por cuenta y consumidor.
2. En finanzas:
   - Realice un **balance de comprobación o un listado del diario** para las mismas cuentas y el mismo período.
3. Compare:
   - Si hay alguna diferencia, comprueba lo siguiente:
     - Líneas rechazadas.
     - Ajustes manuales.
     - Diferentes códigos de período.

Si los desajustes son recurrentes, acuerde una **vista de conciliación estándar** y unos plazos de cierre entre los departamentos de facturación y finanzas.

## Inconvenientes específicos de la edición

**Escollos específicos de Essentials**

Aviso: Se aplica únicamente a Billing Essentials.

Problemas comunes:

- Esperando ver vistas ricas en dominios (nube, aplicaciones, proyectos) que requieren Billing Standard.
- Suponiendo que existe acceso a TBM Studio para todas las funciones, cuando la configuración de Essentials suele ser propiedad de un socio o de un equipo independiente.

Mitigaciones:

- Establezca expectativas claras sobre lo que Essentials puede y no puede mostrar.
- Documenta cómo solicitar cambios de configuración al equipo que tiene acceso a Studio.

**Dificultades específicas de las normas**

Aviso: Se aplica únicamente a la norma de facturación.

Problemas comunes:

- Desplegar componentes de dominio sin estabilizar la ruta principal PxQ.
- Desalineación de los cambios en los costes con las expectativas de facturación (por ejemplo, cambiar el nombre de los servicios o modificar las asignaciones a mitad del periodo).
- Identificar las deficiencias en la gobernanza que socavan las vistas de la nube y las aplicaciones.

Mitigaciones:

- Estabilizar el **servicio básico × facturación al consumidor** antes de añadir la complejidad de la nube, los proyectos y los precios de transferencia.
- Coordinar los cambios en el cálculo de costes con las partes interesadas de facturación y finanzas.
- Utilice informes de control de calidad y excepciones específicos del dominio para garantizar la disciplina de los datos.

## Cuándo escalar

Algunos asuntos se gestionan mejor con un equipo especializado o un socio de apoyo.

Escalar cuando:

- Varios ciclos de facturación consecutivos no se completan o requieren soluciones manuales muy laboriosas.
- Los problemas de exportación y publicación del diario persisten incluso después de las comprobaciones locales.
- Se sospecha que los defectos del modelo se encuentran en los propios componentes entregados, no solo en la configuración local.
- Los plazos legales o reglamentarios corren peligro debido a defectos en la facturación.

Antes de escalar:

- Captura:
  - Descripción clara de los síntomas.
  - Periodo(s) afectado(s).
  - Capturas de pantalla o extractos de informes.
  - Medidas ya adoptadas y conclusiones hasta la fecha.

Un enfoque disciplinado para la resolución de problemas, junto con este apéndice, suele resolver la mayoría de los problemas a nivel local. Cuando no sea así, una buena documentación de lo que ya ha comprobado hará que cualquier escalada sea mucho más eficiente.
