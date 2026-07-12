---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Tipos de actos"
breadcrumb:
  - "Planning"
  - "Flujos de trabajo y colaboración"
  - "Historial de cambios"
source_path: "it-planning/planning/event-types.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Tipos de actos

El historial de cambios captura una amplia gama de eventos del sistema en Apptio Planning, permitiéndole revisar quién hizo qué, cuándo y cómo. Cada evento se clasifica por tipo, área, contenedor, tipo de elemento y cambios de atributo.

Nota: Para acceder al Historial de Cambios se requieren los roles de Administrador o Propietario del Proceso Presupuestario.

A continuación se resumen las principales categorías de actos.

## 1. Planificar eventos de gestión.

Se refieren a cambios importantes en el ciclo de vida del plan.

- **Crear plan** - Se ha creado un nuevo plan.
- **Renombrar plan** - Se ha cambiado el nombre del plan (nombre antiguo → nombre nuevo).
- **Eliminar** plano - Se ha eliminado un plano.
- **Archivar/Restablecer plan** - El plan se archivó o se restableció.
- **Finalizar/Reabrir plan** - Un plan pasa al estado Final o vuelve al estado Abierto.
- **Enviar/Aprobar/Rechazar Objeto** de Coste - Cambios de estado para departamentos individuales u objetos de coste.

## 2. Eventos por partidas

Estos eventos rastrean los cambios en líneas individuales de su plan.

- **Añadir partida** - Se ha añadido una nueva partida.
- **Actualizar partida** - Se ha actualizado una partida existente (muestra los valores "antes" y "después").
- **Eliminar partida** - Se ha eliminado una partida.
- **Importar/Exportar Partidas** - Acciones de carga o descarga masiva.

## 3. Hechos reales y gestión de gastos

Estos capturan la importación/exportación de datos reales y las operaciones de gestión de gastos.

- **Importar reales** - Los datos reales se han cargado en un plan.
- **Exportar** reales - Los datos reales se exportaron para informes o integración.

## 4. Eventos de configuración y datos de referencia

Se refieren a cambios en el modelo o la configuración de los datos subyacentes.

- **Añadir/actualizar/eliminar configuración de columna** - Se ha añadido/modificado/eliminado una columna de diseño o esquema.
- **Cambiar identificador** : operación de búsqueda y sustitución de un código o identificador de dimensión en los planos.
- **Publicar/Revertir/Importar/Exportar Datos de Referencia** - Acciones tomadas en dimensiones como Departamentos, Cuentas, Clases de Activos, etc.
- **Añadir/Actualizar/Borrar Listas o Dimensiones Personalizadas** - Modificaciones de las estructuras de dimensiones personalizadas.

**Tema principal:** [Historial de cambios](../../it-planning/planning/change-history.html "El historial de cambios proporciona una pista de auditoría de las acciones clave realizadas en su entorno de planificación. Permite a las organizaciones mantener la transparencia, respaldar los requisitos de cumplimiento y solucionar problemas de planificación mediante el seguimiento de quién ha cambiado qué, cuándo y cómo.")
