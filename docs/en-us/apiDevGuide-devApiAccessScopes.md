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
      <th className=""><div className="">Scope</div></th>
      <th className=""><div className="">Toast API</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className=""><code className="">cashmgmt:read</code></div></td>
      <td className=""><div className="">cash management API</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">config:read</code></div></td>
      <td className=""><div className="">configuration API</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">delivery_info.address:read</code> <blockquote><strong>Note</strong> This scope exposes additional information in the <code className="">DeliveryInfo</code> object of the orders API.</blockquote> </div></td>
      <td className=""><div className="">orders API</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">digital_schedule:read</code></div></td>
      <td className=""><div className="">order management configuration API</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">guest.pi:read</code> <blockquote><strong>Note</strong> This scope to exposes additional information in the <code className="">Customer</code> object of the orders API.</blockquote> </div></td>
      <td className=""><div className="">orders API</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">kitchen:read</code></div></td>
      <td className=""><div className="">kitchen API</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">labor.employees:read</code></div></td>
      <td className=""><div className="">labor API</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">labor:read</code></div></td>
      <td className=""><div className="">labor API</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">menus:read</code></div></td>
      <td className=""><div className="">menus v2 API</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">orders:read</code></div></td>
      <td className=""><div className="">orders API</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">packaging:read</code></div></td>
      <td className=""><div className="">packaging configuration API</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">restaurants:read</code></div></td>
      <td className=""><div className="">restaurant availability API, restaurants API</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><code className="">stock:read</code></div></td>
      <td className=""><div className="">stock API</div></td>
    </tr>
  </tbody>
</table>
</div>

