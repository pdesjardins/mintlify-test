---
title: "Updating payment information"
id: portalSubmittingPaymentsOmitChunkFromSearchIndex
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingPaymentInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 3. Payments"
previousSectionFile: apiDevGuide-apiPaymentntInformation.md
previousSectionTitle: "Getting information about a specific payment"
nextSectionFile: apiDevGuide-authorizingCcPayments.md
nextSectionTitle: "Credit card payments"
procedures: 0
codeExamples: 0
---

## Updating payment information

### Submitting payments

To indicate that a guest paid for an order on your ordering application, the orders that you submit must contain payment information.

If you use the Toast platform as your credit card payment processor, you [submit payments through Toast's credit card API](authorizingCcPayments.html).

If you use a credit card payment processor outside of the Toast platform, or you submit payments that are not credit card payments, you [submit payments using alternative payment types](apiCreatingAnOrderWithPaymentInformation.html). For example, you use an alternative payment type to submit cash payments.

