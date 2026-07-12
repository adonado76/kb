---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Buenas prácticas en materia de permisos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Permisos del informe"
source_path: "studio/new-uc/reference/report-studio-reference/permission-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Buenas prácticas en materia de permisos

**Patrones de diseño de permisos**

**Modelo 1: Acceso general con filtrado RLS**

- Establecer los permisos de informe en «Todos»
- Utiliza RLS para filtrar los datos confidenciales por usuario
- Simplifica la gestión de permisos sin comprometer la seguridad de los datos

**Modelo 2: Informes segmentados por funciones**

- Crea informes independientes para cada público
- Configurar cada informe para roles específicos
- Ofrece experiencias personalizadas, pero aumenta el mantenimiento

**Patrón 3: Informe único con visibilidad de componentes**

- Crea un informe dirigido a varios públicos
- Utiliza la visibilidad de los componentes para mostrar u ocultar elementos según su función
- Reduce el número de informes y ofrece vistas adaptadas a cada función

**Patrón 4: Organización basada en colecciones**

- Informes de grupos por público en las colecciones
- Configurar permisos a nivel de colección
- Los informes heredan la configuración de la colección, lo que reduce la necesidad de configuraciones individuales

**Principio del privilegio mínimo**

Aplique el principio del mínimo privilegio al configurar los permisos de los informes:

1. **Empieza con restricciones:** comienza con un acceso limitado y amplíalo según sea necesario
2. **Utiliza roles específicos:** evita conceder acceso a «Todos» a menos que sea realmente necesario
3. **Seguridad por capas:** combina los permisos de los informes con RLS para los datos confidenciales
4. **Revisión periódica:** comprueba periódicamente quién tiene acceso a los informes confidenciales

**Tema principal:** [Permisos de informes](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
