---
title: "Message data schema"
id: apiMessageDataSchema
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiUsingWebhooksOmitChunkFromSearchIndex.md
parentSectionTitle: "Using webhooks"
previousSectionFile: apiDevGuide-apiSubscriptions.md
previousSectionTitle: "Subscriptions"
nextSectionFile: apiDevGuide-apiHttpHeaders.md
nextSectionTitle: "HTTP headers"
excerpt: "Webhook messages are always sent as JSON payloads in the body of POST requests. The message is sent with Content-Type: application/json."
keywords: ["message", "data", "schema", "Content-Type: application/json"]
procedures: 0
codeExamples: 1
---

Webhook messages are always sent as JSON payloads in the body of POST requests. The message is sent with `Content-Type:
    application/json`.

Regardless of the event category, the data in the message that is published to your endpoint follows the same schema:

```
{
    "timestamp": “`\<ISO formatted timestamp in UTC\>`”,
    "eventCategory": "`\<eventCategory\>`",
    "eventType": "`\<eventType\>`",
    "guid": "`\<eventGuid\>`",
    "details": {
        `\<eventType specific payload\>`
  }
}
```

For reference information on the payload returned for specific event categories, see [Webhooks reference](apiDevGuide-apiWebhooksReference).

