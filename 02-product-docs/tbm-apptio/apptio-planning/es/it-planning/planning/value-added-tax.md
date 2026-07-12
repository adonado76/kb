---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Impuesto sobre el Valor Añadido"
breadcrumb:
  - "Planning"
  - "Planificación de contratos"
source_path: "it-planning/planning/value-added-tax.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Impuesto sobre el Valor Añadido

Apptio La planificación admite la modelización **del Impuesto sobre el Valor Añadido (IVA)** para las partidas de los contratos, lo que permite a las organizaciones representar con precisión el gasto total de los contratos, con o sin impuestos. El IVA es un impuesto sobre el consumo que se aplica a bienes y servicios y, dependiendo de las políticas contables de su organización, puede ser recuperable o no recuperable.

Esta función permite a los usuarios:

- Incluya el IVA como parte de los costes totales del contrato.
- Haga un seguimiento del IVA separado del importe base del contrato.
- Configure cómo debe calcularse y mostrarse el IVA en las partidas del contrato.

## Conceptos clave

**Importe**

Representa el coste antes de impuestos del contrato o partida (por ejemplo, cuota de suscripción de software, arrendamiento de hardware).

**Tipo del IVA**

Especifica el porcentaje de impuestos aplicado al importe base.

Ejemplos:

- 0% - No imponible
- 10% - Tipo reducido de IVA (por ejemplo, determinados servicios)
- 20% - Tipo normal del IVA

**Importe con IVA**

Representa el coste total, IVA incluido.

Calculado como: **Importe con IVA=** Importe + (Importe × Tipo de IVA)

## Cómo se calcula el IVA

El IVA se calcula en función de la **Localización** seleccionada en cada partida del contrato:

- Cuando se introduce una partida contractual y se especifica una **Ubicación**,
- Apptio Planificación buscará **el tipo de IVA** en la tabla de datos de referencia,
- Y calcular automáticamente el **Importe con IVA** (calculado como: *Importe + (Importe × Tipo de IVA)* )
- El IVA no se amortiza: sólo se utiliza para la amortización el importe original (antes del IVA).

Ejemplo

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Nombre de contrato** | **Importe del contrato** | **Tipo del IVA** | **Importe del IVA** | **Importe con IVA** |
| Licencia de software | 10 000 dólares | 20 % | 2000 dólares | 12 000 dólares |
| Contrato de mantenimiento | 8000 dólares | 10 % | 800 dólares | 8.800 dólares |
| Servicios de consultoría | 5000 dólares | 0 % | $0 | 5000 dólares |

## Configurar el Impuesto sobre el Valor Añadido

Para activar los cálculos del IVA, vaya a **Configuración → Perfil de empresa** y active la opción **Incluir impuesto sobre el valor añadido (IVA)**. Al activar esta opción, se creará automáticamente una tabla de datos de referencia **de tipos de IVA**.

**Pasos de configuración**

**Antes de importar los tipos de IVA**, asegúrese de que sus **datos de referencia de ubicación** incluyen todas las ubicaciones pertinentes en las que debe aplicarse el IVA.

1. Vaya a **Ajustes** (icono de engranaje) **→ Perfil de empresa**.
2. Active **Incluir el Impuesto sobre el Valor Añadido (IVA)** y haga clic en **Guardar y Salir**.
3. Navegue hasta **Configuración → Datos de referencia → Tipos de IVA**.
4. Exporte la plantilla y rellene los campos clave:
5. **Localización** - El identificador de localización utilizado para determinar el tipo de IVA aplicable.
6. **Tipo de IVA** - El tipo impositivo a aplicar, introducido como decimal (por ejemplo, introduzca 0.20 para un 20%).
7. Importar el CSV actualizado
8. Haga clic en el **menú Elipses** y **Publique** los cambios para que estén disponibles para los planes.

**Aplicar el IVA a las partidas contractuales**

Al introducir o importar datos contractuales:

1. Especifique el **importe** del contrato para cada partida.
2. Seleccione una **ubicación.**
3. El **tipo de IVA** se rellena automáticamente en función de los tipos de IVA configurados.
4. Apptio La planificación calcula automáticamente el **importe con IVA** **.**
