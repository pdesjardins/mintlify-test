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


<div className="table-wrapper">
<table>
  <thead>
    <tr>
      <th>Header</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>Toast-Attempt-Number</code></td>
      <td>Indicates how many times the Toast platform has sent the webhook message. <br/> The first time the Toast platform sends a webhook message, the <code>Toast-Attempt-Number</code> is <code>1</code>. If the Toast platform retries sending the message, it increments the number. For information about retrying webhook messages, see <a href="apiDevGuide-apiRetrySupport">Retry support</a>.</td>
    </tr>
    <tr>
      <td><code>Toast-Signature</code></td>
      <td>As a security measure, all webhook messages contain a signature in the <code>Toast-Signature</code> HTTP header. A webhook endpoint uses the <code>Toast-Signature</code> header to confirm that a webhook update message is coming from a known, secure source. See <a href="apiDevGuide-apiMessageSigning">Message signing</a> for more details.</td>
    </tr>
    <tr>
      <td><code>Toast-Event-Type</code></td>
      <td>The type of event that has occurred, for example, a <code>partner_added</code> event for the <code>partners</code> webhook or a <code>low_quantity</code> event for the <code>stock</code> webhook.</td>
    </tr>
    <tr>
      <td><code>Toast-Restaurant-External-ID</code></td>
      <td>If the triggering event has occurred at a restaurant, the GUID of that restaurant is included in the <code>Toast-Restaurant-External-ID</code> HTTP header, for example, if the webhook update is for a <code>low_quantity</code> event, this header identifies the restaurant where the inventory quantity is low. This header is omitted if the triggering event has not occurred at a restaurant, for example, the header is omitted for the Partners webhook event types because those events are triggered by changes to a partner's status, not changes to a restaurant's status.</td>
    </tr>
    <tr>
      <td><code>Toast-Event-Category</code></td>
      <td>The event category, for example, <code>partners</code> or <code>stock</code>. </td>
    </tr>
  </tbody>
</table>
</div>

## Standard HTTP headers

In addition to the Toast-specific HTTP headers, webhook events include the standard HTTP headers shown in the table below. For more detailed information on these headers, see [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers):


<div className="table-wrapper">
<table>
  <thead>
    <tr>
      <th>Header</th>
      <th>Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>Accept-Encoding</code></td>
      <td><code>gzip,deflate</code></td>
    </tr>
    <tr>
      <td><code>Connection</code></td>
      <td><code>close</code></td>
    </tr>
    <tr>
      <td><code>Content-Length</code></td>
      <td>The size of the message body, in bytes.</td>
    </tr>
    <tr>
      <td><code>Content-Type</code></td>
      <td><code>application/json</code></td>
    </tr>
    <tr>
      <td><code>Host</code></td>
      <td>The domain name and port of the server that is listening for webhook events. Generated from the partner URI that is specified when a webhook subscription is created.</td>
    </tr>
    <tr>
      <td><code>User-Agent</code></td>
      <td><code>Apache-HttpClient/4.5.10 (Java/1.8.0_212)</code></td>
    </tr>
  </tbody>
</table>
</div>

