---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Administración de proyectos"
breadcrumb:
  - "TBM Studio"
  - "Administración"
source_path: "studio/new-uc/admin/project-admin.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Administración de proyectos

**Tipo de contenido:** Conceptual / Guía práctica

**Destinatarios:** Administradores, usuarios avanzados

**Requisitos previos:** rol de administrador o de usuario avanzado, acceso a la pestaña «Proyecto»

La administración de proyectos abarca todas las actividades relacionadas con la creación, la configuración y el mantenimiento de los proyectos de TBM Studio. Esto incluye crear proyectos, configurar los ajustes de tiempo, gestionar la configuración de todo el dominio y establecer políticas de gobernanza.

## Comprender los proyectos

Los proyectos son la unidad organizativa básica de TBM Studio. Un proyecto agrupa conjuntos de datos, métricas, modelos e informes en un espacio de trabajo integrado. Cada proyecto tiene su propia configuración, ajustes de tiempo y permisos de usuario.

**Características principales del proyecto:**

- Los proyectos contienen todas las tablas de datos, transformaciones, objetos de modelo, métricas e informes
- Cada proyecto tiene una configuración temporal independiente, en la que se definen el calendario fiscal y los periodos activos
- Los proyectos pueden basarse en plantillas estándar (modelo de cálculo de costes) o en configuraciones personalizadas
- En un mismo dominio pueden coexistir varios proyectos
- En la aplicación solo se puede tener abierto un proyecto a la vez

**Nota:** *Solo los administradores del sistema pueden crear o eliminar proyectos. Póngase en contacto con el administrador del sistema de Apptio si necesita crear un nuevo proyecto o eliminar uno ya existente.*

## Configuración de los ajustes del proyecto

La configuración del proyecto controla el comportamiento a nivel de proyecto en lo que respecta a los cálculos, el formato y la presentación. Accede a la configuración del proyecto desde la pestaña «Proyecto» haciendo clic en «Configuración del proyecto» en el grupo «Configuración del proyecto».

**Configuración clave del proyecto:**

|  |  |
| --- | --- |
| **Valor** | **Descripción** |
| **Moneda base** | Moneda predeterminada para mostrar los valores en los informes. Los usuarios pueden modificar esta configuración en su perfil. |
| **Entorno local** | Establece los formatos de números, moneda y fecha que se utilizarán en todo el proyecto. |
| **Compactación de números** | Abreviaturas para miles (K), millones (M), miles de millones (B) y billones (T). |
| **Versión de los componentes** | Especifica qué versión del contenido se debe utilizar para las actualizaciones e instalaciones de componentes. |
| **Calcular automáticamente** | Cuando está activada, la aplicación actualiza automáticamente los documentos tras guardarlos. Desactiva esta opción en proyectos de gran tamaño para mejorar el rendimiento. |
| **Descripciones de los registros obligatorios** | Obliga a los usuarios a introducir una descripción con cada registro. Recomendado para registros de auditoría. |

**Consejo:** *En proyectos con bases de datos de gran tamaño cuyos cálculos requieran mucho tiempo, desactiva el cálculo automático y permite que los usuarios activen manualmente las actualizaciones cuando sea necesario.*

## Configuración de los ajustes de hora

La configuración de fechas define el calendario fiscal, controla qué periodos están activos y determina qué periodos de datos ven los usuarios de forma predeterminada. Configurar correctamente los ajustes de hora es fundamental para obtener informes precisos y un rendimiento óptimo.

**Para configurar los ajustes de hora:**

1. Ve a **Proyecto > Configuración de tiempo**.
2. Configure la definición del ejercicio fiscal (calendario gregoriano, 13 períodos o variante personalizada 4-5-4).
3. Establezca las fechas de inicio y finalización del proyecto para definir el periodo de cálculo.
4. Configura el periodo de tiempo predeterminado que verán los usuarios al abrir los informes.
5. Defina los períodos cerrados para impedir que se modifiquen los datos de los períodos ya cerrados.

**Advertencia:** *Una vez que actives el seguimiento del tiempo para un proyecto, no podrás desactivarlo. La fecha de inicio del proyecto no se puede modificar una vez realizada la configuración inicial. Planifica bien tu horario antes de comprometerte.*

**Prácticas recomendadas para la configuración de la hora**

- Establezca el periodo predeterminado en el último mes completamente cerrado para garantizar que los usuarios vean datos validados.
- Cierre los periodos una vez que se hayan validado los datos para evitar modificaciones accidentales.
- Limita las fechas de inicio y finalización del proyecto únicamente a los periodos necesarios para mejorar el rendimiento de los cálculos.
- Actualiza el período predeterminado una vez finalizado el cierre de cada fin de mes.

## Configuración del dominio

La configuración del dominio controla los ajustes generales del entorno que se aplican a todos los proyectos de tu instancia de Apptio. Accede a la configuración del dominio desde la pestaña «Proyecto» haciendo clic en «Configuración del dominio».

**Entre los ajustes clave del dominio se incluyen:**

- **Proyecto predeterminado** : el proyecto que se abre cuando los usuarios inician sesión sin especificar un proyecto
- **Servicio multidivisa** : gestión centralizada del cambio de divisas en todos los productos de Apptio
- **Servicio de calendario fiscal** : definiciones de calendario fiscal compartidas entre productos

## Activación de funciones opcionales

TBM Studio ofrece varias funciones opcionales que se pueden activar en función de las necesidades de su organización. Accede a ellas desde la pestaña «Proyecto» haciendo clic en «Habilitar funciones».

|  |  |
| --- | --- |
| **Característica** | **Descripción** |
| Gestión de prioridades de cálculo | Prioriza los cálculos en los distintos proyectos según su importancia o urgencia |
| Gestión de Calc | Activar/desactivar los cálculos de preparación a nivel de proyecto |
| Publicación periódica | Programar la publicación automática de datos de tablas editables en transformaciones |
| Mostrar documentos no utilizados | Identificar tablas, métricas e informes que no se utilizan en ninguna parte del proyecto |
| Mostrar el panel de anomalías | Detección de anomalías en la visualización de patrones de cálculo inusuales |
| Interfaz de usuario de Apex | Habilita la interfaz de usuario modernizada |
