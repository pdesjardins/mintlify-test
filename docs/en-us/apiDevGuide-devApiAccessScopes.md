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


<table>
  <thead>
    <tr>
      <th>Scope</th>
      <th>Toast API</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>`cashmgmt:read`</td>
      <td>cash management API</td>
    </tr>
    <tr>
      <td>`config:read`</td>
      <td>configuration API</td>
    </tr>
    <tr>
      <td>`delivery_info.address:read` <blockquote><strong>Note</strong> This scope exposes additional information in the `DeliveryInfo` object of the orders API.</blockquote> </td>
      <td>orders API</td>
    </tr>
    <tr>
      <td>`digital_schedule:read`</td>
      <td>order management configuration API</td>
    </tr>
    <tr>
      <td>`guest.pi:read` <blockquote><strong>Note</strong> This scope to exposes additional information in the `Customer` object of the orders API.</blockquote> </td>
      <td>orders API</td>
    </tr>
    <tr>
      <td>`kitchen:read`</td>
      <td>kitchen API</td>
    </tr>
    <tr>
      <td>`labor.employees:read`</td>
      <td>labor API</td>
    </tr>
    <tr>
      <td>`labor:read`</td>
      <td>labor API</td>
    </tr>
    <tr>
      <td>`menus:read`</td>
      <td>menus v2 API</td>
    </tr>
    <tr>
      <td>`orders:read`</td>
      <td>orders API</td>
    </tr>
    <tr>
      <td>`packaging:read`</td>
      <td>packaging configuration API</td>
    </tr>
    <tr>
      <td>`restaurants:read`</td>
      <td>restaurant availability API, restaurants API</td>
    </tr>
    <tr>
      <td>`stock:read`</td>
      <td>stock API</td>
    </tr>
  </tbody>
</table>

