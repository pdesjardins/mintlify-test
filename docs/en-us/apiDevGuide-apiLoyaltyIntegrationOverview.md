---
title: "Loyalty integration implementation"
id: apiLoyaltyIntegrationOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Loyalty program integrations"
previousSectionFile: apiDevGuide-apiLoyaltyProgramIntegrationOverview.md
previousSectionTitle: "Loyalty program integration overview"
nextSectionFile: apiDevGuide-apiLoyaltyTransactionDescriptions.md
nextSectionTitle: "Transaction types"
externalReferences: [https://doc.toasttab.com/openapi/loyalty/overview/]
excerpt: "You can integrate your loyalty program with the Toast platform by implementing an API that can handle REST HTTPS requests that the Toast platform sends to it. The Toast loyalty integration API..."
keywords: [loyalty,integration,implementation]
procedures: 0
codeExamples: 0
---

### Loyalty integration implementation

You can integrate your loyalty program with the Toast platform by implementing an API that can handle REST HTTPS requests that the Toast platform sends to it. The Toast loyalty integration API specification describes the required functionality of a REST web service that will handle Toast platform loyalty program transactions. For more information, see reference documentation in the [loyalty integration API reference documentation](https://doc.toasttab.com/openapi/loyalty/overview/).

When a Toast platform restaurant employee handles a sale transaction, the employee can use a Rewards function to find the guest's loyalty account. Once the Toast platform has the account for the guest, it exchanges information with your loyalty program service to present rewards offers and perform other operations. For information about the web services requests that the Toast platform sends for loyalty program transactions, see [Transaction types](apiDevGuide-apiLoyaltyTransactionDescriptions.html).

In your implementation of the Toast loyalty integration API, you create a single HTTPS REST endpoint, named in any way you choose. For example: `https://`myapi.mycompany.com`/`myendpointname``. The Toast platform sends requests to that single endpoint (host name and path) for all loyalty program transactions. You can identify the requests for specific transaction types using the *`Toast-Transaction-Type`* HTTP header parameter for each request that you receive.

