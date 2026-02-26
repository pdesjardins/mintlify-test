---
title: "Using Toast outbound APIs"
id: apiUsingToastOutboundApis
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalOutboundApiOverviewOmitChunkFromSearchIndex.md
parentSectionTitle: "Outbound API overview"
previousSectionFile: apiDevGuide-portalOutboundApiOverviewOmitChunkFromSearchIndex.md
previousSectionTitle: "Outbound API overview"
nextSectionFile: apiDevGuide-apiAuthenticatingRequestsFromToastApiClients.md
nextSectionTitle: "Authenticating outbound API requests"
excerpt: "You can use Toast outbound APIs to integrate restaurant services with the Toast platform. A Toast outbound API includes a REST API server specification that your organization implements and..."
procedures: 0
codeExamples: 0
---

You can use Toast outbound APIs to integrate restaurant services with the Toast platform. A Toast outbound API includes a REST API server specification that your organization implements and maintains. In a Toast outbound API integration, the Toast platform acts as the API client, and sends HTTP requests to your organization's API server. For example, the Toast platform might send API requests to your organization's outbound API server during a Toast POS app workflow to integrate a gift card, loyalty program, or other restaurant service.

The following diagram shows the Toast platform making HTTP requests as an API client and receiving HTTP responses from the API server that your organization implements.

![A diagram showing the Toast platform making HTTP requests as an API client and receiving HTTP responses from your organization's API server.](https://doc.toasttab.com/doc/media/toast-outbound-apis.png)

A Toast outbound API is similar to a webhook in that the Toast platform sends HTTP messages to your organization to communicate about specific Toast platform events. Toast outbound APIs include richer information about Toast platform operations than a webhook and directly interact with your organization's API implementation based on its HTTP responses in a way that is more dynamic than webhooks. For information about Toast platform webhooks, see [Webhook basics](docs/en-us/apiDevGuide-apiWebhookBasics).

