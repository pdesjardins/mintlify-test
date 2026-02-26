---
title: "Endpoint requirements"
id: apiEndpointRequirements
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiUsingWebhooksOmitChunkFromSearchIndex.md
parentSectionTitle: "Using webhooks"
previousSectionFile: apiDevGuide-apiWebhookBasics.md
previousSectionTitle: "Webhook basics"
nextSectionFile: apiDevGuide-apiSubscriptions.md
nextSectionTitle: "Subscriptions"
excerpt: "The Toast..."
keywords: ["endpoint", "requirements"]
procedures: 0
codeExamples: 0
---

The Toast platform publishes updates to a webhook endpoint as they happen. It is possible, but not required, to use the same webhook endpoint for multiple event categories. The specifics of the data posted to the endpoint allow you to determine which event category generated the update.

To work correctly with the Toast platform, a webhook endpoint:

- MUST support the HTTP/1.1 protocol.


- MUST support HTTPS and use a valid TLS1.2 (or better) certificate.


- MUST support the POST method. Updates are published as a POST request.


- SHOULD ensure idempotency of update processing. When [retry support](apiDevGuide-apiRetrySupport) is implemented, it will be possible for updates to be sent to your endpoint more than once and the endpoint must account for these redundant updates. Toast Integrations will provide more information on how to manage this situation at a future date.


- SHOULD return a 2xx response code for a successful POST as soon as possible and perform any internal processing asynchronously. Timeouts are imposed on POST requests to prevent unnecessary delays.


- MUST NOT return a 3xx response code. Redirects are not followed.


- SHOULD NOT return a 4xx response code. In general, the Toast platform will not resend updates after receiving a 4xx response code. The two exceptions will be for the 404 Page Not Found error and the 429 Too Many Requests error. A 404 Page Not Found code can be returned by the proxies, gateways, or load balancers that manage a request on its way to a webhook endpoint. If the Toast platform receives a 404 response code, it will assume that the webhook payload was not delivered to the endpoint and it will try to resend the update. See [Retry support](apiDevGuide-apiRetrySupport) for more information.


- MUST be publicly accessible and should not require authentication. See [Message signing](apiDevGuide-apiMessageSigning) for information on verifying messages.



