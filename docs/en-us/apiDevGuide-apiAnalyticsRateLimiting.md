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



<table>
  <thead>
    <tr>
      <th>Method and endpoint</th>
      <th>Rate limits</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>POST</code><code>/era/v1/metrics</code></td>
      <td>10 requests per hour</td>
      <td>This endpoint uses a custom time range.</td>
    </tr>
    <tr>
      <td><code>POST</code><code>/era/v1/metrics/&#123;timeRange&#125;</code></td>
      <td>If <code>&#123;timeRange</code>&#125; is:
<ul>
<li><code>month</code> or <code>year</code>: 10 requests per hour</li>
<li><code>day</code> or <code>week</code>: 10 requests per minute, 60 requests per hour</li>
</ul>
</td>
      <td></td>
    </tr>
    <tr>
      <td><code>GET</code><code>/era/v1/metrics/&#123;reportRequestGuid&#125;</code></td>
      <td>5 requests per second <br/> 30 requests per minute</td>
      <td> </td>
    </tr>
    <tr>
      <td><code>POST</code><code>/era/v1/check/&#123;timeRange&#125;</code></td>
      <td>5 requests per minute <br/> 60 requests per day</td>
      <td>This endpoint uses <code>day</code> as the <code>&#123;timeRange&#125;</code>.</td>
    </tr>
    <tr>
      <td><code>GET</code><code>/era/v1/check/&#123;reportRequestGuid&#125;</code></td>
      <td>5 requests per second <br/> 30 requests per minute</td>
      <td></td>
    </tr>
    <tr>
      <td><code>POST</code><code>/era/v1/labor/&#123;timeRange&#125;</code></td>
      <td>If <code>&#123;timeRange</code>&#125; is:
<ul>
<li><code>month</code>: 10 requests per hour</li>
<li><code>day</code> or <code>week</code>: 10 requests per minute, 60 requests per hour</li>
</ul>
</td>
      <td></td>
    </tr>
    <tr>
      <td><code>GET</code><code>/era/v1/labor/&#123;reportRequestGuid&#125;</code></td>
      <td>5 requests per second <br/> 30 requests per minute</td>
      <td></td>
    </tr>
    <tr>
      <td><code>POST</code><code>/era/v1/menu</code></td>
      <td>10 requests per hour</td>
      <td>This endpoint uses a custom time range.</td>
    </tr>
    <tr>
      <td><code>POST</code><code>/era/v1/menu/&#123;timeRange&#125;</code></td>
      <td>If <code>&#123;timeRange</code>&#125; is:
<ul>
<li><code>month</code> or <code>year</code>: 10 requests per hour</li>
<li><code>day</code> or <code>week</code>: 10 requests per minute, 60 requests per hour</li>
</ul>
</td>
      <td></td>
    </tr>
    <tr>
      <td><code>GET</code><code>/era/v1/menu/&#123;reportRequestGuid&#125;</code></td>
      <td>5 requests per second <br/> 30 requests per minute</td>
      <td></td>
    </tr>
    <tr>
      <td><code>POST</code><code>/era/v1/payout/&#123;timeRange&#125;</code></td>
      <td>If <code>&#123;timeRange</code>&#125; is:
<ul>
<li><code>month</code>: 10 requests per hour</li>
<li><code>day</code> or <code>week</code>: 10 requests per minute and 60 requests per hour</li>
</ul>
</td>
      <td></td>
    </tr>
    <tr>
      <td><code>GET</code><code>/era/v1/payout/&#123;reportRequestGuid&#125;</code></td>
      <td>5 requests per second <br/> 30 requests per minute</td>
      <td></td>
    </tr>
    <tr>
      <td><code>POST</code><code>/era/v1/payout/payments/&#123;timeRange&#125;</code></td>
      <td>5 requests per minute <br/> 60 requests per day</td>
      <td>This endpoint uses <code>day</code> as the <code>&#123;timeRange&#125;</code>.</td>
    </tr>
    <tr>
      <td><code>GET</code><code>/era/v1/payout/payments/&#123;reportRequestGuid&#125;</code></td>
      <td>5 requests per second <br/> 30 requests per minute</td>
      <td></td>
    </tr>
    <tr>
      <td><code>POST</code><code>/era/v1/payout/sales-date/&#123;timeRange&#125;</code></td>
      <td>If <code>&#123;timeRange</code>&#125; is:
<ul>
<li><code>month</code>: 10 requests per hour</li>
<li><code>day</code> or <code>week</code>: 10 requests per minute and 60 requests per hour</li>
</ul>
</td>
      <td></td>
    </tr>
    <tr>
      <td><code>GET</code><code>/era/v1/payout/sales-date/&#123;reportRequestGuid&#125;</code></td>
      <td>5 requests per second <br/> 30 requests per minute</td>
      <td></td>
    </tr>
    <tr>
      <td><code>POST</code><code>/era/v1/guest/payments/&#123;timeRange&#125;</code></td>
      <td>5 requests per second <br/> 60 requests per minute</td>
      <td>This endpoint uses <code>day</code> or <code>week</code> as the <code>&#123;timeRange&#125;</code>.</td>
    </tr>
    <tr>
      <td><code>GET</code><code>/era/v1/guest/payments/&#123;reportRequestGuid&#125;</code></td>
      <td>5 requests per second <br/> 30 requests per minute</td>
      <td> </td>
    </tr>
    <tr>
      <td><code>GET</code><code>/era/v1/restaurant-info</code></td>
      <td>5 requests per second <br/> 30 requests per minute</td>
      <td></td>
    </tr>
  </tbody>
</table>

