---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Problemas de acceso y navegación"
breadcrumb:
  - "Benchmarking"
  - "Informes comparativos"
  - "Solución de problemas y preguntas frecuentes"
source_path: "it-benchmarking/troubleshooting/access-navigation-issues.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Problemas de acceso y navegación

**El usuario no puede ver la comparativa interactiva en la navegación.**

Síntoma  
: El usuario inicia sesión en Frontdoor y no ve la aplicación o el mosaico Benchmarking. De lo contrario, es posible que el usuario esté intentando acceder a Benchmarking desde Costing u otro producto de IBM Apptio a través de la navegación dentro de la   
aplicación. Posibles causas

- Benchmarking no proporcionado a su empresa
- El rol de usuario no incluye acceso al punto final de evaluación comparativa interactiva
- El rol de usuario no incluye el permiso « “ViewInteractiveBenchmarksAndCostData” ».
- Usuario en el entorno incorrecto (por ejemplo, «sandbox» en lugar de «main»)

Qué hay que comprobar

1. Confirme que Benchmarking está provisionado para su empresa.
2. Comprueba qué roles incluyen acceso a Interactive Benchmarking y si el usuario tiene alguno de ellos.
3. Comprueba que la función asignada tiene el permiso « “ViewInteractiveBenchmarksAndCostData” » (Crear y eliminar reglas de control de acceso).
4. Verifique que el usuario haya iniciado sesión en el entorno Frontdoor correcto.

Respuesta breve que puede enviar  
: No ve Benchmarking porque sus permisos de usuario no tienen acceso a esa aplicación en este entorno. Una vez que se le haya concedido el rol adecuado, la aplicación Benchmarking aparecerá en su navegación.

**El usuario puede abrir Costing, pero no puede acceder a los informes de Benchmarking.**

Síntoma  
: el usuario ve la página de inicio de Costing, pero faltan algunos mosaicos o informes específicos de Benchmarking o dan error.   
Posibles causas

- El usuario no tiene acceso a los informes **de costes** subyacentes
- El informe ha sido eliminado, renombrado o movido
- El acceso basado en roles para ese informe es más restrictivo
- Los componentes de benchmarking no se instalaron en el proyecto Costing

Qué hay que comprobar

1. Abra el informe usted mismo para verificar que existe y funciona.
2. Confirme de qué proyecto de cálculo de costes depende y si el usuario puede acceder a ese proyecto.
3. Comprueba los permisos a nivel de informe o de carpeta.
4. Compruebe que los componentes «IT Spend Benchmarks» y, si procede, «Infra Benchmarks» estén instalados.

Respuesta breve que puede enviar  
: Puede acceder a Costing, pero su función actual no tiene acceso o el informe no está disponible. Una vez que se conceda el acceso y el informe esté disponible, este aparecerá.
