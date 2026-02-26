---
title: "Orders API errors"
id: apiOrdersErrors
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiOrdersOvercviewOmitChunkFromSearchIndex.md
parentSectionTitle: "About the orders API"
previousSectionFile: apiDevGuide-apiOrdersFirstOrder.md
previousSectionTitle: "Submitting your first order to the orders API"
nextSectionFile: apiDevGuide-portalApiGettingOrdersOmitChunkFromSearchIndex.md
nextSectionTitle: "Getting order information"
excerpt: "The entries in the table below define errors you may encounter while using the orders API. These entries are ordered alphabetically by error message."
keywords: ["Address 1", "deliveryInfo.address1", "customer.firstName", "startDate", "endDate)", "businessDate", "endDate", "menuGroups", "menuItems", "type=Discount"]
procedures: 0
codeExamples: 0
---

The entries in the table below define errors you may encounter while using the orders API. These entries are ordered alphabetically by error message.


<table>
  <thead>
    <tr>
      <th>Message</th>
      <th>Resolution</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>Address 1</code> for delivery address cannot be empty </td>
      <td>The <code>Address 1</code> field in your request is empty. Input the customer's address in the <code>deliveryInfo.address1</code> field.</td>
    </tr>
    <tr>
      <td>Customer first name cannot be empty </td>
      <td>Add a value the <code>customer.firstName</code> field.</td>
    </tr>
    <tr>
      <td>Customer phone cannot be empty </td>
      <td>Add a value to the <code>customer.phone</code> field. </td>
    </tr>
    <tr>
      <td>EITHER (<code>startDate</code> and <code>endDate)</code> OR <code>businessDate</code> is required</td>
      <td>Input both a start date and end date or a business date to your request. </td>
    </tr>
    <tr>
      <td>Input <code>startDate</code> must be before <code>endDate</code></td>
      <td>Check the <code>startDate</code> and <code>endDate</code> values throughout your request and ensure that the <code>startDate</code> time stamps occur before the <code>endDate</code> time stamps.</td>
    </tr>
    <tr>
      <td>Item (<em><code>&#123;item GUID&#125;</code></em> ) does not belong to the group (<em><code>&#123;item group GUID&#125;</code></em> )</td>
      <td> A menu item in your request does not belong to the referenced menu group. Update the menu item's <code>menuGroups</code>. You can find <code>menuItems</code> and <code>menuGroups</code> values by submitting a <code>GET</code> request to the <code>/menus/v2/menus</code> endpoint.</td>
    </tr>
    <tr>
      <td>Referenced entity (<code>type=Discount</code>) must contain a GUID</td>
      <td>The discount in your request requires a GUID. You can find discount GUIDs by sending a <code>GET</code> request to the <code>/config/v2/discounts</code> endpoint.</td>
    </tr>
    <tr>
      <td>Referenced entity (<code>type=MenuItem</code>) must contain either a GUID or <code>MultiLocationId</code></td>
      <td>Your request contains a menu item entry that is missing a GUID or a <code>multilocationId</code>. You can find The GUID and <code>multilocationId</code> values by submitting a <code>GET</code> request from the appropriate menu endpoint. For more information see <a href="apiDevGuide-apiComparingMenusAPIV2AndV3">devGuide</a></td>
    </tr>
    <tr>
      <td> Restaurant(&#123;<em><code>restaurant GUID</code></em> &#125;) has been deleted</td>
      <td>The restaurant GUID that you are using in your order request refers to a restaurant that's been deleted. Stop all API requests to this restaurant. </td>
    </tr>
  </tbody>
</table>

