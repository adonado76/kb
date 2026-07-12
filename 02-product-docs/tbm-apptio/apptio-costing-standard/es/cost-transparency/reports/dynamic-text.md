---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Texto dinámico y WikiText"
breadcrumb: []
source_path: "cost-transparency/reports/dynamic-text.html"
images:
  - "resources/images/ct_images/dt-ex-1.png"
  - "resources/images/ct_images/dt-ex-2.png"
  - "resources/images/ct_images/dt-ex-3.png"
  - "resources/images/ct_images/dt-ex-4.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Texto dinámico y WikiText

Conozca el texto dinámico, el wikitexto y las diferencias entre ambos.

## ¿Qué es el texto dinámico?

El texto dinámico permite ejecutar una fórmula Apptio para obtener datos que se utilizarán en contextos específicos. El texto dinámico empieza por "<%=" y termina por "%>".

¿Dónde puedo utilizar el Texto Dinámico?
:   Algunos de los lugares en los que puede utilizar texto dinámico son:

    - En los [elementos de información HTML](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-html-text-box "(se abre en una pestaña o una ventana nueva)")
    - En la [función EvalWiki](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=ff-evalwiki-function "(se abre en una pestaña o una ventana nueva)")
    - Al crear [menús desplegables en tablas editables](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-add-list-editable-table "(se abre en una pestaña o una ventana nueva)")
    - En [ApptioScript](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=apptioscript-structure "(se abre en una pestaña o una ventana nueva)")
    - En los argumentos de la [función CopyTable](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=apptioscript-copytable-function "(se abre en una pestaña o una ventana nueva)")
    - Para controlar [la visibilidad de los componentes del informe](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-arrange-report-components "(se abre en una pestaña o una ventana nueva)")

## ¿Qué es el WikiText?

WikiText se utiliza a veces indistintamente con texto dinámico. La diferencia clave es que en determinados contextos WikiText

Cómo utilizar el texto dinámico
:   Ejemplo 1: Visualización de usuario, proyecto o período en HTML
    :   Para empezar, cree un informe sandbox. No hace falta que lo registres. A continuación, cree un elemento de informe HTML en el informe y pegue lo siguiente en el elemento:

        ID de usuario: <%=$CurrentUser:Users.Id%><br>

        Rol de usuario: <%=$CurrentUser:Users.Role%><br>

        Nombre de usuario: <%=$CurrentUser:Users.Full Name%><br>

        <br>

        Nombre de dominio: <%=DomainName( )%><br>

        Nombre del proyecto: <%=ProjectName( )%><br>

        Tronco o rama: <%=if(Left( ProjectName( ),1)="-", "rama", "tronco")%><br>

        Nombre del proyecto troncal: <%=if(Left( ProjectName( ),1)="-",Mid( ProjectName( ), 2,find( "\_( ",ProjectName())-2),ProjectName( ))%><br>

        Ruta troncal: <%=if(Left( ProjectName(),1)="-",DomainName( )&":"&Mid( ProjectName( ), 2,find( "\_( ",ProjectName())-2),DomainName( )&":"&ProjectName( ))%><br>

        <br>

        Periodo seleccionado actualmente: <%=CurrentDate("MMM ffff")%>

        Cuando cierre el diálogo de configuración HTML debería ver algo como esto:

        ![imagen](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/dt-ex-1.png)

        Este es un ejemplo de lo que se puede hacer con texto dinámico para obtener información sobre usuarios, proyectos o periodos.

    Ejemplo 2: Visualización de datos de tabla en HTML
    :   Si desea mostrar datos de una tabla en un elemento HTML, puede hacerlo asociando columnas de una tabla.

        En este ejemplo crearemos un informe que muestre el Coste de una Torre de Recursos de TI en texto grande y en negrita en la parte superior, y los Pools de Costes asociados en una tabla debajo.

        1. Cree un informe con un elemento HTML configurado como sigue. En este ejemplo llamamos al informe "Demostración de texto dinámico".

           ![imagen](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/dt-ex-2.png)

           El HTML de la captura de pantalla es:

           <font size=5><%=IT Nombre de la Torre de Recursos%>: <b><%=Divisa(Coste)%></b></font>

           Observe que el HTML muestra " {Various} ", esto se debe a que hay más de un valor de Pool de Costes en la columna Pool de Costes. Sin embargo, abordaremos este tema en breve.

           En el mismo informe incluimos una tabla que muestra el Coste por Pool de Costes basado en el objeto Fuente de Coste como se muestra en la captura de pantalla anterior.
        2. A continuación, creamos un informe independiente al que llamamos "Demostración de perforación de texto dinámico" con una tabla que muestra el coste por nombre de torre de recursos de TI y configuramos la perforación ad hoc para perforar el primer informe:

           ![imagen](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/dt-ex-3.png)
        3. Ahora, al hacer clic en el nombre de una torre de recursos informáticos de la tabla, aparecerá el informe "Demostración de texto dinámico" filtrado por el nombre de la torre de recursos informáticos seleccionada. En este ejemplo hemos hecho clic en "Red":

           ![imagen](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/dt-ex-4.png)

    Ejemplo 3: Visibilidad de los componentes
    :   Esto puede colocarse mejor en la [visibilidad del componente del informe](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-arrange-report-components#Arrangereportcomponents__Setcomponentvisibility__title__1 "(se abre en una pestaña o una ventana nueva)").

    Ejemplo 4: Control de los desplegables en tablas editables
    :   Esto puede colocarse mejor en los [menús desplegables de las tablas editables](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-add-list-editable-table#Addalisttoaneditabletable__Generatealistwithdynamictext__title__1 "(se abre en una pestaña o una ventana nueva)").

    Ejemplo 5: En ApptioScript
    :   Esto puede situarse mejor en el [ApptioScript](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=apptioscript-structure#ApptioScript_structure__DynamicText__title__1 "(se abre en una pestaña o una ventana nueva)").
