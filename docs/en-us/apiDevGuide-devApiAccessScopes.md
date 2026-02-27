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
<table>
  <thead>
    <tr>
      <th>Scope</th>
      <th>Toast API</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>cashmgmt:read</code></td>
      <td>cash management API</td>
    </tr>
    <tr>
      <td><code>config:read</code></td>
      <td>configuration API</td>
    </tr>
    <tr>
      <td><code>delivery_info.address:read</code> <blockquote><strong>Note</strong> This scope exposes additional information in the <code>DeliveryInfo</code> object of the orders API.</blockquote> </td>
      <td>orders API</td>
    </tr>
    <tr>
      <td><code>digital_schedule:read</code></td>
      <td>order management configuration API</td>
    </tr>
    <tr>
      <td><code>guest.pi:read</code> <blockquote><strong>Note</strong> This scope to exposes additional information in the <code>Customer</code> object of the orders API.</blockquote> </td>
      <td>orders API</td>
    </tr>
    <tr>
      <td><code>kitchen:read</code></td>
      <td>kitchen API</td>
    </tr>
    <tr>
      <td><code>labor.employees:read</code></td>
      <td>labor API</td>
    </tr>
    <tr>
      <td><code>labor:read</code></td>
      <td>labor API</td>
    </tr>
    <tr>
      <td><code>menus:read</code></td>
      <td>menus v2 API</td>
    </tr>
    <tr>
      <td><code>orders:read</code></td>
      <td>orders API</td>
    </tr>
    <tr>
      <td><code>packaging:read</code></td>
      <td>packaging configuration API</td>
    </tr>
    <tr>
      <td><code>restaurants:read</code></td>
      <td>restaurant availability API, restaurants API</td>
    </tr>
    <tr>
      <td><code>stock:read</code></td>
      <td>stock API</td>
    </tr>
  </tbody>
</table>
</div>

