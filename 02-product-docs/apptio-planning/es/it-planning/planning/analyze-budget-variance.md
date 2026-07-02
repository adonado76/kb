---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Análisis de desviaciones"
breadcrumb:
  - "Planning"
  - "Análisis de varianza"
source_path: "it-planning/planning/analyze-budget-variance.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Análisis de desviaciones

La función Análisis de desviaciones le ayuda a comparar un plan de previsión actual con una línea de base (presupuesto o previsión anterior), identificar diferencias significativas y crear un seguimiento de comentarios que explique los motivos de las desviaciones.

## Ventajas claves

- Analice las desviaciones por centro de coste, cuenta o departamento a escala.
- Marque sólo las desviaciones significativas utilizando umbrales definidos para centrar el esfuerzo.
- Asigne factores de desviación y comentarios para crear pistas de explicación listas para la auditoría.
- Exportación de comentarios para su integración con herramientas de elaboración de informes.

## Configurar el análisis de varianza

Nota: Para configurar el Análisis de Desviaciones se requieren los roles de Administrador o Propietario del Proceso Presupuestario.

Paso 1: Activar la función

1. Vaya a **Ajustes** (icono de engranaje) **→ Perfil de empresa**
2. Activar **el cuadro de mandos y los controladores de desviaciones**

Paso 2: Definir los factores de desviación

1. Vaya a **Configuración → Datos de referencia → Controlador de desviación**
2. Cargar una lista de valores de controladores de desviaciones (por ejemplo, *calendario del proyecto*, *calendario contable*, *gastos no planificados* )
3. **Publicar** los cambios

Paso 3: Definir categorías de cuentas

1. Vaya a **Configuración → Datos de referencia → Categoría de cuenta**
2. Cargue una lista de **categorías de cuentas** para agrupar las cuentas de mayor en grupos de alto nivel
3. Nota: El análisis de desviaciones se realiza a nivel de categoría de cuenta
4. **Publicar** los cambios

Paso 4: Asignar cuentas a categorías

1. Vaya a **Configuración → Datos de referencia → Cuentas**
2. En la columna **Categoría**, asigne cada **cuenta de mayor** a un **código de categoría de cuenta**
3. Importe la tabla de Cuentas actualizada y **publique** los cambios

Paso 5: Configurar el análisis de desviaciones para el plan

1. Abra su plan y vaya a **Análisis de desviaciones** en el menú de la izquierda
2. Haga clic en el **menú Elipses** → **Configurar análisis de varianza**
3. En el modal, configure los ajustes:

   |  |  |
   | --- | --- |
   | **Campo** | **Descripción** |
   | Comparar con el plan | Seleccione el plan de comparación. Todos los planes no archivados podrán seleccionarse.    Nota: Los Planes en estado NUEVO no serán visibles para los Propietarios de Centros de Coste. |
   | Período de comparación | Elija el periodo de tiempo (por ejemplo, último mes, último trimestre, año completo o personalizado) |
   | Alineación del plan | Alinee los planes haciendo **coincidir el año fiscal** o **el año de inicio del plan** |
   | Umbral de variación $ | **Diferencia monetaria** mínima que requiere explicación |
   | Operador | Seleccione Y u O para determinar cómo deben aplicarse los umbrales de desviación monetaria y porcentual:    Y - deben cumplirse ambos umbrales    O - basta con alcanzar cualquiera de los dos umbrales |
   | Varianza Umbral % | **Varianza porcentual** mínima que requiere explicación |

Paso 6: Generar el análisis

- Haga clic en **Vista previa** para revisar los resultados
- Haga clic en **Crear** para generar el análisis de varianza

Una vez creadas, las desviaciones que superen los umbrales se marcarán para que se expliquen y comenten.

## Ejecución de un análisis de varianza

Nota: El análisis de desviaciones sólo está disponible para los planes de tipo Previsión.

1. Abra su **plan de previsiones**.
2. Vaya a **Plan → Análisis de desviaciones** en el menú de navegación izquierdo.
3. En la tabla, busque las **banderas rojas de desviación**, que indican Categorías de cuentas en las que la desviación supera el umbral definido.
4. Seleccione una **Categoría de Cuenta** marcada para un Departamento específico para profundizar en los detalles de la desviación.
5. Utilice las pestañas **Resumen** y **Reales** para revisar la desviación como un gráfico en cascada y los detalles de las transacciones.
6. Asigne uno o varios **controladores de desviación** e introduzca una explicación de forma libre para la desviación.
7. Haga clic en la **X** para salir de la vista detallada de desviaciones.
8. Una vez que todas las desviaciones tengan asignados controladores y explicaciones, la **bandera de estado se volverá verde**.

## Editar la configuración del análisis de desviaciones

Nota: Se requieren los roles de Administrador o Propietario del Proceso Presupuestario para editar la configuración del Análisis de Desviaciones.

**Actualizar umbrales o ajustes de comparación**

1. Haga clic en el **menú Elipses** de la página Análisis de varianza
2. Seleccione **Configurar análisis de varianza**
3. Ajuste la configuración (plano, alineación, umbrales, etc.)
4. Haga clic en **Actualizar** para aplicar los cambios

Importante: La actualización de la configuración eliminará todas las explicaciones de desviaciones existentes.

**Actualizar las desviaciones de las previsiones activas**

Si está comparando contra periodos de previsión (por ejemplo, comparación de todo el año entre dos planes), puede que necesite actualizar los valores de desviación cuando cambien los datos del plan.

1. Haga clic en el **menú Elipses**
2. Seleccione **Actualizar análisis de desviaciones**
3. El cuadro de diálogo mostrará qué partidas deben actualizarse junto con la fecha de la última actualización
4. Haga clic en **Actualizar** para volver a calcular la tabla de desviaciones utilizando los últimos valores de previsión.

Importante: La actualización del análisis puede eliminar los factores de desviación y las explicaciones si dichas desviaciones han cambiado.

## Exportación e informes

- En el menú **Acciones** de la página Análisis de desviaciones puede seleccionar **Exportar comentario de desviaciones** para exportarlo a csv. La exportación incluye todos los controladores, comentarios y registros de desviaciones.
- En el **panel de control**, vaya a *Desviaciones de gastos* para ver un mapa de árbol y un desglose por controladores y departamentos.
