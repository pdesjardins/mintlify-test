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
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Header</div></th>
      <th className=""><div className="">Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Toast-Attempt-Number</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Indicates how many times the Toast platform has sent the webhook message.</p> <p className="text-base leading-relaxed">The first time the Toast platform sends a webhook message, the <code className="font-mono text-sm">Toast-Attempt-Number</code> is <code className="font-mono text-sm">1</code>. If the Toast platform retries sending the message, it increments the number. For information about retrying webhook messages, see <a href="apiDevGuide-apiRetrySupport" className="">Retry support</a>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Toast-Signature</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">As a security measure, all webhook messages contain a signature in the <code className="font-mono text-sm">Toast-Signature</code> HTTP header. A webhook endpoint uses the <code className="font-mono text-sm">Toast-Signature</code> header to confirm that a webhook update message is coming from a known, secure source. See <a href="apiDevGuide-apiMessageSigning" className="">Message signing</a> for more details.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Toast-Event-Type</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The type of event that has occurred, for example, a <code className="font-mono text-sm">partner_added</code> event for the <code className="font-mono text-sm">partners</code> webhook or a <code className="font-mono text-sm">low_quantity</code> event for the <code className="font-mono text-sm">stock</code> webhook.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Toast-Restaurant-External-ID</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If the triggering event has occurred at a restaurant, the GUID of that restaurant is included in the <code className="font-mono text-sm">Toast-Restaurant-External-ID</code> HTTP header, for example, if the webhook update is for a <code className="font-mono text-sm">low_quantity</code> event, this header identifies the restaurant where the inventory quantity is low. This header is omitted if the triggering event has not occurred at a restaurant, for example, the header is omitted for the Partners webhook event types because those events are triggered by changes to a partner's status, not changes to a restaurant's status.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Toast-Event-Category</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The event category, for example, <code className="font-mono text-sm">partners</code> or <code className="font-mono text-sm">stock</code>. </p></div></td>
    </tr>
  </tbody>
</table>
</div>

## Standard HTTP headers

In addition to the Toast-specific HTTP headers, webhook events include the standard HTTP headers shown in the table below. For more detailed information on these headers, see [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers):


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Header</div></th>
      <th className=""><div className="">Value</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Accept-Encoding</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">gzip,deflate</code></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Connection</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">close</code></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Content-Length</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The size of the message body, in bytes.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Content-Type</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">application/json</code></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Host</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The domain name and port of the server that is listening for webhook events. Generated from the partner URI that is specified when a webhook subscription is created.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">User-Agent</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Apache-HttpClient/4.5.10 (Java/1.8.0_212)</code></p></div></td>
    </tr>
  </tbody>
</table>
</div>

