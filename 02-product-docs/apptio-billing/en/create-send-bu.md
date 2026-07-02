---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "create-send-bu.html"
title: "Create and send business unit bills"
breadcrumb: []
source_path: "create-send-bu.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Create and send business unit bills

You can customize the text messages that are displayed in the header and footer of a bill. The messages are stored in the Email Invoice Messages table. The descriptions for the three messages are as follows:

- Global Message - A message that will be displayed at the top of
  every invoice. This is in addition to the default header message.
- Default Header Message - The default message that will be displayed
  at the top of every invoice if a default header message has not been defined in the Recipient
  Invoice List table, or by a message entered in Production at the time the invoice is sent.
- Default Footer Message - The default message that will be displayed
  at the bottom of every invoice if a footer message has not been defined in the Recipient Invoice
  List table.

To edit the messages:

1. In the TBM Studio Project Explorer, open the Email Invoice Messages
   table. The table is located under the group.
2. On the Home tab, click Export , and
   select Excel to export the table to Excel.
3. Modify the text in Excel and save the file.
4. Upload the file to the Email Invoice Messages table.
   - Set the date to the beginning date of the project.
   - Click the Upload step.
   - Click Initial Upload and select Overwrite .
   - Locate the Excel file you want to upload.

Designate the recipients and their bill information

The users that will receive an invoice is determined by the list of users in the Recipient
Invoice List table. Maintain the list in an Excel spreadsheet and upload the file to . See [Upload a data
file](../studio/data_studio/upload-data-file.htm "(Opens in a new tab or window)") .

The fields in the table include:

- Bill Name - Each row must have a unique value.
- Filter Column - You can limit the entries in a bill by applying a
  filter. Enter the name of a column from the Business Unit Allocation Master Data table. The columns
  most often used are Governing Body, Business Unit, and Department. The column can be a custom column
  in the Master Data table.
- Filter Value - Enter a value from the filter column. For example,
  you might enter the name of a business unit.
- Recipient - Enter the name of the recipient followed by their email
  address. You can enter an individual email or an alias. The names are optional. Only an email
  addresses is required.   
   Example : Pat Smith
  <psmith@abc\_company.com>.
- Reply To - The name and email address of the person the recipients
  should contact for more information about the bill.   
   Example :
  Pat Smith <psmith@abc\_company.com>.   
   NOTE : An email alias
  can be used in the field, but you cannot enter a list of email addresses.
- Default Header Message - The first message displayed at the top of
  the invoice. If the field is left blank, the Global Message will be used.
- Footer Message - The message displayed at the bottom of the invoice.
  If the field is left blank, the Default Footer Message will be used.

Lock to Staging and promote
to Production

Bills can be sent only from the Production environment. You must lock the project in the
Staging environment and then promote the project to the Production environment. See [Lock and promote a
project](https://community.apptio.com/docs/doc-5117 "(Opens in a new tab or window)") .

Designate bills to be sent

1. Switch to the Production environment.
2. On the homepage, click Manage and Send Invoices .
3. Click the bill you want to send, or click Send all Bills on the main
   page.   
    It only will send bills that have not already been sent.

Enter a custom message for a
specific bill

You can enter a custom message for a specific bill.

1. Open the bill you wish to edit.
2. Navigate to the comment section on the left of the screen.
3. Enter your comment into the box.
4. If you wish to send the bill with the custom message now, click Send
   .
5. If you wish to send the bill at a later time, click Save .
     
    This will save the custom message and display it next time you open the bill.
6. Re-opening a bill with a saved message will allow you to edit the message again, or send the bill

Preview a bill

You can preview a bill before you send it in two ways.

- Navigate to the Invoice report :
  - This report is located in the Service Charges report collection. To
    display the report, click Invoice .
  - Use the Business Unit Hierarchy Global Slicer to create variants of the
    bill for preview.   
     Note that this screen will have no impact on the actual bill.
    Changes you make here are for preview purposes only.
- Click on the bill and locate the preview pane on the right side of the
  screen - This screen will show you what will actually be sent. The Filter Column and
  Value defined in the data set will be applied here, and cannot be changed in Production. This screen
  is a very similar to what the recipient will see when opening the email.

Send business unit bill(s)

You can send individual bills, or send all bills. If you click Send All
Bills , only bills that have not been sent before will be sent.

To send a single bill:

1. Click on the bill you wish to send.
2. Navigate to the comment box on the left side of the screen.
3. Enter a comment, or leave the default message.
4. Click Send .
5. Observe the status bar above the comment box, this status bar will let you know when the Bill has successfully sent.
6. If you wish to resend a bill that has previously been sent:
   1. Open the previously sent Bill
   2. Click Reset under the comment box on the left of the screen.
   3. Click Send .
   4. Resetting the Bill will also allow you to send the Bill using the Send All
      Bills functionality

To send all bills, click Send All Bills on the Distribution Report.

Track the status of the bills

A bill can have one of the following statuses:

- Not Sent - The bill has note been sent and requires action by the
  sender.
- Sent - The bill has been sent successfully but has not been read by
  the recipient.
- Read - The bill has been sent and has been read by the recipient.
- Error - There was an error sending the message. You can view the
  errors dialogue to investigate.

Remove the link from the invoice email

Beginning with TBM Studio 2.9.1, you can remove from the invoice email the link that sends a user to the invoice that generated the email. You can remove this link, if needed.

To remove the email link:

1. In the TBM Studio Project Explorer, go to Tables > , then
   click Recipient Invoice List
2. In the Append to Recipient Invoice List dialog, set the
   Link Visible value to "no".   
    Any other value in this column prevents the
   ability to hide the link. To remove the link, the value must be "no".
3. All emails going forward no longer display the link.

**Parent topic:** [Billing Standard](home.html)
