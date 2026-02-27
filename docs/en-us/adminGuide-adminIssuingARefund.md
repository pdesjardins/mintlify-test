---
title: "Issuing a refund"
id: adminIssuingARefund
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminRefundsOmitChunkFromSearchIndex.md
parentSectionTitle: "Refunds"
previousSectionFile: adminGuide-adminRefundsAndVoids.md
previousSectionTitle: "Refunds and voids"
nextSectionFile: adminGuide-adminRefundedItemsInTheKitchen.md
nextSectionTitle: "Effect of refunds in the kitchen"
excerpt: "To issue a refund, you locate the check that requires a refund and then choose a refund type from the Refund menu."
keywords: ["issuing", "refund"]
procedures: 0
codeExamples: 0
---

To issue a refund, you [locate the check](adminGuide-adminIssuingARefund#adminLocatingACheckToRefund) that requires a refund and then choose a refund type from the Refund menu.

You can choose to refund specific items, the entire check, tip only, tax only, or a custom amount. When you refund specific items or the entire check, you can specify the quantity to refund for each item.

![Refund drop-down with the available refund types.](https://doc.toasttab.com/doc/media/refunds-refund-menu.png)

## Locating a check to refund

To issue a refund, you must first locate the original check on either the POS or Toast Web.

You can only issue cash refunds from a Toast POS device.

### Locating a check on a Toast POS device

To locate a check on a Toast POS device:

1. To display the check search:

1. On the Toast POS device, tap the Toast logo in the top corner until the Toast POS home screen appears.


2. Under Manager Activities, select Find Checks & Issue Refund.

![Toast POS home screen with the Manager Activities section.](https://doc.toasttab.com/doc/media/refunds-locating-ck-in-pos-1.png)



Alternatively, from the Payment Terminal screen:

1. Select the overflow menu (the ⋮ icon) in the upper-right corner.


2. Select Advanced Check Search.

![Overflow menu on the Payment Terminal screen, which includes the Advanced Check Search option.](https://doc.toasttab.com/doc/media/refunds-locating-ck-in-pos-2.png)




2. To locate the check:

- By check number: Select Find by Check Number, enter the check's number, select a date in the calendar and select Search.


- By ID: Select Find by ID, enter a check ID, order ID, check GUID, or order GUID and select Search. IDs and GUIDs for checks and orders can be found on the [Order Details page](adminGuide-platformOrdersDetailsReportsAbout).


- By customer info: Select Find by Customer Info, enter the customer's phone number, first name, last name, or tab name, and select Search.


- By credit card: Select Find by Credit Card, enter the last 4 digits of the credit card number, and select Search.





### Locating a check in Toast Web

To locate a check in Toast Web:

1. Log in to Toast Web.


2. Scroll to the Quick Action section on the home page, then select Find checks & issue refund.


3. To locate the check:

- By check number: Select Find by Check Number, enter the check's number, select a date in the calendar and select Search.


- By ID: Select Find by ID, enter a check ID, order ID, check GUID, or order GUID and select Search. IDs and GUIDs for checks and orders can be found on the [Order Details page](adminGuide-platformOrdersDetailsReportsAbout).


- By customer info: Select Find by Customer Info, enter the customer's phone number, first name, last name, or tab name, and select Search.


- By credit card: Select Find by Credit Card, enter the last 4 digits of the credit card number, and select Search.





## Refunding items and service charges

One option for a refund is to refund specific items or service charges.

As you select items to refund, the Refund Total at the bottom of each screen is updated to reflect the current amount of the refund.

**Procedure 6.23. To issue a refund on a specific item or service charge:**

1. After you [locate the check to refund](adminGuide-adminIssuingARefund#adminLocatingACheckToRefund), select the Refund button, then select By Item(s).

![Refund drop-down menu to select the type of refund.](https://doc.toasttab.com/doc/media/refunds-refund-menu.png)


2. The next page displays the items and service charges for the selected order. This list includes both [gratuity and non-gratuity service charges](adminGuide-adminServiceChargeType).

![Screen to select the items and service charges to refund.](https://doc.toasttab.com/doc/media/refunds-on-items-and-service-chgs-2.png)

By default, none of the items and service charges are selected. To determine the items and quantities to refund:

1. In the Item column, select the boxes next to each item and service charge to refund.


2. Optionally, in the Quantity column, specify the quantity to refund for each item. By default, the entire quantity is refunded.

For example, an order contains two cheeseburgers. The list contains a single cheeseburger entry, with a Quantity value of 2. To refund only one of those cheeseburgers, change Quantity to 1.

You can also specify a fractional quantity for an item. For example, an item with a Quantity of 1 might represent a pound of pulled chicken or a half a pound of macaroni and cheese. You can then refund the value of some fraction of that amount. The fractional quantity can have up to two decimal places. The fractional quantity represents the fraction of the amount of the item. For example, an item represents eight ounces of meat. If the refund quantity is .5, then the refund is for the value of four ounces of meat. The refund is not for a half an ounce.

The quantity to refund must be less than or equal to the quantity ordered.


3. After you choose the items and quantities to refund, select Next.




  1. In the Item column, select the boxes next to each item and service charge to refund.


  2. Optionally, in the Quantity column, specify the quantity to refund for each item. By default, the entire quantity is refunded.

For example, an order contains two cheeseburgers. The list contains a single cheeseburger entry, with a Quantity value of 2. To refund only one of those cheeseburgers, change Quantity to 1.

You can also specify a fractional quantity for an item. For example, an item with a Quantity of 1 might represent a pound of pulled chicken or a half a pound of macaroni and cheese. You can then refund the value of some fraction of that amount. The fractional quantity can have up to two decimal places. The fractional quantity represents the fraction of the amount of the item. For example, an item represents eight ounces of meat. If the refund quantity is .5, then the refund is for the value of four ounces of meat. The refund is not for a half an ounce.

The quantity to refund must be less than or equal to the quantity ordered.


  3. After you choose the items and quantities to refund, select Next.


3. The next page displays the payment method with the current amount to refund based on your selections. For information about refunds for orders that have multiple payments, see [Refunding a check that has multiple payments](adminGuide-adminIssuingARefund#adminRefundingACheckWithMultiplePayments).

From this page, you can optionally refund some or all of the original tip.

In the Tip field, enter the amount of the tip to refund. Note that the Original Amountvalue for the tip does not include [gratuity service charges](adminGuide-adminServiceChargeType). These charges are listed on the previous screen.

![Screen to optionally refund some or all of the tip in addition to the selected items and service charges.](https://doc.toasttab.com/doc/media/refunds-on-items-and-service-chgs-3.png)

To continue, select Next.


4. Optionally, enter a comment to indicate the reason for the refund.

This comment appears in the Reports &gt; Cash and loss management &gt; Refunds report.

![Screen to enter additional comments for the refund.](https://doc.toasttab.com/doc/media/refunds-on-items-and-service-chgs-4.png)

To continue, select Next.


5. Review the amount that will be refunded based on your selections.

To change any of your refund selections, select Back until you reach the appropriate screen. Make your edits, then select Next to return to the confirmation screen.

![Confirmation screen for a refund.](https://doc.toasttab.com/doc/media/refunds-on-items-and-service-chgs-5.png)

To confirm your refund selections, select Confirm.


6. Select the receipt option based on how your guest would like to receive a receipt.

![Screen to select the receipt option for the refund.](https://doc.toasttab.com/doc/media/refunds-refund-processed.png)

Note that printed receipts are not available when you use the Toast Web to issue a refund.


7. After you complete your receipt selection, you see a Refund Completed message with the total refund amount.

![Refund Completed screen for a refund.](https://doc.toasttab.com/doc/media/refunds-on-items-and-service-chgs-7.png)

To close the message, select Ok.



## Refunding an entire check

The Entire check option contains the same steps and options as the By item(s) option. When you choose Entire check, all of the order items are selected by default. You can then de-select items and specify refund quantities. You can also choose to refund some or all of the tip.

As you select items to refund, the Refund Total at the bottom of each screen is updated to reflect the current amount of the refund.

**Procedure 6.24. To issue a refund on an entire check:**

1. After you [locate the check to refund](adminGuide-adminIssuingARefund#adminLocatingACheckToRefund), select the Refund button, then select Entire Check.


2. The next page displays the items and service charges for the selected order. This list includes both gratuity and non-gratuity service charges.

All of the items and service charges are selected.

![Screen to select the items and service charges to refund. By default, all items and service charges are selected.](https://doc.toasttab.com/doc/media/refunds-on-entire-ck-2.png)

1. To exclude an item or service charge from the refund, in the Item column, de-select the box next to that item or service charge.


2. Optionally, you can specify the quantity to refund for each item. By default, the entire quantity is refunded.

To enable the Quantity field, de-select the box next to the item, then select it again. In the Quantity field, set the quantity to refund.

For example, an order contains two cheeseburgers. The list contains a single cheeseburger entry, with a Quantity value of 2. To refund only one of those cheeseburgers, change Quantity to 1.

You can also specify a fractional quantity for an item. For example, an item with a Quantity of 1 might represent a pound of pulled chicken or a half a pound of macaroni and cheese. You can then refund the value of some fraction of that amount. The fractional quantity can have up to two decimal places. The fractional quantity represents the fraction of the amount of the item. For example, an item represents eight ounces of meat. If the refund quantity is .5, then the refund is for the value of four ounces of meat. The refund is not for a half an ounce.

The quantity to refund must be less than or equal to the quantity ordered.


3. After you confirm the selected items and quantities to refund, select Next.




  1. To exclude an item or service charge from the refund, in the Item column, de-select the box next to that item or service charge.


  2. Optionally, you can specify the quantity to refund for each item. By default, the entire quantity is refunded.

To enable the Quantity field, de-select the box next to the item, then select it again. In the Quantity field, set the quantity to refund.

For example, an order contains two cheeseburgers. The list contains a single cheeseburger entry, with a Quantity value of 2. To refund only one of those cheeseburgers, change Quantity to 1.

You can also specify a fractional quantity for an item. For example, an item with a Quantity of 1 might represent a pound of pulled chicken or a half a pound of macaroni and cheese. You can then refund the value of some fraction of that amount. The fractional quantity can have up to two decimal places. The fractional quantity represents the fraction of the amount of the item. For example, an item represents eight ounces of meat. If the refund quantity is .5, then the refund is for the value of four ounces of meat. The refund is not for a half an ounce.

The quantity to refund must be less than or equal to the quantity ordered.


  3. After you confirm the selected items and quantities to refund, select Next.


3. The next page displays the payment method with the current amount to refund based on your selections. For information about refunds for orders that have multiple payments, see [Refunding a check that has multiple payments](adminGuide-adminIssuingARefund#adminRefundingACheckWithMultiplePayments).

From this page, you can optionally refund some or all of the original tip.

In the Tip field, enter the amount of the tip to refund. Note that the Original Amountvalue for the tip does not include [gratuity service charges](adminGuide-adminServiceChargeType). These charges are listed on the previous screen.

![Screen to optionally refund some or all of the tip in addition to the selected items and service charges.](https://doc.toasttab.com/doc/media/refunds-on-entire-ck-3.png)

To continue, select Next.


4. Optionally, enter a comment to indicate the reason for the refund.

This comment appears in the Reports &gt; Cash and loss management &gt; Refunds report.

To continue, select Next.


5. On the confirmation screen, review the amount to refund based on your selections.

To change any of your refund selections, select Back until you reach the appropriate screen. Make your edits, then select Next to return to the confirmation screen.

![Confirmation screen for a refund.](https://doc.toasttab.com/doc/media/refunds-on-entire-ck-5.png)

To confirm your refund selections, select Confirm.


6. Select the receipt option based on how your guest would like to receive a receipt.

Note that printed receipts are not available when you use the Toast Web to issue a refund.


7. After you complete the receipt selection, you see a Refund Completed message with the total refund amount.

To close the message, select Ok.



## Refunding a tip only

The Tip only option allows you to refund some or all of the tip on an order.

You cannot use the Tip only option to refund a gratuity service charge. To refund a service charge, use the By item(s) or Entire checkoption.

**Procedure 6.25. To refund only the tip:**

1. After you [locate the check to refund](adminGuide-adminIssuingARefund#adminLocatingACheckToRefund), select the Refund button, then select Tip only.


2. On the next page, in the Tip field, enter the amount of the tip to refund.

For information about refunds for orders that have multiple payments, see [Refunding a check that has multiple payments](adminGuide-adminIssuingARefund#adminRefundingACheckWithMultiplePayments).

![Screen to enter the amount of the tip to refund.](https://doc.toasttab.com/doc/media/refunds-tip-only-2.png)

To continue, select Next.


3. Optionally, enter a comment to indicate the reason for the refund.

This comment appears in the Reports &gt; Cash and loss management &gt; Refunds report.

To continue, select Next.


4. On the confirmation screen, review the amount of the tip to refund.

To change any of your refund selections, select Back until you reach the appropriate screen. Make your edits, then select Next to return to the confirmation screen.

![Confirmation screen for a refund.](https://doc.toasttab.com/doc/media/refunds-tip-only-4.png)

To confirm your refund selections, select Confirm.


5. Select the receipt option based on how your guest would like to receive a receipt.

Note that printed receipts are not available when you use the Toast Web to issue a refund.


6. After you complete the receipt selection, you see a Refund Completed message with the total refund amount.

To close the message, select Ok.



## Refunding tax only

The Tax only option allows you to refund only the tax for an order. You can also optionally refund some or all of the order tip.

**Procedure 6.26. To refund the tax on an order:**

1. After you [locate the check to refund](adminGuide-adminIssuingARefund#adminLocatingACheckToRefund), select the Refund button, then select Tax only.


2. On the next page, the Refund Tax field displays the amount of the tax to refund.

In the Tax Exemption field, you can optionally provide a tax exemption number.

![Screen to review the refund amount on the tax, and to optionally enter a tax exemption number.](https://doc.toasttab.com/doc/media/refunds-tax-only-2.png)

To continue, select Next.


3. The next page displays the payment method with the tax amount to refund. For information about refunds for orders that have multiple payments, see [Refunding a check that has multiple payments](adminGuide-adminIssuingARefund#adminRefundingACheckWithMultiplePayments).

From this page, you can optionally refund some or all of the original tip.

In the Tip field, enter the amount of the tip to refund. Note that the Original Amountvalue for the tip does not include gratuity service charges.

![Screen to optionally refund some or all of the tip in addition to the tax.](https://doc.toasttab.com/doc/media/refunds-tax-only-3.png)

To continue, select Next.


4. On the next screen, optionally enter a comment to indicate the reason for the refund.

This comment appears in the Reports &gt; Cash and loss management &gt; Refunds report.

To continue, select Next.


5. On the confirmation screen, review the amount to refund based on your selections.

To change any of your refund selections, select Back until you reach the appropriate screen. Make your edits, then select Next to return to the confirmation screen.

![Confirmation screen for the refund.](https://doc.toasttab.com/doc/media/refunds-tax-only-5.png)

To confirm your refund selections, select Confirm.


6. Select the receipt option based on how your guest would like to receive a receipt.

Note that printed receipts are not available when you use the Toast Web to issue a refund.


7. After you complete the receipt selection, you see a Refund Completed message with the total refund amount.

To close the message, Select Ok.



## Refunding a custom amount on a payment

The Custom amount option allows you to specify a specific amount to refund, instead of selecting specific items or charges. When you refund a custom amount, you can also choose to refund some or all of the tip.

Custom amount refunds impact financial reporting differently from other refund types. For details, see [Custom amount refunds](adminGuide-adminViewingRefundsInToastReports#adminCustomAmountRefunds).

**Procedure 6.27. To refund a custom amount on an order:**

1. After you [locate the check to refund](adminGuide-adminIssuingARefund#adminLocatingACheckToRefund), select the Refund button, then select Custom amount.


2. The next page displays the payment method, with fields to specify the custom amount and tip amount to refund. For information about refunds for orders that have multiple payments, see [Refunding a check that has multiple payments](adminGuide-adminIssuingARefund#adminRefundingACheckWithMultiplePayments).

![Screen to enter the custom amount and tip amount to refund.](https://doc.toasttab.com/doc/media/refunds-on-custom-amt-2.png)

1. In the Amount field, specify the amount to refund. The Original Amount value reflects the total amount, including items, service charges, and tax. It does not include the tip.


2. In the Tip field, enter the amount of the tip to refund. Note that the Original Amount value for the tip does not include gratuity service charges.


3. To continue, select Next.




  1. In the Amount field, specify the amount to refund. The Original Amount value reflects the total amount, including items, service charges, and tax. It does not include the tip.


  2. In the Tip field, enter the amount of the tip to refund. Note that the Original Amount value for the tip does not include gratuity service charges.


  3. To continue, select Next.


3. On the next screen, optionally enter a comment to indicate the reason for the refund.

This comment appears in the Reports &gt; Cash and loss management &gt; Refunds report.

To continue, select Next.


4. On the confirmation screen, review the amount to refund based on your selections.

To change any of your refund selections, select Back until you reach the appropriate screen. Make your edits, then select Next to return to the confirmation screen.

![Confirmation screen for the refund.](https://doc.toasttab.com/doc/media/refunds-on-custom-amt-4.png)

To confirm your refund selections, select Confirm.


5. Select the receipt option based on how your guest would like to receive a receipt.

Note that printed receipts are not available when you use the Toast Web to issue a refund.


6. After completing your receipt selection, you see a Refund Completed message with the refund amount.

To close the message, select Ok.



## Refunding a check that has multiple payments

In the refund process, the payment screen displays the payment for the refunded check:

- For refunds by item, refunds of an entire check, and tax refunds, the payment screen shows the amount of the refund based on your selections, and allows you to specify the amount of the tip refund.


- For custom amount refunds, the payment screen allows you to specify the amount of the check refund and the tip refund.


- For tip only refunds, the payment screen allows you to specify the amount of the tip refund.



When a refunded check contains multiple payments, you can distribute the refund among those payments.

### Information about multiple payments on the payment screen

The payment screen displays all of the eligible payments. For each payment, the screen shows the amount paid toward the check and the tip. You can then specify the refund values for each payment.

In the following example, the Amount field for each payment is $35.31, and the Tip for each payment is $3.53. In other words, the two payers split a $70.62 check and each added a $3.53 tip.

![Payment screen with multiple payments.](https://doc.toasttab.com/doc/media/refunds-multiple-payments-0.png)

The screen does not display payment types that are not eligible for refunds:

- If you issue the refund from a Toast POS device, then cash payments are not included in the list. Cash refunds must be issued from the Toast POS.


- The payment list can only include cash, credit card, and Toast gift card payments.

The payment list never includes other payment types, house accounts, and third-party gift cards. For information on how to remove those payments, see [Removing other payments, house accounts, and third-party gift cards](adminGuide-adminIssuingARefund#adminRemovingOtherPaymentsHouseAccountsAndThirdPartyGiftCards).



### Distributing refunds for item, entire check, and tax refunds

For refunds by item, entire check refunds, and tax refunds, the banner at the top of the payment screen initially shows the amount of the refund based on your selections. As you enter values in the Amount fields, the banner is updated to indicate the remaining refund amount to distribute.

In the following example, the selected refund amount is 19.26. The values in the Amount fields must add up to 19.26.

![Multiple payments screen for item, entire check, and tax refunds.](https://doc.toasttab.com/doc/media/refunds-multiple-payments-1.png)

### Distributing refunds for custom value and tip only refunds

For custom value refunds and tip only refunds, the banner at the top of the page initially shows the total check amount before the tip.

For tip only refunds, the Amount fields are disabled.

![Multiple payments screen for a custom value or a tip only refund.](https://doc.toasttab.com/doc/media/refunds-multiple-payments-2.png)

### Refunds for payments that were not included in the original refund

If you do not specify a refund value for a payment when you refund a multi-payment check, then to issue a refund against that payment method later on, you must use the custom value refund method.

For example, you issue a refund against a $40.00 check that has two credit card payments. You refund $15.00 to one of the credit cards, but do not refund anything to the other credit card. To issue a refund to the other credit card, you must use a custom value refund.

## Removing other payments, house accounts, and third-party gift cards

To reverse payments made using house accounts, third-party gift cards or other payment types, you must use the Remove workflow, which is available from the Pay screen on the Toast POS app. You cannot remove these payments from Toast Web.

Payment removals are not considered refunds. They do not appear as refunds in Toast reporting.

You can remove these payments at any time, unless they are on a [restricted check](adminGuide-index).

Restricted checks are checks that have reached a certain age, by default 90 days. Restricted checks cannot be pulled back to the Toast POS app and edited. So after a check passes 90 days, you cannot reverse payments on it.

To change the restricted check age to something other than 90 days, contact Toast Support.

