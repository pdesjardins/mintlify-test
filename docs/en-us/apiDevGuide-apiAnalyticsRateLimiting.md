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
      <td className=""><div className=""><code className="">POST</code><code className="">/era/v1/metrics</code></div></td>
      <td className=""><div className="">10 requests per hour</div></td>
      <td className=""><div className="">This endpoint uses a custom time range.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">POST</code><code className="">/era/v1/metrics/&#123;timeRange&#125;</code></div></td>
      <td className=""><div className="">If <code className="">&#123;timeRange</code>&#125; is:<ul className=""><li className=""><code className="">month</code> or <code className="">year</code>: 10 requests per hour</li><li className=""><code className="">day</code> or <code className="">week</code>: 10 requests per minute, 60 requests per hour</li></ul></div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">GET</code><code className="">/era/v1/metrics/&#123;reportRequestGuid&#125;</code></div></td>
      <td className=""><div className="">5 requests per second <br/> 30 requests per minute</div></td>
      <td className=""><div className=""> </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">POST</code><code className="">/era/v1/check/&#123;timeRange&#125;</code></div></td>
      <td className=""><div className="">5 requests per minute <br/> 60 requests per day</div></td>
      <td className=""><div className="">This endpoint uses <code className="">day</code> as the <code className="">&#123;timeRange&#125;</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">GET</code><code className="">/era/v1/check/&#123;reportRequestGuid&#125;</code></div></td>
      <td className=""><div className="">5 requests per second <br/> 30 requests per minute</div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">POST</code><code className="">/era/v1/labor/&#123;timeRange&#125;</code></div></td>
      <td className=""><div className="">If <code className="">&#123;timeRange</code>&#125; is:<ul className=""><li className=""><code className="">month</code>: 10 requests per hour</li><li className=""><code className="">day</code> or <code className="">week</code>: 10 requests per minute, 60 requests per hour</li></ul></div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">GET</code><code className="">/era/v1/labor/&#123;reportRequestGuid&#125;</code></div></td>
      <td className=""><div className="">5 requests per second <br/> 30 requests per minute</div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">POST</code><code className="">/era/v1/menu</code></div></td>
      <td className=""><div className="">10 requests per hour</div></td>
      <td className=""><div className="">This endpoint uses a custom time range.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">POST</code><code className="">/era/v1/menu/&#123;timeRange&#125;</code></div></td>
      <td className=""><div className="">If <code className="">&#123;timeRange</code>&#125; is:<ul className=""><li className=""><code className="">month</code> or <code className="">year</code>: 10 requests per hour</li><li className=""><code className="">day</code> or <code className="">week</code>: 10 requests per minute, 60 requests per hour</li></ul></div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">GET</code><code className="">/era/v1/menu/&#123;reportRequestGuid&#125;</code></div></td>
      <td className=""><div className="">5 requests per second <br/> 30 requests per minute</div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">POST</code><code className="">/era/v1/payout/&#123;timeRange&#125;</code></div></td>
      <td className=""><div className="">If <code className="">&#123;timeRange</code>&#125; is:<ul className=""><li className=""><code className="">month</code>: 10 requests per hour</li><li className=""><code className="">day</code> or <code className="">week</code>: 10 requests per minute and 60 requests per hour</li></ul></div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">GET</code><code className="">/era/v1/payout/&#123;reportRequestGuid&#125;</code></div></td>
      <td className=""><div className="">5 requests per second <br/> 30 requests per minute</div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">POST</code><code className="">/era/v1/payout/payments/&#123;timeRange&#125;</code></div></td>
      <td className=""><div className="">5 requests per minute <br/> 60 requests per day</div></td>
      <td className=""><div className="">This endpoint uses <code className="">day</code> as the <code className="">&#123;timeRange&#125;</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">GET</code><code className="">/era/v1/payout/payments/&#123;reportRequestGuid&#125;</code></div></td>
      <td className=""><div className="">5 requests per second <br/> 30 requests per minute</div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">POST</code><code className="">/era/v1/payout/sales-date/&#123;timeRange&#125;</code></div></td>
      <td className=""><div className="">If <code className="">&#123;timeRange</code>&#125; is:<ul className=""><li className=""><code className="">month</code>: 10 requests per hour</li><li className=""><code className="">day</code> or <code className="">week</code>: 10 requests per minute and 60 requests per hour</li></ul></div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">GET</code><code className="">/era/v1/payout/sales-date/&#123;reportRequestGuid&#125;</code></div></td>
      <td className=""><div className="">5 requests per second <br/> 30 requests per minute</div></td>
      <td className=""><div className=""></div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">POST</code><code className="">/era/v1/guest/payments/&#123;timeRange&#125;</code></div></td>
      <td className=""><div className="">5 requests per second <br/> 60 requests per minute</div></td>
      <td className=""><div className="">This endpoint uses <code className="">day</code> or <code className="">week</code> as the <code className="">&#123;timeRange&#125;</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">GET</code><code className="">/era/v1/guest/payments/&#123;reportRequestGuid&#125;</code></div></td>
      <td className=""><div className="">5 requests per second <br/> 30 requests per minute</div></td>
      <td className=""><div className=""> </div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">GET</code><code className="">/era/v1/restaurant-info</code></div></td>
      <td className=""><div className="">5 requests per second <br/> 30 requests per minute</div></td>
      <td className=""><div className=""></div></td>
    </tr>
  </tbody>
</table>
</div>

