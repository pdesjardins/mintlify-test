---
title: "Standard API access scopes"
id: devApiAccessScopes
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-ifYoureAStandardApiAccessDeveloperOmitChunkFromSearchIndex.md
parentSectionTitle: "If you're a standard API access developer"
previousSectionFile: apiDevGuide-devApiAccessRequirements.md
previousSectionTitle: "Standard API access requirements"
nextSectionFile: apiDevGuide-devApiAccessResources.md
nextSectionTitle: "Standard API access resources"
excerpt: "Scopes determine the actions that your Toast API client has permission to perform, which is authenticated using the client ID and secret created in Toast Web. For more information, see ."
keywords: ["delivery_info.address:read", "DeliveryInfo", "digital_schedule:read", "Customer"]
procedures: 0
codeExamples: 0
---

Scopes determine the actions that your Toast API client has permission to perform, which is authenticated using the client ID and secret created in Toast Web. For more information, see [Scopes](apiDevGuide-apiScopes).

Standard API access provides access to the following scopes:


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Scope</th>
      <th className="">Toast API</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><code className="">cashmgmt:read</code></td>
      <td className="">cash management API</td>
    </tr>
    <tr className="">
      <td className=""><code className="">config:read</code></td>
      <td className="">configuration API</td>
    </tr>
    <tr className="">
      <td className=""><code className="">delivery_info.address:read</code> <blockquote><strong>Note</strong> This scope exposes additional information in the <code className="">DeliveryInfo</code> object of the orders API.</blockquote> </td>
      <td className="">orders API</td>
    </tr>
    <tr className="">
      <td className=""><code className="">digital_schedule:read</code></td>
      <td className="">order management configuration API</td>
    </tr>
    <tr className="">
      <td className=""><code className="">guest.pi:read</code> <blockquote><strong>Note</strong> This scope to exposes additional information in the <code className="">Customer</code> object of the orders API.</blockquote> </td>
      <td className="">orders API</td>
    </tr>
    <tr className="">
      <td className=""><code className="">kitchen:read</code></td>
      <td className="">kitchen API</td>
    </tr>
    <tr className="">
      <td className=""><code className="">labor.employees:read</code></td>
      <td className="">labor API</td>
    </tr>
    <tr className="">
      <td className=""><code className="">labor:read</code></td>
      <td className="">labor API</td>
    </tr>
    <tr className="">
      <td className=""><code className="">menus:read</code></td>
      <td className="">menus v2 API</td>
    </tr>
    <tr className="">
      <td className=""><code className="">orders:read</code></td>
      <td className="">orders API</td>
    </tr>
    <tr className="">
      <td className=""><code className="">packaging:read</code></td>
      <td className="">packaging configuration API</td>
    </tr>
    <tr className="">
      <td className=""><code className="">restaurants:read</code></td>
      <td className="">restaurant availability API, restaurants API</td>
    </tr>
    <tr className="">
      <td className=""><code className="">stock:read</code></td>
      <td className="">stock API</td>
    </tr>
  </tbody>
</table>
</div>

