---
title: "Network failure and idempotence"
id: apiLoyaltyIntegrationNetworkFailureAndIdempotence
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Loyalty program integrations"
previousSectionFile: apiDevGuide-apiLoyaltyLatencyRequirements.md
previousSectionTitle: "Latency requirements"
nextSectionFile: apiDevGuide-apiLoyaltyIntegrationAuthentication.md
nextSectionTitle: "Loyalty integration authentication"
excerpt: "The..."
keywords: ["network", "failure", "idempotence", "LOYALTY_REVERSE", "Toast-Transaction-GUID", "LOYALTY_ACCRUE", "LOYALTY_REDEEM"]
procedures: 0
codeExamples: 0
---

### Network failure and idempotence

The Toast loyalty integration API will retry a request if it does not receive a response from your API implementation (for example, because of a network failure). The Toast API does not indicate that the request is a duplicate of an earlier transaction request. When the Toast loyalty integration API sends a duplicate request, your API implementation must return a cached, duplicate response containing the result of the operation.

Toast's retry logic varies by transaction type:

- If your endpoint returns a failure response to a `LOYALTY_REVERSE` request, the Toast loyalty integration API will retry the request and will send the same `Toast-Transaction-GUID` as the original request.


- If your endpoint returns a failure response to a `LOYALTY_ACCRUE` request, the Toast loyalty integration API will retry the request and will send a different `Toast-Transaction-GUID` than the original request.


- If your endpoint returns a failure response to a `LOYALTY_REDEEM` request, the Toast loyalty integration API will not retry the request.



