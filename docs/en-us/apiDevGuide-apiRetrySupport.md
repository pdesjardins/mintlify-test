---
title: "Retry support"
id: apiRetrySupport
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiUsingWebhooksOmitChunkFromSearchIndex.md
parentSectionTitle: "Using webhooks"
previousSectionFile: apiDevGuide-apiTimeouts.md
previousSectionTitle: "Timeouts"
nextSectionFile: apiDevGuide-apiMessageSigning.md
nextSectionTitle: "Message signing"
excerpt: "The Toast platform attempts to resend updates to a webhook endpoint in the following circumstances:"
keywords: ["retry", "support"]
procedures: 0
codeExamples: 0
---

The Toast platform attempts to resend updates to a webhook endpoint in the following circumstances:

- There is a timeout when connecting to, sending to, or receiving from the webhook endpoint. See [Timeouts](apiTimeouts.html) for more information.


- The endpoint returns an HTTP 404 (not found) response code.


- The endpoint returns an HTTP 429 (too many requests) response code.


- The endpoint returns an HTTP 5xx response code.



For the conditions above, the Toast platform will wait five minutes and then resend the update. If the resent update also results in one of the conditions above, then the Toast platform will wait 10 minutes and resend the update a second time. If the second resend attempt fails, the Toast platform does not send the update again.



> **Note**
> 
> Restaurant availability updates will retry five times in a minute with exponential back-off.


The Toast platform does not attempt to resend an update if:

- The endpoint returns an HTTP 4xx response code other than 404 (not found) or 429 (too many requests).


- The endpoint returns an HTTP 3xx response code.



