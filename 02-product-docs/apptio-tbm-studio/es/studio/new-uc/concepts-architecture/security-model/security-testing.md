---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Pruebas y validación de seguridad"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Buenas prácticas de seguridad"
source_path: "studio/new-uc/concepts-architecture/security-model/security-testing.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Pruebas y validación de seguridad

Comprobar que la configuración de seguridad es correcta es tan importante como configurarla en primer lugar. Utiliza estas técnicas para asegurarte de que tus medidas de seguridad funcionen como es debido.

**Técnicas de evaluación**

1. **Filtro de vista previa:** En el paso del proceso de RLS, utiliza el filtro de vista previa para introducir el correo electrónico de un usuario y ver exactamente qué filas vería en una tabla concreta.
2. **Suplantación de identidad de usuario:** Los administradores pueden suplantar la identidad de cualquier usuario para ver informes y tablas desde la perspectiva de dicho usuario. Esto comprueba el conjunto completo: roles, permisos de informes y RLS.
3. **Cambio de rol:** Si dispone de varios roles, cambie entre ellos para comprobar que la visibilidad de los informes y el acceso a los componentes varían según lo esperado. Recuerda actualizar el navegador después de cambiar.
4. **Validación de informes cruzados:** Tras configurar RLS, abra todos los informes que utilicen los datos protegidos para comprobar que el filtrado funciona correctamente, incluidos los destinos de desglose.

**Errores comunes de configuración de seguridad**

|  |  |  |
| --- | --- | --- |
| **Configuración errónea** | **Riesgo** | **Prevención** |
| RLS se aplica a las tablas de resumen, pero no a las de detalle | Los usuarios ven resúmenes filtrados, pero los datos sin filtrar cuando profundizan en los datos | Aplica RLS a todas las tablas a las que se pueda acceder mediante la navegación de desglose |
| Utilización de RLS para usuarios con privilegios de administrador | Los usuarios con privilegios de administrador pueden eludir RLS mediante el modo Studio | Utiliza el rol de administrador solo para aquellos usuarios que realmente necesiten acceso completo al sistema |
| Falta el RLS en un paso del modelo | Los datos son visibles en un nivel, pero no en otros, lo que da lugar a vistas incoherentes | Añade un paso RLS a cada paso del modelo en el proceso que requiera filtrado |
| La tabla de asignación no se actualiza tras los cambios en la organización | Los nuevos empleados o los empleados trasladados ven datos erróneos | Establecer un proceso para actualizar las tablas de correspondencias cada vez que se produzcan cambios organizativos |
| Cuentas de API con permisos excesivos | Los procesos automatizados tienen un acceso más amplio del necesario | Crea roles personalizados específicos para cuentas de API con permisos mínimos |

**Tema principal:** [Prácticas recomendadas de seguridad](../../../../studio/new-uc/concepts-architecture/security-model/security-best-practices.html)
