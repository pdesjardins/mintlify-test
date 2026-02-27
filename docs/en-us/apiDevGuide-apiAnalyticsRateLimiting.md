---
title: "Analytics API rate limits"
id: apiAnalyticsRateLimiting
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiAboutAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "About the analytics API"
previousSectionFile: apiDevGuide-apiAnalyticsScope.md
previousSectionTitle: "Required scope for the analytics API"
nextSectionFile: apiDevGuide-apiAnalyticsDataDiscrepancies.md
nextSectionTitle: "Understanding data discrepancies"
excerpt: "The rate limit used by..."
keywords: ["analytics", "rate", "limits", "/era/v1/metrics/{timeRange}", "{timeRange", "/era/v1/metrics/{reportRequestGuid}", "/era/v1/check/{timeRange}", "{timeRange}", "/era/v1/check/{reportRequestGuid}", "/era/v1/labor/{timeRange}"]
procedures: 0
codeExamples: 0
---

The rate limit used by an endpoint depends on the endpoint and its time range. The following table lists the endpoints of the analytics API, organized by endpoint, method type, and rate limit. Notes are included when applicable.



> **Note**
> 
> As a Toast API, the analytics API adheres to the global rate limits. For more information, see [Rate limiting](apiDevGuide-apiRateLimiting).



<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Method and endpoint</div></th>
      <th className=""><div className="">Rate limits</div></th>
      <th className=""><div className="">Notes</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code><code className="font-mono text-sm">/era/v1/metrics</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">10 requests per hour</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This endpoint uses a custom time range.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code><code className="font-mono text-sm">/era/v1/metrics/&#123;timeRange&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If <code className="font-mono text-sm">&#123;timeRange</code>&#125; is:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">month</code> or <code className="font-mono text-sm">year</code>: 10 requests per hour</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">day</code> or <code className="font-mono text-sm">week</code>: 10 requests per minute, 60 requests per hour</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code><code className="font-mono text-sm">/era/v1/metrics/&#123;reportRequestGuid&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5 requests per second</p> <p className="text-base leading-relaxed">30 requests per minute</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code><code className="font-mono text-sm">/era/v1/check/&#123;timeRange&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5 requests per minute</p> <p className="text-base leading-relaxed">60 requests per day</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This endpoint uses <code className="font-mono text-sm">day</code> as the <code className="font-mono text-sm">&#123;timeRange&#125;</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code><code className="font-mono text-sm">/era/v1/check/&#123;reportRequestGuid&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5 requests per second</p> <p className="text-base leading-relaxed">30 requests per minute</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code><code className="font-mono text-sm">/era/v1/labor/&#123;timeRange&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If <code className="font-mono text-sm">&#123;timeRange</code>&#125; is:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">month</code>: 10 requests per hour</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">day</code> or <code className="font-mono text-sm">week</code>: 10 requests per minute, 60 requests per hour</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code><code className="font-mono text-sm">/era/v1/labor/&#123;reportRequestGuid&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5 requests per second</p> <p className="text-base leading-relaxed">30 requests per minute</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code><code className="font-mono text-sm">/era/v1/menu</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">10 requests per hour</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This endpoint uses a custom time range.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code><code className="font-mono text-sm">/era/v1/menu/&#123;timeRange&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If <code className="font-mono text-sm">&#123;timeRange</code>&#125; is:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">month</code> or <code className="font-mono text-sm">year</code>: 10 requests per hour</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">day</code> or <code className="font-mono text-sm">week</code>: 10 requests per minute, 60 requests per hour</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code><code className="font-mono text-sm">/era/v1/menu/&#123;reportRequestGuid&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5 requests per second</p> <p className="text-base leading-relaxed">30 requests per minute</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code><code className="font-mono text-sm">/era/v1/payout/&#123;timeRange&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If <code className="font-mono text-sm">&#123;timeRange</code>&#125; is:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">month</code>: 10 requests per hour</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">day</code> or <code className="font-mono text-sm">week</code>: 10 requests per minute and 60 requests per hour</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code><code className="font-mono text-sm">/era/v1/payout/&#123;reportRequestGuid&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5 requests per second</p> <p className="text-base leading-relaxed">30 requests per minute</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code><code className="font-mono text-sm">/era/v1/payout/payments/&#123;timeRange&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5 requests per minute</p> <p className="text-base leading-relaxed">60 requests per day</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This endpoint uses <code className="font-mono text-sm">day</code> as the <code className="font-mono text-sm">&#123;timeRange&#125;</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code><code className="font-mono text-sm">/era/v1/payout/payments/&#123;reportRequestGuid&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5 requests per second</p> <p className="text-base leading-relaxed">30 requests per minute</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code><code className="font-mono text-sm">/era/v1/payout/sales-date/&#123;timeRange&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If <code className="font-mono text-sm">&#123;timeRange</code>&#125; is:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">month</code>: 10 requests per hour</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">day</code> or <code className="font-mono text-sm">week</code>: 10 requests per minute and 60 requests per hour</p></li></ul></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code><code className="font-mono text-sm">/era/v1/payout/sales-date/&#123;reportRequestGuid&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5 requests per second</p> <p className="text-base leading-relaxed">30 requests per minute</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">POST</code><code className="font-mono text-sm">/era/v1/guest/payments/&#123;timeRange&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5 requests per second</p> <p className="text-base leading-relaxed">60 requests per minute</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">This endpoint uses <code className="font-mono text-sm">day</code> or <code className="font-mono text-sm">week</code> as the <code className="font-mono text-sm">&#123;timeRange&#125;</code>.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code><code className="font-mono text-sm">/era/v1/guest/payments/&#123;reportRequestGuid&#125;</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5 requests per second</p> <p className="text-base leading-relaxed">30 requests per minute</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"> </div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">GET</code><code className="font-mono text-sm">/era/v1/restaurant-info</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">5 requests per second</p> <p className="text-base leading-relaxed">30 requests per minute</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"></p></div></td>
    </tr>
  </tbody>
</table>
</div>

