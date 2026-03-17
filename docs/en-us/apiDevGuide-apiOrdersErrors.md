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
      <th className=""><div className=""><p className="text-base leading-relaxed">Message</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Resolution</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><code className="font-mono text-sm">Address 1</code> for delivery address cannot be empty </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">Address 1</code> field in your request is empty. Input the customer's address in the <code className="font-mono text-sm">deliveryInfo.address1</code> field.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Customer first name cannot be empty </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Add a value the <code className="font-mono text-sm">customer.firstName</code> field.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Customer phone cannot be empty </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Add a value to the <code className="font-mono text-sm">customer.phone</code> field. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">EITHER (<code className="font-mono text-sm">startDate</code> and <code className="font-mono text-sm">endDate)</code> OR <code className="font-mono text-sm">businessDate</code> is required</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Input both a start date and end date or a business date to your request. </p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Input <code className="font-mono text-sm">startDate</code> must be before <code className="font-mono text-sm">endDate</code> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Check the <code className="font-mono text-sm">startDate</code> and <code className="font-mono text-sm">endDate</code> values throughout your request and ensure that the <code className="font-mono text-sm">startDate</code> time stamps occur before the <code className="font-mono text-sm">endDate</code> time stamps.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Item (<em className=""><code className="font-mono text-sm">&#123;item GUID&#125;</code></em> ) does not belong to the group (<em className=""><code className="font-mono text-sm">&#123;item group GUID&#125;</code></em> )</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"> A menu item in your request does not belong to the referenced menu group. Update the menu item's <code className="font-mono text-sm">menuGroups</code>. You can find <code className="font-mono text-sm">menuItems</code> and <code className="font-mono text-sm">menuGroups</code> values by submitting a <code className="font-mono text-sm">GET</code> request to the <code className="font-mono text-sm">/menus/v2/menus</code> endpoint.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Referenced entity (<code className="font-mono text-sm">type=Discount</code>) must contain a GUID</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The discount in your request requires a GUID. You can find discount GUIDs by sending a <code className="font-mono text-sm">GET</code> request to the <code className="font-mono text-sm">/config/v2/discounts</code> endpoint.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Referenced entity (<code className="font-mono text-sm">type=MenuItem</code>) must contain either a GUID or <code className="font-mono text-sm">MultiLocationId</code></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Your request contains a menu item entry that is missing a GUID or a <code className="font-mono text-sm">multilocationId</code>. You can find The GUID and <code className="font-mono text-sm">multilocationId</code> values by submitting a <code className="font-mono text-sm">GET</code> request from the appropriate menu endpoint. For more information see <a href="apiDevGuide-apiComparingMenusAPIV2AndV3" className="">devGuide</a></p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"> Restaurant(&#123;<em className=""><code className="font-mono text-sm">restaurant GUID</code></em> &#125;) has been deleted</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The restaurant GUID that you are using in your order request refers to a restaurant that's been deleted. Stop all API requests to this restaurant. </p></div></td>
    </tr>
  </tbody>
</table>
</div>

