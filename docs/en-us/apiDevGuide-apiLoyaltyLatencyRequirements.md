---
title: "Latency requirements"
id: apiLoyaltyLatencyRequirements
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Loyalty program integrations"
previousSectionFile: apiDevGuide-apiLoyaltyErrorHandling.md
previousSectionTitle: "Error handling"
nextSectionFile: apiDevGuide-apiLoyaltyIntegrationNetworkFailureAndIdempotence.md
nextSectionTitle: "Network failure and idempotence"
excerpt: "The..."
keywords: [latency,requirements]
procedures: 0
codeExamples: 0
---

### Latency requirements

The Toast platform expects a 500ms average response time from your loyalty program integration. The maximum response time must be 5s seconds, after which point the Toast platform may close the socket and send another request.

Response times should be as short as possible because during a loyalty program transaction, a restaurant employee is at a Toast POS device and waiting for the loyalty response.

