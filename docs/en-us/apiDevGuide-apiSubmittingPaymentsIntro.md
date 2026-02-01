---
title: "Submitting payments"
id: apiSubmittingPaymentsIntro
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalSubmittingPaymentsOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating payment information"
previousSectionFile: apiDevGuide-portalSubmittingPaymentsOmitChunkFromSearchIndex.md
previousSectionTitle: "Updating payment information"
nextSectionFile: apiDevGuide-authorizingCcPayments.md
nextSectionTitle: "Credit card payments"
excerpt: "To indicate that a guest paid for an order on your ordering application, the orders that you submit must contain payment information."
procedures: 0
codeExamples: 0
---

### Submitting payments

To indicate that a guest paid for an order on your ordering application, the orders that you submit must contain payment information.

If you use the Toast platform as your credit card payment processor, you [submit payments through Toast's credit card API](authorizingCcPayments.html).

If you use a credit card payment processor outside of the Toast platform, or you submit payments that are not credit card payments, you [submit payments using alternative payment types](apiCreatingAnOrderWithPaymentInformation.html). For example, you use an alternative payment type to submit cash payments.

