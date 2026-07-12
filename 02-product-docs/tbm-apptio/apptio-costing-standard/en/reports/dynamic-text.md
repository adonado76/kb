---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Dynamic Text and WikiText"
breadcrumb: []
source_path: "reports/dynamic-text.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Dynamic Text and WikiText

Learn about dynamic text, wikitext, and the differences between the two.

## What is Dynamic Text?

Dynamic text allows you to execute an Apptio formula to obtain data for use in specific contexts.
Dynamic text starts with "<%=" and ends with "%>".

Where can I use Dynamic Text?
:   Some of the places you can use dynamic text include:

    - In [HTML reporting elements](https://help.apptio.com/en-us/studio/reports/html.htm#InsertcontextdependenttextintotheHTML "(Opens in a new tab or window)")
    - In the [EvalWiki function](https://help.apptio.com/en-us/studio/formulas-and-functions/functions/evalwiki.htm "(Opens in a new tab or window)")
    - When creating [drop down menus in editable tables](https://help.apptio.com/en-us/studio/reports/tables/add-list-to-editable-table.htm?Highlight=dynamic%20text#dynamictext "(Opens in a new tab or window)")
    - In [ApptioScript](https://help.apptio.com/en-us/studio/apptioscript/apptioscript_structure.htm?Highlight=dynamic%20text "(Opens in a new tab or window)")
    - In arguments to the [CopyTable function](https://help.apptio.com/en-us/studio/formulas-and-functions/functions/copytable.htm?Highlight=dynamic "(Opens in a new tab or window)")
    - To control [report component visibility](https://help.apptio.com/en-us/studio/reports/arrange-report-components.htm#Setcomponentvisibility "(Opens in a new tab or window)")

## What is WikiText?

WikiText is sometimes used interchangeably with dynamic text. The key difference is that in
certain contexts WikiText

How to use Dynamic Text
:   Example 1: Displaying User, Project, or Period in HTML
    :   To start, create a sandbox report. You don’t need to check it in. Then create an HTML reporting
        element on the report and paste the following into the element:

        User ID: <%=$CurrentUser:Users.Id%><br>

        User Role: <%=$CurrentUser:Users.Role%><br>

        User Name: <%=$CurrentUser:Users.Full Name%><br>

        <br>

        Domain Name: <%=DomainName()%><br>

        Project Name: <%=ProjectName()%><br>

        Trunk or Branch: <%=if(Left(ProjectName(),1)="-","branch","trunk")%><br>

        Trunk Project Name:
        <%=if(Left(ProjectName(),1)="-",Mid(ProjectName(),2,find("\_(",ProjectName())-2),ProjectName())%><br>

        Trunk Path:
        <%=if(Left(ProjectName(),1)="-",DomainName()&":"&Mid(ProjectName(),2,find("\_(",ProjectName())-2),DomainName()&":"&ProjectName())%><br>

        <br>

        Currently Selected Period: <%=CurrentDate("MMM ffff")%>

        When you close the HTML configuration dialog you should see something like this:

        ![](../../resources/images/ct_images/dt-ex-1.png)

        This is an example of what you can do with dynamic text to obtain user, project, or period
        information.

    Example 2: Displaying Table Data in HTML
    :   If you wish to display data from a table in an HTML element, you can do this by associating
        columns from a table.

        In this example we will create a report which displays the Cost of an IT Resource Tower in large
        bold text at the top, and the associated Cost Pools in a table beneath.

        1. Create a report with an HTML element configured as follows. In this example we call the
           report "Dynamic Text Demo".

           ![](../../resources/images/ct_images/dt-ex-2.png)

           The HTML in the screen shot is:

           <font size=5><%=IT Resource Tower Name%>: <b><%=Currency(Cost)%></b></font>

           Note that the HTML displays "{Various}", this is because there is more than one Cost Pool value
           in the Cost Pool column. However, we will address that shortly.

           On the same report we include a table that displays Cost by Cost Pool based on Cost Source object
           as shown in the screen shot above.
        2. Next we create a separate report we call “Dynamic Text Drill Demo” with a table that displays
           Cost by IT Resource Tower Name and configure the Ad-Hoc drill to drill to the first report:

           ![](../../resources/images/ct_images/dt-ex-3.png)
        3. Now when we click on a IT Resource Tower Name in the table we arrive at the “Dynamic Text
           Demo” report filtered by the selected IT Resource Tower Name. In this example we clicked on
           “Network”:

           ![](../../resources/images/ct_images/dt-ex-4.png)

    Example 3: Component Visibility
    :   This may better be placed in the [report component visibility](../../studio/reports/arrange-report-components.html "Applies to: TBM Studio 12.0 and later").

    Example 4: Controlling Drop Downs in Editable Tables
    :   This may better be placed in the [drop down menus in editable tables](https://help.apptio.com/en-us/studio/reports/tables/add-list-to-editable-table.htm#Generatealistwithdynamictext "(Opens in a new tab or window)").

    Example 5: In ApptioScript
    :   This may better be placed in the [ApptioScript](https://help.apptio.com/en-us/studio/apptioscript/apptioscript_structure.htm?Highlight=dynamic%20text "(Opens in a new tab or window)").

**Parent topic:** [Costing Standard](../home.html)
