---
title: "Gift card integration overview"
id: apiGiftCardIntegrationOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingGiftCardIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Gift Card Integrations"
previousSectionFile: apiDevGuide-apiBuildingGiftCardIntegrationOmitChunkFromSearchIndex.md
previousSectionTitle: "Gift Card Integrations"
nextSectionFile: apiDevGuide-apiGiftCardIntegrationWorkflow.md
nextSectionTitle: "Gift card integration workflow"
externalReferences: [https://doc.toasttab.com/openapi/giftcards/overview/]
excerpt: "This section explains how to implement an integration with the Toast platform that allows the Toast POS to process gift card transactions using your gift card provider service."
keywords: [gift,card,integration,overview]
procedures: 0
codeExamples: 0
---

### Gift card integration overview

This section explains how to implement an integration with the Toast platform that allows the Toast POS to process gift card transactions using your gift card provider service.

You can integrate your gift card provider service with the Toast platform by implementing an API that can handle REST HTTP requests that the Toast platform sends to it. The Toast gift card API specification describes the required functionality of a REST web service that will handle Toast POS gift card transactions. For more information, see reference documentation in the [gift card integration API reference documentation](https://doc.toasttab.com/openapi/giftcards/overview/).



> **Note**
> 
> Toast Gift Card balances cannot be retrieved using the Toast APIs.


When a restaurant employee processes a gift card transaction, the Toast platform sends one or more REST HTTP requests to your integration API implementation. The requests include information about the transaction. Your integration API implementation attempts to process the transaction and returns information about the result of that attempt in the HTTP response to the request. The Toast platform continues processing the gift card transaction based on the information your implementation sends.

The following diagram shows the relationship between the Toast platform and a gift card provider when processing gift card transactions.

![A diagram showing the REST HTTP request and response interactions between the Toast platform and a gift card provider.](https://doc.toasttab.com/doc/media/gift-card-integration-overview.png)



> **Important**
> 
> Your gift card API implementation must use HTTPS for all REST requests and responses.




> **Note**
> 
> Toast Online Ordering functionality supports gift card integrations only if your integration supports verification codes (PINs). For more information, see [Verification Codes (PINs)](apiGiftCardIntegrationWorkflow.html#apiGiftCardIntegrationVerificationsCodes).


