---
title: "Standard API access FAQs"
id: devApiAccessFAQs
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-ifYoureAStandardApiAccessDeveloperOmitChunkFromSearchIndex.md
parentSectionTitle: "If you're a standard API access developer"
previousSectionFile: apiDevGuide-devApiAccessWebhookSubscriptions.md
previousSectionTitle: "Standard API access webhook subscriptions"
nextSectionFile: apiDevGuide-devApiAccessSupportStandardApiAccess.md
nextSectionTitle: "Standard API access support"
excerpt: "Why is the &quot;Manage Credentials&quot; interface not visible? You must have the &quot;Manage Integrations&quot; permission to view the &quot;Manage Credentials&quot; interface."
keywords: ["POST", "GET"]
procedures: 0
codeExamples: 0
---


<div className="table-wrapper">
<table>
  <tbody>
    <tr>
      <td><strong>Q:</strong> </td>
      <td>Why is the "Manage Credentials" interface not visible?</td>
    </tr>
    <tr>
      <td><strong>A:</strong> </td>
      <td>You must have the "Manage Integrations" permission to view the "Manage Credentials" interface.</td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table>
  <tbody>
    <tr>
      <td><strong>Q:</strong> </td>
      <td>How do I add new locations to my existing credentials?</td>
    </tr>
    <tr>
      <td><strong>A:</strong> </td>
      <td>You can add new locations on the Edit credentials page. For information on how to edit which location(s) you have standard API access to, see <a href="apiDevGuide-devApiAccessCredentials#devApiAccessEditingCredentials">Editing standard API access credentials</a>.</td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table>
  <tbody>
    <tr>
      <td><strong>Q:</strong> </td>
      <td>Why is there a lock next to a Toast POS location that is not available (appears dimmed)?</td>
    </tr>
    <tr>
      <td><strong>A:</strong> </td>
      <td>If a location displays a lock and is displayed as not available (appears dimmed), that indicates that the location does not have access to Toast Restaurant Management Suite Essentials or higher. Every location you want to have standard API access to requires a subscription to Toast Restaurant Management Suite Essentials or higher. <br/> Changes made to locations with an active subscription to Toast Restaurant Management Suite Essentials or higher may take a few minutes to be reflected in the Toast platform.</td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table>
  <tbody>
    <tr>
      <td><strong>Q:</strong> </td>
      <td>Why am I seeing a 401 error when making an API request?</td>
    </tr>
    <tr>
      <td><strong>A:</strong> </td>
      <td>You may see a 401 error because you did not authenticate with valid credentials. For more information on authentication, see <a href="apiDevGuide-authentication">Authentication and restaurant access</a>. For more information about error codes, see <a href="apiDevGuide-apiResponsesAndErrors">API responses and errors</a>.</td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table>
  <tbody>
    <tr>
      <td><strong>Q:</strong> </td>
      <td>Why am I seeing a 403 error when making an API request?</td>
    </tr>
    <tr>
      <td><strong>A:</strong> </td>
      <td>You may see a 403 error message when making an API request for any of the following reasons:<ul><li>You made a <code>POST</code> request. Standard API access only supports <code>GET</code> requests.</li><li>You tried to access the <code>menus /v3</code> endpoints. Standard API access only supports <code>menus /v2</code> endpoints.</li><li>Your credentials do not include access to this restaurant. For information on how to edit which location(s) you have standard API access to, see <a href="apiDevGuide-devApiAccessCredentials#devApiAccessEditingCredentials">Editing standard API access credentials</a>.</li><li>Your API client is missing the required scope for this endpoint. For information on how to edit the scopes configured for a client, see <a href="apiDevGuide-devApiAccessCredentials#devApiAccessEditingCredentials">Editing standard API access credentials</a>.</li></ul> <blockquote><strong>Note</strong> This list is not exhaustive. For more information about error codes, see <a href="apiDevGuide-apiResponsesAndErrors">API responses and errors</a>.</blockquote> </td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table>
  <tbody>
    <tr>
      <td><strong>Q:</strong> </td>
      <td>Why don't I have access to create standard API access credentials?</td>
    </tr>
    <tr>
      <td><strong>A:</strong> </td>
      <td>Confirm that you have the Manage Integrations permission for the location(s) you want to create credentials for. If you do not have permission, contact your restaurant or store team to have the permission assigned.</td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table>
  <tbody>
    <tr>
      <td><strong>Q:</strong> </td>
      <td>Why can’t I see guest data in the JSON for an in-store order?</td>
    </tr>
    <tr>
      <td><strong>A:</strong> </td>
      <td>Guest data is only provided for orders that have a dining behavior of either Takeout or Delivery. Guest data is not provided for in-store orders.</td>
    </tr>
  </tbody>
</table>
</div>

