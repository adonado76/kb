---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "HTML text box"
breadcrumb: []
source_path: "reports/html.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# HTML text box

Applies to: TBM Studio 12.0 and later

You can add a box containing text formatted in HTML. The text can present information that
explains the report or provides other important information. A sample HTML box is shown in the
following image. The HTML syntax supported is dependent on the browser you are using (not on the
HTML text box).

![](../../resources/images/studio_images/studioimages/studio/stu518.png)

The HTML can include links to other reports and context-dependent text (dynamic text) such as
date or user name. For more information, see [Coding Links to Other Reports](coding-links-to-other-reports.html "Applies to: TBM Studio 12.0 and later"). The HTML component is used most
often to add text, but you can enter any properly formatted HTML code. For example, you can add
borders and graphics around the text box.

Note: The HTML text box does not support JavaScript.

You can add an object context for the context-dependent text using the HTML Configuration
pane.

Text boxes are visible to all users regardless of role.

## Add an HTML text box

1. From the Report tab, click the HTML icon. The text box is added to the report and
   the Edit Content dialog is opened as shown in the following image:![](../../resources/images/studio_images/studioimages/reports/rep146.png)
2. Enter the text and HTML coding in the dialog.
   - To add the text to the text box and leave the Edit Content dialog open, click
     Apply.
   - To add the text to the text object and close the dialog, click OK.

## Add a table context to the HTML box

If you are using context-dependent text in the HTML box, you can add a table context using the
HTML Configuration pane.

1. Select the HTML box.
2. In the HTML Configuration pane, select a table from the field at the top of the
   pane.
3. If you have added a metric in the text such as Cost, drag the corresponding calculation field
   into the Values area of the dialog as shown in the first image.

## Edit text in a text box

To edit text in a text box:

1. Select the text box.
2. From the HTML tab, click Edit Content.

## Insert context-dependent text into the HTML

The application provides a scripting syntax you can use to insert context-dependent (dynamic)
text into HTML text boxes and data paths. You can use this syntax to create custom report titles,
captions, and headers for grouped columns in tables. You also can use it in the Edit Path
dialog box available from the Advanced pane in the Properties dialog box for a
table.

Dynamic text uses the following syntax:

`<%=code%>`

In the preceding statement, *code* can be a column reference to any table, metric, formula,
or function.

## Examples

The following example displays the current value for the metric Cost:

> `<%=Cost%>`

The following examples show two ways to format the current value for the metric Cost as
currency:

> `<%=Currency(Cost)%>`
>
> `<%=NumberFormat(Table.Column,”$#,###.00”)%>`

The following example references the content of the Server Name column to display the name of the
current server:

> ```
> <%=Server.Server
>           Name%>
> ```

The following example calls the LEFT function to display the left-most three characters of the
server name:

> `<%=LEFT(Servers.Server OS,3)%>`

The following example uses dynamic syntax in a URL to display the CMDB entry for a server:

> ```
> <a
>           href="http://cmdb.company.com/report?server=<%=Server.ServerId%>">
> ```

The following example displays the current date in the text:

> `<%=CurrentDate()%>`

The following example displays the user’s email account name:

> `<%=$CurrentUser:Users.Id%>`

The following example displays the user's full name:

> `<%=$CurrentUser:Users.Full Name%>`

The following example displays $0 if the value returned is blank:

> ```
> <%=IF(IsNumeric(SRM
>           Debits and Credits),Currency({SRM Debits and
> Credits},"#,###"),"$0")%>
> ```

## Properties

To edit the properties for an HTML component, display the Properties dialog by performing
one of the following actions:

- In the top-left corner of the component, click the small triangle ![](../../resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png) next to the
  component name to display the Actions menu. From the Actions menu, select
  Properties.
- Right-click anywhere within the borders of the component and select Properties from the
  pop-up menu.

## General properties

- Name - Enter a name to be displayed in the table header above the component. The name is
  displayed when Show Header option is selected.
- Show Header - The component header displays the contents of the Name field. Select
  this option to make the component header visible (the default). When the header is hidden, you can
  pause the mouse pointer on the component to display it when in Edit mode.
- Show Border - Select this option to display a border around the table. When the border is
  hidden, you can display it by pausing the mouse pointer on the component.
- Wrap Title - Wraps the text entered in the Name field to accommodate the width of
  the component.
- Dynamic Text Context - Specifies the path to the source that will be used for dynamic
  text entered in the HTML box. For information on dynamic text, see Inserting Context-Dependent Text
  above.

## Advanced properties

- Auto Refresh When Calculations Finish - When the application displays an HTML component,
  it displays it with the calculated data that is currently available. In many cases, the application
  may be calculating new values in the background. If you want the results displayed when the
  calculations are complete, check this option. The option is available only when the **Calculation
  Policy** (in the Project Calculation dialog) for a project is set to **Dynamic
  Publishing**.

## Add a scroll bar

If you want to enter a large amount of text in the HTML box, but you want to limit the size of
the box, you can add a scroll bar by using the following HTML code:

> ```
> <div
>           style="overflow-y:scroll; height:100%">
> This is
>             a</br>
> test for scroll</br>
> bars</br>
> </div>
> ```
