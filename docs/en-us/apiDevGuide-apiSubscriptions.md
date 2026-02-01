---
title: "Subscriptions"
id: apiSubscriptions
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiUsingWebhooksOmitChunkFromSearchIndex.md
parentSectionTitle: "Using webhooks"
previousSectionFile: apiDevGuide-apiEndpointRequirements.md
previousSectionTitle: "Endpoint requirements"
nextSectionFile: apiDevGuide-apiMessageDataSchema.md
nextSectionTitle: "Message data schema"
excerpt: "After..."
keywords: [subscriptions]
procedures: 0
codeExamples: 0
---

### Subscriptions

After you have created a webhook endpoint, you work with the Toast Integrations team to have your webhook subscription created. The subscription registers a webhook endpoint in the Toast platform and creates an association between the partner that owns the webhook endpoint and the event categories that will be sent to the endpoint. The subscription also defines the [webhook secret](apiMessageSigning.html) that is used for verifying the authenticity of a message and its contents.

After the subscription has been created, your endpoint will receive updates as they happen in the Toast platform. To unsubscribe from the webhook, you must contact the Toast Integrations team.

