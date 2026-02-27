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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Message</th>
      <th className="">Resolution</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><code className="">Address 1</code> for delivery address cannot be empty </td>
      <td className="">The <code className="">Address 1</code> field in your request is empty. Input the customer's address in the <code className="">deliveryInfo.address1</code> field.</td>
    </tr>
    <tr className="">
      <td className="">Customer first name cannot be empty </td>
      <td className="">Add a value the <code className="">customer.firstName</code> field.</td>
    </tr>
    <tr className="">
      <td className="">Customer phone cannot be empty </td>
      <td className="">Add a value to the <code className="">customer.phone</code> field. </td>
    </tr>
    <tr className="">
      <td className="">EITHER (<code className="">startDate</code> and <code className="">endDate)</code> OR <code className="">businessDate</code> is required</td>
      <td className="">Input both a start date and end date or a business date to your request. </td>
    </tr>
    <tr className="">
      <td className="">Input <code className="">startDate</code> must be before <code className="">endDate</code></td>
      <td className="">Check the <code className="">startDate</code> and <code className="">endDate</code> values throughout your request and ensure that the <code className="">startDate</code> time stamps occur before the <code className="">endDate</code> time stamps.</td>
    </tr>
    <tr className="">
      <td className="">Item (<em className=""><code className="">&#123;item GUID&#125;</code></em> ) does not belong to the group (<em className=""><code className="">&#123;item group GUID&#125;</code></em> )</td>
      <td className=""> A menu item in your request does not belong to the referenced menu group. Update the menu item's <code className="">menuGroups</code>. You can find <code className="">menuItems</code> and <code className="">menuGroups</code> values by submitting a <code className="">GET</code> request to the <code className="">/menus/v2/menus</code> endpoint.</td>
    </tr>
    <tr className="">
      <td className="">Referenced entity (<code className="">type=Discount</code>) must contain a GUID</td>
      <td className="">The discount in your request requires a GUID. You can find discount GUIDs by sending a <code className="">GET</code> request to the <code className="">/config/v2/discounts</code> endpoint.</td>
    </tr>
    <tr className="">
      <td className="">Referenced entity (<code className="">type=MenuItem</code>) must contain either a GUID or <code className="">MultiLocationId</code></td>
      <td className="">Your request contains a menu item entry that is missing a GUID or a <code className="">multilocationId</code>. You can find The GUID and <code className="">multilocationId</code> values by submitting a <code className="">GET</code> request from the appropriate menu endpoint. For more information see <a href="apiDevGuide-apiComparingMenusAPIV2AndV3" className="">devGuide</a></td>
    </tr>
    <tr className="">
      <td className=""> Restaurant(&#123;<em className=""><code className="">restaurant GUID</code></em> &#125;) has been deleted</td>
      <td className="">The restaurant GUID that you are using in your order request refers to a restaurant that's been deleted. Stop all API requests to this restaurant. </td>
    </tr>
  </tbody>
</table>
</div>

