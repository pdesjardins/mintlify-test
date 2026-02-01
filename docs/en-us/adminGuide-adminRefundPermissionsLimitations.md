---
title: "Refund permissions and limitations"
id: adminRefundPermissionsLimitations
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminRefundsOmitChunkFromSearchIndex.md
parentSectionTitle: "Refunds"
previousSectionFile: adminGuide-adminRefundsOmitChunkFromSearchIndex.md
previousSectionTitle: "Refunds"
nextSectionFile: adminGuide-adminRefundsAndVoids.md
nextSectionTitle: "Refunds and voids"
excerpt: "The refund process allows you to issue refunds to guests. The process is available from the Toast POS and Toast Web."
keywords: [refund,permissions,limitations]
procedures: 0
codeExamples: 0
---

### Refund permissions and limitations

The refund process allows you to issue refunds to guests. The process is available from the Toast POS and Toast Web.

Before an employee can issue a refund, they must be given permission to find checks and refund payments.

There are also limitations and recommendations around the types of payments that support refunds, and when you can issue cash and credit card refunds.

#### Refund permissions

To be able to issue refunds, an employee must have the following permissions:



****Manager \> Find Checks****
: This permission allows employees to locate a check to refund.



****Manager \> Void / Refund Payments****
: This permission allows employees to issue refunds.





**Procedure 6.22. To grant the required permissions to an employee:**

1. Navigate to Employees \> Employee management \> Employees.


2. In the Actions column for the employee, select the pencil icon.


3. Click Jobs and permissions.


4. In the Permissions list, under Manager, enable the Void / Refund Payments and Find Checkspermissions.

For each permission:

1. Click Override.


2. Select the Allow check box.




  1. Click Override.


  2. Select the Allow check box.


5. Click Save.



#### Allowed payment types for refunds

You can issue refunds on checks that have credit card, cash, or Toast gift card payments on them.

You cannot refund payments that were made using other payment types, house accounts, or third-party gift cards. For information on how to remove these payments, see [Removing other payments, house accounts, and third-party gift cards](adminIssuingARefund.html#adminRemovingOtherPaymentsHouseAccountsAndThirdPartyGiftCards).

#### Cash refunds

You can only issue refunds on cash payments in the Toast POS app. You cannot refund cash payments from Toast Web.

Toast support strongly recommends that you issue cash refunds on a Toast POS device that is associated with a cash drawer. This allows the refund to appear in the cash drawer's report.

When you issue a cash refund on a device that is not associated with a cash drawer, there is no cash drawer report to log the refund to. There will be no record of the cash refund in your reports.

#### Credit card refunds

You can refund credit card or Toast gift card payments in either the Toast POS app or in Toast Web.

Credit card payments can only be refunded once. If you issue a partial refund on a credit card payment, you cannot issue a second refund on that same credit card to refund the remaining amount of the original payment.

Credit card payments can only be refunded up to 90 days after they are completed.

When you reverse a credit card payment on the same day that it is taken, before it is captured and settled, it is considered a void, not a refund. Voided credit card payments display in the Reports \> Cash and loss management \> Voided paymentsreport.

