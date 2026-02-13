---
title: "Timeouts"
id: apiTimeouts
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiUsingWebhooksOmitChunkFromSearchIndex.md
parentSectionTitle: "Using webhooks"
previousSectionFile: apiDevGuide-apiHttpHeaders.md
previousSectionTitle: "HTTP headers"
nextSectionFile: apiDevGuide-apiRetrySupport.md
nextSectionTitle: "Retry support"
excerpt: "In order..."
keywords: ["timeouts"]
procedures: 0
codeExamples: 0
---

In order to keep the Toast platform's webhook support operating with
    optimum performance, timeouts are enforced on requests sent to webhook
    endpoints. This protects the webhook system from endpoints that may be
    experiencing issues or are poorly implemented. Currently, these timeouts
    are:

- Connection timeout: If the Toast platform experiences a timeout
        greater than 2 seconds while trying to connect to the webhook
        endpoint, it will abandon the update request.



> **Important**
> 
> Toast API clients must return a 2xx response within the
          2-second window to acknowledge the event, before processing any
          additional business logic.



- Socket timeout: If the Toast platform experiences a timeout
        longer than 2 seconds while sending an update request or while waiting
        for a webhook endpoint to acknowledge receipt of a request, it will
        abandon the request.



