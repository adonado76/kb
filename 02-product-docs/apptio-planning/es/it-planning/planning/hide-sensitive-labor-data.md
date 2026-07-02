---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Ocultar datos laborales sensibles"
breadcrumb:
  - "Planning"
  - "Planificación laboral"
source_path: "it-planning/planning/hide-sensitive-labor-data.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Ocultar datos laborales sensibles

Los administradores pueden restringir la visibilidad de columnas específicas en la pestaña Mano de Obra -como el nombre del empleado, el salario u otros detalles de compensación- para que los usuarios sin el permiso requerido puedan ver las entradas de mano de obra sin ver los campos sensibles.

Nota: Para configurar datos confidenciales se requieren los roles de Administrador o Propietario de Proceso Presupuestario.

**Por qué utilizarlo**

- Proteja la confidencialidad de los empleados al tiempo que permite a los propietarios de los centros de costes revisar los costes relacionados con la mano de obra en todos los departamentos.
- Garantice el cumplimiento de las políticas internas de privacidad o RRHH ocultando detalles sensibles de la remuneración a públicos más amplios.
- Permitir la planificación financiera colaborativa sin exponer la información individual sobre salarios o primas.

## Cómo funciona

1. Los datos laborales son visibles para los usuarios en función de sus permisos y del acceso a los objetos de coste.
2. Las columnas marcadas como *Datos Sensibles* en el esquema laboral (como *Nombre del Empleado*, *Remuneración Base*, *Otra Remuneración* ) pueden ocultarse para los usuarios que carezcan del permiso **Ver Columnas Sensibles** o **Ver Finanzas Sensibles**.
3. Los usuarios sin permiso verán las partidas de mano de obra, pero las columnas sensibles quedarán ocultas, mientras que el resto de la información de costes (por ejemplo, función, cantidad, centro de coste, coste totalmente cargado) permanece visible.
4. Los administradores gestionan qué columnas se marcan como sensibles a través de **Configuración → Esquema → Labor.**
5. Los Permisos de Objeto de Coste determinan la visibilidad de los datos laborales sensibles a través de los siguientes ajustes:
   1. **Ver columnas confidenciales** : permite a los usuarios ver y editar los atributos marcados como *datos confidenciales* en la pestaña Mano de obra.
   2. **Ver finanzas sensibles** - Permite a los usuarios ver las finanzas laborales generadas en la pestaña Resumen.

## Instrucciones de instalación

**1. Marcar columnas sensibles**

1. Vaya a **Configuración → Esquema → Trabajo**.
2. Seleccione los atributos que contienen datos privados (por ejemplo, *Nombre del empleado*, *Remuneración base* ).
3. Active la casilla **Datos sensibles**.
4. Guarde los cambios del esquema.

***2. Asignar permisos de objetos de coste***

1. Vaya a **Configuración → Permisos de objetos de coste**.
2. Para cada departamento, asigne visibilidad concediendo uno o ambos de los siguientes permisos:
3. **Ver Columnas Sens** ibles - Para ver o editar datos sensibles de mano de obra en la pestaña Mano de Obra.
4. **Ver** Finanzas Sensibles - Para ver las finanzas laborales sensibles en la pestaña Resumen.
5. Los usuarios sin estos permisos no verán las columnas sensibles en la pestaña Mano de Obra ni las finanzas laborales relacionadas en la pestaña Resumen.

***3. Verificar el comportamiento***

1. Hacerse pasar por un usuario sin acceso a datos sensibles.
2. Abra un plan y navegue hasta **Gastos → Mano de obra**.
3. Confírmalo:
4. Las líneas de trabajo están visibles, pero las columnas sensibles (por ejemplo, *Nombre del empleado*, *Remuneración base* ) están ocultas.
5. La **pestaña Resumen** no muestra detalles financieros laborales sensibles.

Para más información, consulte [Preguntas frecuentes: Ocultar datos laborales sensibles](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=planning-faq-hide-sensitive-labor-data "(se abre en una pestaña o una ventana nueva)").
