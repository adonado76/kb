---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar dispositivos de usuario final"
breadcrumb: []
source_path: "studio/reports/component_end_user_devices.html"
images:
  - "resources/images/studio_images/eud-1.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar dispositivos de usuario final

Siga estos pasos para empezar a utilizar los dispositivos de usuario final:

## Instale el componente Dispositivos de usuario final

1. Crear un proyecto en TBM Studio.
2. Vaya a Proyecto > Habilitar funciones y compruebe que el administrador de soporte de Apptio o el CSM de Apptio han habilitado Plantillas y módulos (Beta).

   Nota: Para las versiones R12.10.0 a R12.10.7, la opción **Plantillas y módulos (Beta)** debe estar activada. Una vez activada esta opción, podrá instalar el componente "Dispositivos de usuario final". A partir de la versión R12.10.8, End User Devices es GA y este componente está disponible sin ninguna habilitación de funciones.
3. Vaya a Proyecto > Componentes, desplácese hasta la lista de Funciones disponibles e instale Dispositivos de usuario final en el proyecto.
   - Para los clientes con formato de fecha (dd/MM/yyyy), vaya a editar la configuración del proyecto y asegúrese de que "Locale" está configurado como "United Kingdom".
   - Para los clientes con formato de fecha (MM/dd/aaaa), vaya a Editar configuración del proyecto y asegúrese de que la "Configuración regional" está establecida en "Estados Unidos".
4. Existen principalmente tres conjuntos de datos necesarios para configurar los Dispositivos de Usuario Final. Prepare los datos en forma tabular para las siguientes tablas de su proyecto:
   - Active Directory datos
   - Datos laborales
   - Datos de los dispositivos de usuario final
5. Asigne estas tablas a las siguientes tablas maestras. Para más información, consulte [Cargar datos](../data%20studio/upload-data.html) y [Columnas del mapa](../data%20studio/mapcolumns.html).

| Tabla creada | Tabla maestra (presente en Tablas) |
| --- | --- |
| Active Directory datos | EUI Active Directory Datos maestros |
| Datos laborales | EUI Datos maestros de mano de obra |
| Datos de los dispositivos de usuario final | Entrada del dispositivo del usuario final |

Las siguientes tablas se crean automáticamente cuando se instala el componente, y pueden verse en la lista **Tablas** :

- Entrada de términos EOL y EOW del dispositivo
- Estimación del dispositivo Coste de actualización
- Usuario Final Dispositivo En Stock Estado Definición Entrada
- Usuario final Dispositivo Versión SO Entrada de referencia
- Entrada de la exención del usuario final

Debe cargar datos en estas tablas. Para más información, consulta [Cargar datos](../data%20studio/upload-data.html).

Nota: Cargue los datos en las tablas maestras de entrada cuando se produzcan cambios o cuando haya una actualización mensual. Esto garantiza la exactitud de los informes.

## Detalles del componente

| Nombre de tabla | Tipo |
| --- | --- |
| Active Directory | Tabla de entrada (Tabla a crear y datos a cargar) |
| DISPOSITIVOS DE USUARIO FINAL | Tabla de entrada (Tabla a crear y datos a cargar) |
| DATOS LABORALES | Tabla de entrada (Tabla a crear y datos a cargar) |
| Entrada de términos EOL y EOW del dispositivo | Tabla de entrada |
| Estimación del dispositivo Coste de actualización | Tabla de entrada |
| Usuario Final Dispositivo En Stock Estado Definición Entrada | Tabla de entrada |
| Usuario final Dispositivo Versión SO Entrada de referencia | Tabla de entrada |
| Entrada de la exención del usuario final | Tabla de entrada |
| Término EOL y EOW del dispositivo | Mesa principal |
| Dispositivo Estimación del coste de actualización | Mesa principal |
| Definición del estado de existencias del dispositivo del usuario final | Mesa principal |
| Referencia de la versión del sistema operativo del dispositivo del usuario final | Mesa principal |
| Exención para usuarios finales | Mesa principal |
| Visión del usuario final Datos maestros | Mesa principal |
| Entrada del dispositivo del usuario final | Mesa principal |
| EUI Active Directory Datos maestros | Mesa principal |
| EUI Datos maestros de mano de obra | Mesa principal |
| Referencia de la versión del SO para el usuario final | Mesa principal |
| Secuencia de clasificación de informes EOL EOW | Referencia/Tabla de consulta |
| Ayuda para los periodos EOL y EOW | Referencia/Tabla de consulta |
| Rango de edad del usuario final Tablematch | Referencia/Tabla de consulta |
| Secuencia del informe | Referencia/Tabla de consulta |
| Perspectivas de los usuarios finales Puesta en escena previa | Tabla normal/Tabla de transición |
| Perspectiva del usuario final Datos maestros previos | Tabla normal/Tabla de transición |
| Información para el usuario final Referencia editable | Mesa transformada |

Consejo: Dispositivos de Usuario Final soporta multidivisa.

## Configure los ajustes para el modelo de Dispositivos de Usuario Final

1. Cree tablas de entrada y cargue los datos periódicamente (preferiblemente una vez al mes) y asigne todos los datos necesarios a las tablas maestras existentes. Consulte [Instalar el componente Dispositivos de usuario final](#ConfigureEndUserDevices__InstalltheEndUserDevicescomponent) para obtener más información.
2. Asigne los datos laborales y de directorio en los Datos Maestros Laborales EUI y en los Datos Maestros EUI Active Directory respectivamente. Consulte [Instalar el componente Dispositivos de usuario final](#ConfigureEndUserDevices__InstalltheEndUserDevicescomponent) para obtener más información.
3. Configure sus tablas de entrada en tablas maestras utilizando las fórmulas que se indican a continuación. Si el paso Fórmulas no aparece, añádalo utilizando la opción Añadir paso.

   Consejo: Las fórmulas que figuran a continuación son sólo datos de referencia. Puede actualizar las fórmulas según sus datos específicos y las normas del sector.

   Para clientes con formato de fecha dd/MM/aaaa
   :   - Actualice la siguiente columna para **Active Directory** :

         | Nombre de columna | Tipo | Formato | Fórmula |
         | --- | --- | --- | --- |
         | Última hora de inicio de sesión | Fecha | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |
       - Cree y actualice las siguientes columnas para **Dispositivos de Usuario Final** :

         | Nombre de columna | Tipo | Formato | Fórmula |
         | --- | --- | --- | --- |
         | Unidad de negocio | Etiqueta |  | =Lookup(ID de empleado,EUI Datos maestros de trabajo,ID de empleado,Unidad de negocio) |
         | Propietario de la Unidad de Negocio | Etiqueta |  | =Lookup(ID de empleado,EUI Datos maestros de trabajo,ID de empleado,Propietario de unidad de negocio) |
         | Comprobación CC | Etiqueta |  | =Lookup(ID empleado,EUI Datos maestros trabajo,ID empleado,Centro coste) |
         | Centro de costes | Etiqueta |  | =IF( {CC Check}!="",Lookup(ID del empleado,EUI Datos maestros de trabajo,ID del empleado,Descripción del centro de coste)&" ("&Lookup(ID del empleado,ACME LAB,ID del empleado,Centro de coste)&")","") |
         | Propietario del centro de costes | Etiqueta |  | =Lookup(ID empleado,EUI Datos maestros trabajo,ID empleado,Propietario centro coste) |
         | Departamento | Etiqueta |  | =Lookup(ID empleado,EUI Datos maestros trabajo,ID empleado,Descripción centro coste) |
         | Número de dispositivos | Numérico |  | =1 |
         | Existencias | Etiqueta |  | =Lookup(Estado inventario,Dispositivo usuario final En definición estado stock,En lista estado stock,En lista estado stock) |
         | SO | Etiqueta |  | =Lookup(ID de activo,EUI Active Directory Datos maestros,ID de activo,OS) |
         | Versión de SO | Etiqueta |  | =Lookup(ID activo,EUI Active Directory Datos maestros,ID activo,Versión SO) |
         | Fuente Tabla | Etiqueta |  | ="Dispositivos de usuario final en bruto" |
         | Nombre de usuario HR | Etiqueta |  | =Lookup(ID empleado,EUI Datos maestros trabajo,ID empleado,Nombre empleado) |
         | Fecha de adquisición | Fecha | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |
         | Fecha de fin de vida útil | Fecha | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |
         | Fecha de actualización | Fecha | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |
         | Nombre de usuario | Etiqueta |  | =if($\_!="",$\_,If( {User Name HR} ="" AND {In Stock Inventory} ="", "ID de empleado no encontrado", {User Name HR} )) |
         | Fecha de finalización de la garantía | Fecha | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |
         | Fecha de inicio de la garantía | Fecha | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |

         ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/eud-1.png)

         ![imagen](../../resources/images/studio_images/eud-2_913x453.png)
       - Actualice las siguientes columnas para **Datos Laborales** :

         | Nombre de columna | Tipo | Formato | Fórmula |
         | --- | --- | --- | --- |
         | Centro de costes e ID | Etiqueta |  | =Descripción del centro de coste&&Centro de coste |
         | Fecha de finalización | Fecha | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |
         | Fecha de inicio | Fecha | dd/MM/aaaa | =DateFormat($\_,"dd/MM/yyyy") |

         ![imagen](../../resources/images/studio_images/eud-3_913x458.png)

   Para clientes con formato de fecha MM/dd/aaaa
   :   - Actualice la siguiente columna para **Active Directory** :

         | Nombre de columna | Tipo | Formato | Fórmula |
         | --- | --- | --- | --- |
         | Última hora de inicio de sesión | Fecha | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |
       - Cree y actualice las siguientes columnas para **Dispositivos de Usuario Final** :

         | Nombre de columna | Tipo | Formato | Fórmula |
         | --- | --- | --- | --- |
         | Unidad de negocio | Etiqueta |  | =Lookup(ID de empleado,EUI Datos maestros de trabajo,ID de empleado,Unidad de negocio) |
         | Propietario de la Unidad de Negocio | Etiqueta |  | =Lookup(ID de empleado,EUI Datos maestros de trabajo,ID de empleado,Propietario de unidad de negocio) |
         | Comprobación CC | Etiqueta |  | =Lookup(ID empleado,EUI Datos maestros trabajo,ID empleado,Centro coste) |
         | Centro de costes | Etiqueta |  | =IF( {CC Check}!="",Lookup(ID del empleado,EUI Datos maestros de trabajo,ID del empleado,Descripción del centro de coste)&" ("&Lookup(ID del empleado,ACME LAB,ID del empleado,Centro de coste)&")","") |
         | Propietario del centro de costes | Etiqueta |  | =Lookup(ID empleado,EUI Datos maestros trabajo,ID empleado,Propietario centro coste) |
         | Departamento | Etiqueta |  | =Lookup(ID empleado,EUI Datos maestros trabajo,ID empleado,Descripción centro coste) |
         | Número de dispositivos | Numérico |  | =1 |
         | Existencias | Etiqueta |  | =Lookup(Estado inventario,Dispositivo usuario final En definición estado stock,En lista estado stock,En lista estado stock) |
         | SO | Etiqueta |  | =Lookup(ID de activo,EUI Active Directory Datos maestros,ID de activo,OS) |
         | Versión de SO | Etiqueta |  | =Lookup(ID activo,EUI Active Directory Datos maestros,ID activo,Versión SO) |
         | Fuente Tabla | Etiqueta |  | ="Dispositivos de usuario final en bruto" |
         | Nombre de usuario HR | Etiqueta |  | =Lookup(ID empleado,EUI Datos maestros trabajo,ID empleado,Nombre empleado) |
         | Fecha de adquisición | Fecha | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |
         | Fecha de fin de vida útil | Fecha | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |
         | Fecha de actualización | Fecha | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |
         | Nombre de usuario | Etiqueta |  | =if($\_!="",$\_,If( {User Name HR} ="" AND {In Stock Inventory} ="", "ID de empleado no encontrado", {User Name HR} )) |
         | Fecha de finalización de la garantía | Fecha | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |
         | Fecha de inicio de la garantía | Fecha | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |

         ![imagen](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_1.png)
       - Actualice las siguientes columnas para **Datos Laborales** :

         | Nombre de columna | Tipo | Formato | Fórmula |
         | --- | --- | --- | --- |
         | Centro de costes e ID | Etiqueta |  | =Descripción del centro de coste&&Centro de coste |
         | Fecha de finalización | Fecha | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |
         | Fecha de inicio | Fecha | MM/dd/aaaa | =DateFormat($\_,"MM/dd/yyyy") |

         ![imagen](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_2_762x592.png)
4. Asigne **datos de los dispositivos del usuario final** a **la entrada del dispositivo del usuario final** agregándolos. Para más información, consulte [Añadir datos](../data%20studio/append-data.html).

   ![imagen](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_3_821x505.png)
5. Si las columnas tienen una columna de fecha, compruebe el formato y establezca el formato de fecha para todas las tablas de datos maestros o, al cargar los datos, asegúrese de establecer el tipo de datos de anulación de esas columnas en el formato que desee.
6. Si hay algunas fechas codificadas en la tabla maestra, por favor, cambie el formato según sus necesidades.
7. Compruebe los datos premaestros de End User Insights para confirmar si todos los datos proceden de **End User Device Input**.
8. Consulte **la etapa preliminar de pre-maestría de End User Insights** para confirmar si todos los datos y fórmulas provienen de **los datos preliminares de End User Insights**.
9. Compruebe **End User Insights Master Data** para confirmar el flujo de datos desde **End User Insights Pre Master Staging**.

   ![imagen](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_4.png)
10. Compruebe **el modelo End User Insights** para ver si la mayoría de los costes se asignan correctamente.

    ![imagen](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_5.png)

    Nota: El coste que aparece en la captura de pantalla sirve únicamente de referencia.

    ![imagen](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_6.png)

    Nota: El coste que aparece en la captura de pantalla sirve únicamente de referencia.
11. Compruebe si **los informes OOTB de los dispositivos de usuario final** muestran los números deseados.

## Flujo de configuración de dispositivos de usuario final

![imagen](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_7.png)

## Estudio de informes

Después de instalar Dispositivos de Usuario Final, **Report Studio** muestra un mosaico de Dispositivos de Usuario Final en la página de inicio. Puede utilizarlo para navegar hasta los **informes de Dispositivos de usuario final**.

A continuación se ofrece una rápida instantánea de los informes sobre dispositivos de usuario final:

![imagen](../../resources/images/end%20user%20devices%20-%20configuration%20guide/component%20end%20user%20devices_9.png)

[Más información sobre los informes de dispositivos de usuario final](end_user_dev_dashboard.html)
