---
title: "Managing house account invoices"
id: platformManageHouseAccounts
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformHouseAccountsOmitChunkFromSearchIndex.md
parentSectionTitle: "House accounts"
previousSectionFile: adminGuide-platformPayHouseAccountBalance.md
previousSectionTitle: "Paying a house account balance"
nextSectionFile: adminGuide-platformViewHouseAccountsReporting.md
nextSectionTitle: "Viewing house accounts reporting"
externalReferences: [https://central.toasttab.com/s/article/How-to-run-a-Tax-Exempt-transaction-1492809352212]
excerpt: "House account invoices have one of the following statuses:"
keywords: ["managing", "house", "account", "invoices"]
procedures: 0
codeExamples: 0
---

### Managing house account invoices

House account invoices have one of the following statuses:

- PAID: The invoice has been paid.


- OPEN: The invoice has been created and sent.


- DRAFT: The invoice has been created but not sent.

![Shows various invoices and their statuses on the House account profile page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-invoice-statuses.png)



Invoices can be sent according to a set payment schedule. At the end of the billing cycle, you must create and send an invoice(s) for the outstanding house account balance.

#### Configure bulk house account invoice settings

You can configure house account settings for bulk invoices. On the Settings page, you can configure the following settings:

- Default dining option: Choose a dining option to filter POS orders linked to a house account.


- House account charges: Configure and add service charges to be applied to house account invoices.


- Default time range for new invoices: Select a time range to generate new house account invoices.



![Shows House accounts invoice settings section on the Settings page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-bulk-invoice-settings.png)

Configured settings apply to all bulk invoices, however you can choose to remove a setting from individual invoices.

#### Creating a house account invoice

You can create an invoice(s) for house account(s) in Toast Web.

**Procedure 6.103. To create a house account invoice**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Go to Payments \> Payment methods \> House accounts to open the Accountspage.


3. Select the house account to invoice. This opens the House account profile page.


4. On the House account profile page, select the Create invoice button. This opens the New invoice page and the Add house account balance to invoice dialog.


5. In the Add house account balance to invoice dialog, you can complete the following actions:

- View the current house account balance


- Select the charge method:

- Transactions


- Custom amount




- Select a date range to invoice


- Select the checks to invoice



![Shows the Add house account balance to invoice dialog in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-add-balance-to-invoice.png)


6. On the New invoice page, you can view and access the following tabs:

- Customer


- Order


- Payment schedule


- Details


- History




7. On the New invoice page, you can customize your invoice:

- From the Customer tab:

- Edit your guest information:

- Select the + Add additional recipients link to manually add another email address to send the invoice to. Under Email address, enter the email address and then select the Save recipients button to save your changes. You can add multiple email addresses.



![Shows the Customer tab with the Save recipients button emphasized in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-add-email.png)


- Choose whether to send the invoice by email or text message or both.



> **Note**
> 
> If you choose to send invoice by text message, a dialog appears with SMS Terms and Conditions. Select the Close button to acknowledge the Terms and Conditions.





- From the Order tab:

- Open a new order. This converts a draft order into an open order and sends it to all Toast POS devices.


- Select the house account dining option to invoice. This sorts and filters all in-store orders linked to the house account dining option.


- View, add, or delete items in the invoice or adjust your invoice balance:

- To view the items in your invoice, select the down arrow next to the check number. This displays all the items in your check.

![Shows the items in a check on the Order tab in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-view-items.png)


- To add an item to your invoice, select the Add item link. This opens the Select menu item page. On the Select menu item page, you can search for a menu item and then select the Add to order button to add it to the order.

![Shows the Select menu item page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-add-item.png)


- To delete an item from your invoice, select the Delete button in the overflow menu. This deletes the item from the invoice.


- To edit your invoice balance, select the Edit button in the overflow menu. This opens the Add house account balance to invoice dialog where you can change your charge method, invoice amount, and item name.




- Mark order as tax exempt: Select the checkbox to exclude taxes from the invoice. If you choose to make the order tax-exempt, you cannot add a discount.

- Add tax exemption ID: Add a tax exemption ID. For more information, see this [Toast Central article](https://central.toasttab.com/s/article/How-to-run-a-Tax-Exempt-transaction-1492809352212).




- Add a service charge to the invoice. To add a service charge, select the + Add service chargelink to open the Add a service chargedialog. In the Add a service chargedialog, select the service charge and then the Add service charges button to add the charge to the invoice. For more information, see [Configuring service charges](adminServiceChargeCreate.html).

![Shows the Add a service charge dialog in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-add-service-charge.png)


- Add a discount to the invoice. To add a discount, select the + Add discount link to open the Add discount dialog. In the Add discount dialog, select the discount type and then the Add discountbutton to add the discount to the invoice.




- From the Payment schedule tab:

- Configure how and when you want your guests to pay their invoices:

- Choose the due date for the invoice. Use the date picker to set the payment deadline. If the invoice is paid after the due date, it is considered past due.


- Choose to either pay the full amount or a percentage of the invoice amount.






- From the Details tab:

- (Optional) Choose an employee from the Server dropdown menu that will receive tips from the order.


- Select if you want to Allow customers to add a tip and to Allow customers to pay with a credit card.

- Allow customers to add a tip: This allows your guests to add a tip to the invoice.


- Allow customers to pay with a credit card: This allows your guests to pay their invoice with a payment card.




- Choose to enter a custom message to attach to the invoice.


- Choose to add an attachment to the invoice email.




- From the History tab:

- View house account’s payment history.






8. Select the Review invoice button to open the Review and send invoice page or select the Save as draft link to save the invoice.


9. On the Review and send invoice page, you can complete the following actions:

- View a PDF of the invoice


- View an email version of the invoice


- Edit the invoice


- Send the invoice


- Print the invoice


- Download the invoice



![Shows the invoice PDF of an invoice in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-review-invoice.png)


10. Select the Send invoice button to send the invoice by email or select the down arrow to the right of the Send invoice button to also choose to send by text message. On the House account profilepage, the recently created invoice shows a status of OPEN. 

![Shows an invoice with an OPEN status on the House account profile page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-open-invoice.png)

The newly created invoice is sent as an email, text message, or both to your guest with a link to view and pay their invoice.

![Shows an open invoice with a link to pay now.](https://doc.toasttab.com/doc/media/platform-house-accounts-emailed-invoice.png)



##### Sending a draft invoice

You can send a previously saved draft invoice from the House account profile page. You can edit draft invoices before you send them.

In the Invoices section, choose the invoice with a DRAFT status and select the invoice link to open the Invoice page. Complete the workflow from the [Creating a house account invoice](platformManageHouseAccounts.html#platformCreateHouseAccountInvoice) section.

##### Deleting a draft invoice

On the Invoice page, you can delete a draft invoice. From the Actions dropdown menu, select Delete draft. A confirmation dialog box appears asking if you want to delete the draft. This action cannot be undone. Select the Delete draft button to continue. This opens the Catering & Events page where you view all your invoices and their statuses. The invoice is removed from the Invoice page.

##### Creating bulk invoices

You can choose to create multiple invoices and bulk send them to guests to collect payment. You can bulk create and send invoices on the House accounts page in Toast Web.

**Procedure 6.104. To create bulk invoices**

1. [Access Toast Web](adminAccessToastAdminBackend.html).


2. Go to Payments \> Payment methods \> House accounts to open the House accounts page.


3. On the left panel, select the Bulk invoice tab. This opens the Bulk invoice page.


4. On the Bulk invoice page, you can view the Overview table. The Overview table displays the following information:

- The date and time bulk invoice(s) were created and sent


- The transaction date range the invoices were generated for


- The status of the bulk invoice(s)


- The number of invoices successfully sent



Select the Create bulk invoice button. This opens the Set up invoices page.


5. On the Set up invoices page, you can:

- Select a dining option to filter all orders on the POS app.


- Enter a custom message to be sent with the invoices.


- Select the invoice payment due date.

- Choose to allow customers to pay with a credit card.


- Choose to set the invoice amount to the outstanding balance.




- Add a house account charge.



> **Note**
> 
> If you do not add a house account charge, the Toast platform only displays house accounts with charges for the transaction date range set. If you add a house account charge, the Toast platform displays all house accounts that can be invoiced for the house account charge.
> To remove a house account from the list of house accounts with a charge, uncheck the checkbox next to the house account name.



- Select the transaction date range. This searches and filters orders by transaction date.




6. Select the Generate [number of invoices] invoices button. This opens the Bulk invoice page.

![The Set up invoices page with the Generate number of invoices button emphasized in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-bulk-invoice.png)


7. On the Bulk invoice page, the newly created invoice appears in the Overviewtable. The Overview table displays the following information:

- Date the invoice(s) were created


- The status of the invoice(s). The following statuses are available:

- CREATING


- READY TO SEND


- SENDING


- SENT


- CREATED




- The number of invoices




8. To review the invoices, select the invoice to open the Preview invoices [date] page. On the Preview invoices [date] page, you can view the following information:

- Summary of the invoices:

- Status of the invoices


- Total number of invoices


- Transaction range


- Total paid




- House account information:

- Name of the house account owner


- Customer number


- Invoice number


- Invoice amount


- Invoice status


- Link to download all invoices


- Link to download an individual invoice




- A preview of the invoice


- A preview of the guest email


- Link to download the invoice


- Link to print the invoice

![Shows the Preview invoices page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-preview-bulk-invoice.png)




9. To bulk send the invoices, select the Send [number of invoices] invoices button. This opens a confirmation dialog. Confirm the invoice is correct before sending.


10. Select the Send invoices button to send the invoices. This opens the Bulk invoicepage. The status of the invoice changes from READY TO SEND to SENDING.

![Shows the Bulk invoice page with an invoice with a status of SENDING emphasized in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-send-bulk-invoice.png)

If the invoice was successfully sent, the invoice status changes to SENT and the number of total invoices changes to reflect the number of successfully sent invoices.



