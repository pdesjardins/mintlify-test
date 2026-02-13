---
title: "Refunds and voids"
id: adminRefundsAndVoids
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminRefundsOmitChunkFromSearchIndex.md
parentSectionTitle: "Refunds"
previousSectionFile: adminGuide-adminRefundPermissionsLimitations.md
previousSectionTitle: "Refund permissions and limitations"
nextSectionFile: adminGuide-adminIssuingARefund.md
nextSectionTitle: "Issuing a refund"
excerpt: "You can void items in an order until a payment is captured. After the payment is captured, you must refund the payment on the items."
keywords: ["refunds", "voids"]
procedures: 0
codeExamples: 0
---



> **Note**
> 
> When voiding payments, use the Toast POS device that the cash payment was originally taken on. Voiding cash payments on a different device can cause reporting problems and discrepancies in shift review.


You can void items in an order until a payment is captured. After the payment is captured, you must refund the payment on the items.



> **Important**
> 
> Do not attempt to void items before or after you issue a refund on a check. Voiding items before or after you issue a refund can cause problems with Toast POS behavior and Toast reporting information.


For credit card payments, the payment is considered captured when it completes the credit card capture process. Voided credit card payments display in the Reports &gt; Cash and loss management &gt; Voided payments report.

Cash payments and Toast gift card payments are considered captured at the end of that business day. Toast support configures the restaurant business day cutoff for each restaurant. The cutoff typically is set to 4:00 AM.

