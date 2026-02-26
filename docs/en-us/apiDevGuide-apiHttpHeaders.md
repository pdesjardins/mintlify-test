---
title: "HTTP headers"
id: apiHttpHeaders
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiUsingWebhooksOmitChunkFromSearchIndex.md
parentSectionTitle: "Using webhooks"
previousSectionFile: apiDevGuide-apiMessageDataSchema.md
previousSectionTitle: "Message data schema"
nextSectionFile: apiDevGuide-apiTimeouts.md
nextSectionTitle: "Timeouts"
externalReferences: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers]
excerpt: "Webhook updates include a set of HTTP headers, some of which are standard HTTP headers and some of which are Toast-specific. This section provides more details on both types."
keywords: ["http", "headers"]
procedures: 0
codeExamples: 0
---

Webhook updates include a set of HTTP headers, some of which are standard HTTP headers and some of which are Toast-specific. This section provides more details on both types.

- [Toast-specific HTTP headers](apiDevGuide-apiHttpHeaders#apiToastSpecificHttpHeaders)


- [Standard HTTP headers](apiDevGuide-apiHttpHeaders#apiStandardHttpHeaders)



## Toast-specific HTTP headers

The following table describes the Toast-specific HTTP headers included with webhook events.


<table>
  <thead>
    <tr>
      <th>Header</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`Toast-Attempt-Number`</td>
      <td>Indicates how many times the Toast platform has sent the webhook message. <br/> The first time the Toast platform sends a webhook message, the `Toast-Attempt-Number` is `1`. If the Toast platform retries sending the message, it increments the number. For information about retrying webhook messages, see [Retry support](apiDevGuide-apiRetrySupport).</td>
    </tr>
    <tr>
      <td>`Toast-Signature`</td>
      <td>As a security measure, all webhook messages contain a signature in the `Toast-Signature` HTTP header. A webhook endpoint uses the `Toast-Signature` header to confirm that a webhook update message is coming from a known, secure source. See [Message signing](apiDevGuide-apiMessageSigning) for more details.</td>
    </tr>
    <tr>
      <td>`Toast-Event-Type`</td>
      <td>The type of event that has occurred, for example, a `partner_added` event for the `partners` webhook or a `low_quantity` event for the `stock` webhook.</td>
    </tr>
    <tr>
      <td>`Toast-Restaurant-External-ID`</td>
      <td>If the triggering event has occurred at a restaurant, the GUID of that restaurant is included in the `Toast-Restaurant-External-ID` HTTP header, for example, if the webhook update is for a `low_quantity` event, this header identifies the restaurant where the inventory quantity is low. This header is omitted if the triggering event has not occurred at a restaurant, for example, the header is omitted for the Partners webhook event types because those events are triggered by changes to a partner's status, not changes to a restaurant's status.</td>
    </tr>
    <tr>
      <td>`Toast-Event-Category`</td>
      <td>The event category, for example, `partners` or `stock`. </td>
    </tr>
  </tbody>
</table>

## Standard HTTP headers

In addition to the Toast-specific HTTP headers, webhook events include the standard HTTP headers shown in the table below. For more detailed information on these headers, see [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers):


<table>
  <thead>
    <tr>
      <th>Header</th>
      <th>Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`Accept-Encoding`</td>
      <td>`gzip,deflate`</td>
    </tr>
    <tr>
      <td>`Connection`</td>
      <td>`close`</td>
    </tr>
    <tr>
      <td>`Content-Length`</td>
      <td>The size of the message body, in bytes.</td>
    </tr>
    <tr>
      <td>`Content-Type`</td>
      <td>`application/json`</td>
    </tr>
    <tr>
      <td>`Host`</td>
      <td>The domain name and port of the server that is listening for webhook events. Generated from the partner URI that is specified when a webhook subscription is created.</td>
    </tr>
    <tr>
      <td>`User-Agent`</td>
      <td>`Apache-HttpClient/4.5.10
              (Java/1.8.0_212)`</td>
    </tr>
  </tbody>
</table>

