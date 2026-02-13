---
title: "Adjustments"
id: platformPwfAdjustments
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPwfOmitChunkFromSearchIndex.md
parentSectionTitle: "Payment workflows"
previousSectionFile: adminGuide-platformPwfDigitalReceipts.md
previousSectionTitle: "Digital receipts and printed receipts"
nextSectionFile: adminGuide-platformPwfTenders.md
nextSectionTitle: "Payment workflows"
keywords: ["adjustments"]
procedures: 0
codeExamples: 0
---

## Voids

Voiding a check, item or payment is the process of removing an item or payment from a check or removing the check altogether. Check items can only be voided if that have been sent to the kitchen, and payments can only be voided if it was successfully processed.

The following procedures define workflows for voiding a check, a payment or line items.

### Check, item, and payment voids

Voiding a check, item, or payment happens for multiple reasons, including:

- A guest leaves without paying for their check.


- An item is sccidentally selected.


- A check's payment method needs to be changed.


- A guest has an unsatisfactory experience.



The following procedures show how to void a check, item, or payment.

#### Voiding a check

**Procedure 6.1. To void a check**

A check void completely removes a check. Keep the following in mind when voiding a check.

- You cannot void a check with a payment applied. You must remove each payment and then void the check.


- If a check has a percent service charge, this charge remains on the check and is not removed if voided. However, service charge is updated to $0.00.


- If a check has been sent to the kitchen, and then voided, the voided check is still shown on the Payments report in Toast Web. You can find this report from Reports &gt; Payments &gt; Payments.


- Voiding a check with a negative balance prompts you to refund the guest.



The following procedure shows how to void an order on the Toast platform.

1. Select All checks menu from an order screen.

![Location of the All checks button.](https://doc.toasttab.com/doc/media/pwfVoidAllChecksButtonLight.png)


2. Select the correct tab corresponding to the status of the check whether that be Open, Paid, or Closed.

![Diagram selecting the Open tab](https://doc.toasttab.com/doc/media/pwfVoidCheckStatuses.png)


3. Locate and select the check you want to void. The check's payment screen opens.

![Diagram selecting a check to void.](https://doc.toasttab.com/doc/media/pwfVoidPaymentSelectCheck.png)


4. Select Update.

![Location of Update button on the Toast platform.](https://doc.toasttab.com/doc/media/pwfVoidUpdateLight.png)


5. Select the overflow menu from the upper-right corner and choose Void Order.

![Location of the check menu button](https://doc.toasttab.com/doc/media/pwfVoidVoidOrderLight.png)


6. Select Void order to confirm.

![Location of the check menu button](https://doc.toasttab.com/doc/media/pwfVoidVoidConfirmLight.png)



#### Voiding a payment

You may want to void a payment if an incorrect payment was applied to a transaction. The following procedure shows how to void a payment on the Toast platform.

**Procedure 6.2. To void a payment**

1. Open the All checks menu from an order screen.

![Location of the All checks button.](https://doc.toasttab.com/doc/media/pwfVoidAllChecksButtonLight.png)


2. Select the Paid tab.

![Closed tab location.](https://doc.toasttab.com/doc/media/pwfVoidPaidTab.png)


3. Locate and select the check whose payment you want to void.

![Diagram selecting the check.](https://doc.toasttab.com/doc/media/pwfVoidPaymentSelectCheck.png)


4. Select Pay.

![Diagram selecting Pay.](https://doc.toasttab.com/doc/media/pwfVoidPayLight.png)


5. Select the payment on the check and choose Void.

![Diagram selecting a payment to void.](https://doc.toasttab.com/doc/media/pwfVoidVoidPaymentLight.png)


6. Select Void to confirm.

![Diagram confirming to void a payment.](https://doc.toasttab.com/doc/media/pwfVoidVoidPaymentConfirmLight.png)



#### Voiding an item

When an employee makes a mistake, or to appease a guest who had an unsatisfactory experience, you may have to void an item. The following procedure shows how to void an item on the Toast platform.

**Procedure 6.3. To void an item**

1. Select All checks from an order screen.

![Location of the All checks button.](https://doc.toasttab.com/doc/media/pwfVoidAllChecksButtonLight.png)


2. Locate and select the check whose item you want to void.

![Selecting a check.](https://doc.toasttab.com/doc/media/pwfVoidPaymentSelectCheck.png)


3. Select Update.

![Update button.](https://doc.toasttab.com/doc/media/pwfVoidUpdateLight.png)


4. Choose the item you want to void, and select Void.

![Item select and void buttons](https://doc.toasttab.com/doc/media/pwfVoidItemSelect.png)


5. Select Void Item to confirm.

![Void item button.](https://doc.toasttab.com/doc/media/pwfVoidItemConfirm.png)



## Refunds

Refunding a guest is one of the most common actions taken on a point of sale system. Most commonly, a refund is issued if an incorrect payment type is used, or to resolve guest issues. For more information about refunds, see [Refunds](adminGuide-adminRefundPermissionsLimitations).

