---
title: "Paying a house account balance"
id: platformPayHouseAccountBalance
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformHouseAccountsOmitChunkFromSearchIndex.md
parentSectionTitle: "House accounts"
previousSectionFile: adminGuide-platformEnableHouseAccountsPaymentMethod.md
previousSectionTitle: "Enabling house accounts as a payment method"
nextSectionFile: adminGuide-platformManageHouseAccounts.md
nextSectionTitle: "Managing house account invoices"
externalReferences: [https://central.toasttab.com/s/article/Configuring-Payment-Options]
excerpt: "House accounts can hold either a balance or a credit. If a guest pays for a check using a house account, this creates an outstanding balance. The balance is the total charge amount due. If a guest..."
keywords: ["paying", "house", "account", "balance"]
procedures: 0
codeExamples: 0
---

House accounts can hold either a balance or a credit. If a guest pays for a check using a house account, this creates an outstanding balance. The balance is the total charge amount due. If a guest has funds available in their house account, this creates a credit balance. Outstanding balances must be paid either on the Toast POS or by invoice.

Below is a list of actions that will increase an outstanding balance and actions that will decrease an outstanding balance and may create a credit:

**Actions that increase the outstanding balance**

- Paying a check with a house account.


- Manually increasing the outstanding balance.



> **Note**
> 
> Only internal Toast administrators can complete this action.



- Paying a custom invoice house account payment.



**Actions that decrease the outstanding balance**

- Paying a house account balance on a Toast POS device.


- Paying a house account invoice.


- Overpaying an outstanding house account balance.


- Manually decreasing the outstanding balance.


- Removing a house account payment on a POS device.



> **Note**
> 
> Toast support recommends that house account balances be paid from a Toast Web invoice or on a Toast POS device.




House accounts can hold a credit that can used for future orders. This allows guests to pay and close orders to their house account to reduce the balance. For example, if the house account’s outstanding balance is -$100.00, the guest has a $100 credit that they can use for orders before they will be invoiced for additional orders.

Guests can pay a house account balance on a Toast POS device on any order screen. House account balances can be paid by all payment methods except by another house account. For more information on configuring payment options, see this [Toast Central article](https://central.toasttab.com/s/article/Configuring-Payment-Options).

## Paying a house account balance on the POS

**Procedure 6.98. To pay a house account balance on the POS**

1. On the Toast POS home screen, select an order screen.


2. On the order screen, select the House Accounts button.


3. Select the Pay Balance button. This opens the Pay House Account Balance dialog.


4. In the Pay House Account Balance dialog, enter the customer number, or house account, or select the Lookup button to open the Customer lookup screen. On the Customer lookup screen, enter the guest's first or last name, email address, customer number, or phone number to search for the house account. Partial information can be used to search.


5. This opens the Pay House Account Balancescreen. If there are unpaid invoices linked to the house account, the invoices are displayed. If there are no unpaid invoices, a dialog appears where you can pay the house account balance.

![The Pay house account balance screen on the Toast POS.](https://doc.toasttab.com/doc/media/platform-house-accounts-pay-account-balance-unpaid-invoices.png)


6. On the Pay House Account Balance screen, choose to:

- Pay an open invoice. This opens the Payment Terminal screen. On the Payment Terminal screen, choose to pay for the invoice using the available payment methods.



> **Note**
> 
> Toast support recommends you pay open invoices to keep records accurate.



- Select the Skip button to open a dialog where you can pay the current balance or update the payment amount. Select the Pay balancebutton to pay the house account balance.



![The Pay house account balance dialog on the Toast POS.](https://doc.toasttab.com/doc/media/platform-house-accounts-pay-account-balance-dialog.png)



> **Note**
> 
> If you try to pay a house account that has a credit as the outstanding balance, a message appears notifying you that payment is not necessary.



7. On the order screen, your payment is listed on the order details dialog. To remove a payment, select the payment on the order details panel and select the Remove button. This removes the payment from the check.

![The Remove button emphasized on a payment screen.](https://doc.toasttab.com/doc/media/platform-house-accounts-remove-balance-payment.png)



## Paying a house account invoice

Guests can pay their invoice on Toast Web or from the pay link in their invoice email or text message.

### Paying an invoice from email or text message

**Procedure 6.99. To pay a house account invoice from email or text message**

1. From the email or text message, select the View and pay this invoice link. This opens the invoice in a web browser.


2. In the invoice, go to the Pay this invoice section. Select the payment method and enter the payment details.


3. Select the Pay now button to complete the payment.



### Paying an invoice on Toast Web

**Procedure 6.100. To pay a house account balance on Toast Web**

1. [Access Toast Web](docs/en-us/adminGuide-adminAccessToastAdminBackend).


2. Go to Payments &gt; Payment methods &gt; House accounts to open the Accountspage.


3. On the Accounts page, select the house account. This opens the House account profile page.


4. On the House account profile page, go to the Invoices section.


5. Select the Invoice link to open the Invoice page.



> **Note**
> 
> Unpaid invoices display an OPENstatus under the Status column.



6. On the Invoice page, choose how to pay the invoice.

- From the Payment schedule tab, choose one of the following methods to pay the invoice:

- View payment page: Select the link to view and pay the invoice by entering payment details in the card input fields. Select the Pay now button to complete the payment.

A *The payment was successful*banner appears and a PAID label appears at the top of the Invoicepage.


- Enter a payment: Select the link to view to open the Pay invoice page. On the Pay invoice page, you can view the invoice, add a tip, and pay using a configured payment method. Select the Process payment button to complete the payment.

A `The payment was successful` banner appears and a PAID label appears at the top of the Invoice page.



![Shows the Payment schedule tab with the View payment page and the Enter a payment buttons emphasized in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-payment-schedule.png)


- From the Actions dropdown menu, choose the Enter payment button to open the Pay invoice page. On the Pay invoice page, you can view the invoice, add a tip, and pay using a configured payment method. Select the Process paymentbutton to complete the payment.

A *`The payment was successful`* banner appears and a PAID label appears at the top of the Invoice page.



On the Payment schedule tab, the payment is listed with the due date, amount paid, and the status. To view more payment details, select the down arrow next to the Status column. You can view payment details such as the payment method type, tip amount, payment date, and payment status.

![Shows an invoice with the PAID label on the Payment schedule page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-paid-invoice.png)



### Adding a tip



> **Note**
> 
> Toast support recommends that you do not add tips to invoices as the guest may have already tipped on the check.


You can add a pre-configured tip amount or a custom tip to an open or paid invoice on the Invoice or Pay invoice page. The tip amount is reflected in the Order summary report.

- On the Invoice page, select Add tip from the Actionsdropdown menu. This opens the Pay invoicepage. On the Pay invoice page, go to the Add tip section and select the tip amount.

![Shows the Add tip button on the Invoice page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-add-tip.png)


- On the Pay invoice page, go to the Add tip section and select the tip amount.

![Shows the Add tip button on the Pay invoice page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-add-tip-paid.png)





> **Note**
> 
> You can turn off the tipping feature by clearing the Allow customers to add a tip checkbox in the Details section on the Invoice page.


### Resending a receipt

To resend a paid invoice receipt, select Resend receipt from the Actions dropdown menu on the Invoice page. If the receipt was successfully sent, a `Receipt sent successfully` banner appears at the bottom of the page.

### Adjusting a payment

You can adjust the payment amount for an invoice on the Invoice page. You can void or adjust a payment from the Payment schedule section or from the Actions dropdown menu on the Invoice page.



> **Note**
> 
> The Toast platform does not send an email if an invoice payment was voided.


**Procedure 6.101. To adjust a payment**



> **Note**
> 
> If the order has been fully paid, only the tip can be adjusted.


1. On the Invoice page, select Adjust/void payment from the Actions dropdown menu or from the Payment schedule section. This opens the Adjust/void payment dialog.


2. In the Adjust/void payment dialog, you can:

- View the amount authorized to be paid


- View the date and time of the payment


- View the balance due




3. Add the tip amount. The new tip amount is shown in the Total section.

![Shows the new tip amount in the Adjust/void payment dialog in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-adjust-payments.png)


4. Select the Adjust button to add the tip. The new tip amount is shown in the Orders section on the Invoice page.



### Voiding a payment

You can void a payment for an open invoice on the Invoice page.

**Procedure 6.102. To void a payment**

1. On the Invoice page, select Void invoice from the Actions dropdown menu. This opens the Adjust/void payment dialog.

![Shows the Void invoice button on the Invoice page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-void-payment.png)


2. A confirmation dialog window appears asking if you want to void the invoice. Select the Void paymentbutton to void the payment.

If the payment was successfully voided, the invoice status changes from PAID to OPEN.



