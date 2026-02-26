---
title: "Enabling house accounts as a payment method"
id: platformEnableHouseAccountsPaymentMethod
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformHouseAccountsOmitChunkFromSearchIndex.md
parentSectionTitle: "House accounts"
previousSectionFile: adminGuide-platformManageHouseAccountsInfo.md
previousSectionTitle: "Managing house account information"
nextSectionFile: adminGuide-platformPayHouseAccountBalance.md
nextSectionTitle: "Paying a house account balance"
externalReferences: [https://central.toasttab.com/s/article/Basic-Digital-Receipt-Configuration]
excerpt: "Your guests can use a house account as a payment method to pay for Toast orders. To allow your guests to pay using a house account, you need to turn on the Take house account payments on a POS..."
keywords: ["enabling", "house", "accounts", "payment", "method"]
procedures: 1
codeExamples: 0
---

Your guests can use a house account as a payment method to pay for Toast orders. To allow your guests to pay using a house account, you need to turn on the Take house account payments on a POSsetting in Toast Web.

**Procedure 6.95. To enable house accounts as a payment method**

1. [Access Toast Web](docs/en-us/adminGuide-adminAccessToastAdminBackend).


2. Go to Payments &gt; Payment methods &gt; House accounts to open the Accountspage.


3. On the left panel, select the Settings tab. This opens the Settings page.


4. Select the Take house account payments on a POS setting and toggle the option from Off to On.


5. Select the Save button to save your changes and then the Publish all changes button to publish your changes.



> **Note**
> 
> If a house account has been enabled as a payment method on the Toast POS, employees can access this feature without manager approval.




## Paying for orders with a house account

Guests who have a house account and the Take house account payments on a POS setting set to On can choose to pay for a Toast order with a house account.



> **Note**
> 
> Phone number inputs are not available in the United Kingdom (UK).


**Procedure 6.96. To pay for an order with a house account**

1. On the Toast POS home screen, select an order screen.


2. Place the order and then select the Paybutton to open the payment screen.


3. On the payment screen, select the House account button. This opens the Enter account number dialog.

![The House account button emphasized on the payment screen.](https://doc.toasttab.com/doc/media/platform-house-accounts-house-account-button.png)


4. In the Enter account number dialog, enter the customer number, or the house account number, or select the Lookup button to open the Customer lookup screen.


5. On the Customer lookup screen, enter the guest's first or last name, email address, customer number, or phone number to search for the house account. Partial information can be used to search.


6. Select the Done button to select the house account. This opens the Charge this account dialog.


7. In the Charge this account dialog, select how you want to charge the order:

- Track but do not invoice: Use this option if the guest is going to pay for the order but not use the house account.



> **Note**
> 
> If you choose to Track but do not invoice, the total order spend is calculated into the total spend for the house account.



- Use a different account: Use this option if the guest is going to pay for the order using another house account.


- Invoice: Use this option if the guest is going to pay for the order using the house account. This option closes the order on the Toast POS and defers the payment. The order will appear on the house account’s list of activities in Toast Web. 

![The Charge this account dialog on a payment screen.](https://doc.toasttab.com/doc/media/platform-house-accounts-charge-account.png)



On the Payment Terminal screen on the Toast POS device, checks that have been paid by a house account show the total check amount and the house account icon. For more information, see [House accounts](docs/en-us/adminGuide-platformPwfTenders#platformPwfHouseAccountsInfo).



> **Note**
> 
> You can add a tip to a house account transaction. To add a tip, you must configure your digital receipts settings. For more information, see this [Toast Central article](https://central.toasttab.com/s/article/Basic-Digital-Receipt-Configuration).


![Shows a paid order with the house account payment details emphasized.](https://doc.toasttab.com/doc/media/platform-house-accounts-paid-check.png)

On the House account profile page in Toast Web, you can view the order (transaction) in the Account activity section. The transaction displays CHARGE as the activity type and the amount charged.

![Shows the paid order in the Account Activity section on the House account profile page in Toast Web.](https://doc.toasttab.com/doc/media/platform-house-accounts-paid-check-Toast-web.png)



## Paying for an order with a negative house account balance

If a house account has a negative balance, guests can pay for their order using the credit on the house account. When prompted on the Toast POS device, select House account as the payment method. The house account credit is used to pay for the order and no payment is necessary until the balance is positive.

The total of the transaction is deducted from the house account and the outstanding balance is shown on the House account profile page. Transaction details are shown in the Account activity section. The transaction displays CHARGE as the activity type and the amount charged.

## Moving a closed check to a different house account

You can move a check(s) that was accidentally closed to the wrong house account.



> **Note**
> 
> If a check is opened and closed on the same day, you can skip steps 1-5 and proceed to step 6. Checks opened and closed on the same day can be moved on the Payment Terminal screen on a Toast POS device.


**Procedure 6.97. To move a closed check to a different house account**

1. [Access Toast Web](docs/en-us/adminGuide-adminAccessToastAdminBackend).


2. Go to Reports &gt; Sales &gt; Orders to open the Orders report.


3. Locate the closed order that you want to move to different house account.


4. Select the Re-open check link next to the check number. A confirmation dialog appears asking if you want to reopen the check.


5. Select the OK button to proceed. This reopens the check and sends it to all POS devices.


6. Locate the reopened check on the Toast POS device. The reopened check appears under the Paid tab on the Payment Terminal screen.


7. On the Payment Terminal screen, select the reopened check.


8. Select the Pay $ button to open the payment screen.


9. On the order screen, select the house accounton the order details panel.


10. Select the Remove button to remove the house account. This opens the payment screen.

![Shows the house account with the Remove button emphasized.](https://doc.toasttab.com/doc/media/platform-house-accounts-remove-button.png)


11. On the payment screen, select the House account button to select another house account to complete the payment.

For more information, see [Reopening closed checks](docs/en-us/adminGuide-platformOrdersReopening).



