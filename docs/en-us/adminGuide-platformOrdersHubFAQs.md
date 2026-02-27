---
title: "FAQs"
id: platformOrdersHubFAQs
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformOrdersHubOmitChunkFromSearchIndex.md
parentSectionTitle: "Orders Hub"
previousSectionFile: adminGuide-platformManagingDeliveryOrders.md
previousSectionTitle: "Managing first-party delivery orders"
nextSectionFile: adminGuide-adminOnlineOrderingSchedulesOmitChunkFromSearchIndex.md
nextSectionTitle: "Online ordering hours"
externalReferences: [https://central.toasttab.com/s/article/Double-Printing?utm_campaign=toast-community&utm_medium=toastweb&utm_source=web]
excerpt: "I’m offering both takeout and delivery dining options for online ordering. Why am I only seeing the quote time for one of them? The quote time for a specific dining option is displayed on the Orders..."
keywords: ["faqs", "Manager Passcode or Swipe Card Required"]
procedures: 0
codeExamples: 0
---


<div className="table-wrapper">
<table className="">
  <tbody className="">
    <tr className="">
      <td className=""><strong className="">Q:</strong> </td>
      <td className="">I’m offering both takeout and delivery dining options for online ordering. Why am I only seeing the quote time for one of them?</td>
    </tr>
    <tr className="">
      <td className=""><strong className="">A:</strong> </td>
      <td className="">The quote time for a specific dining option is displayed on the Orders Hub screen only if both of the following conditions are satisfied:<ul className=""><li className="">You have selected Delivery as a dining option in the Takeout/delivery page in Toast Web. From Toast Web, choose Takeout & delivery &gt; Takeout/delivery to open the Takeout/delivery page.</li><li className="">You have turned on the Delivery or Takeout toggle in the Toast Online Ordering section on the Takeout & delivery page.</li></ul></td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table className="">
  <tbody className="">
    <tr className="">
      <td className=""><strong className="">Q:</strong> </td>
      <td className="">Can I use the Orders Hub screen in dark mode?</td>
    </tr>
    <tr className="">
      <td className=""><strong className="">A:</strong> </td>
      <td className="">Yes, you can use the Orders Hub screen in dark mode. To enable dark mode on your device, navigate to the Setup screen. Tap on Device Setup &gt; POS Display Theme. Select Dark mode and then tap the Save button.</td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table className="">
  <tbody className="">
    <tr className="">
      <td className=""><strong className="">Q:</strong> </td>
      <td className="">Can I manually fire a Scheduled order from the Orders Hub screen?</td>
    </tr>
    <tr className="">
      <td className=""><strong className="">A:</strong> </td>
      <td className="">On an Autofire configured device, you can manually fire a Scheduled order from the Orders Hub screen by selecting the Fire Now button on the detailed order information screen.</td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table className="">
  <tbody className="">
    <tr className="">
      <td className=""><strong className="">Q:</strong> </td>
      <td className="">Can multiple devices use and access Orders Hub?</td>
    </tr>
    <tr className="">
      <td className=""><strong className="">A:</strong> </td>
      <td className="">Yes, Orders Hub can be used on multiple devices.</td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table className="">
  <tbody className="">
    <tr className="">
      <td className=""><strong className="">Q:</strong> </td>
      <td className="">What are various Autofire device scenarios that I may encounter when using Orders Hub?</td>
    </tr>
    <tr className="">
      <td className=""><strong className="">A:</strong> </td>
      <td className="">Orders Hub can only be used with an Autofire device. The recommendation is to enable Autofire on only one device per restaurant; however, there are instances where none or more than one Autofire device may be used in a restaurant.<ul className=""><li className="">If a restaurant has one Autofire device and one non-Autofire device: Scheduled orders will appear on both devices, however the Fire Now button will only be available on the Autofire enabled device. When the order is ready to be prepped, the order moves to the Active tab on both devices. The kitchen/prep station printer automatically prints the ticket on the Autofire enabled device.</li><li className="">If a restaurant has two Autofire devices: Scheduled orders will appear on both devices and both devices can "Fire Now". When the order is ready to be prepped, it moves to the Active tab on both devices. The kitchen/prep station printer automatically prints on one of the devices. It is strongly recommended that only one device should be configured to Autofire as there is a <a href="https://central.toasttab.com/s/article/Double-Printing?utm_campaign=toast-community&utm_medium=toastweb&utm_source=web" className="">risk of double printing</a> as you do not have the ability to determine which device prints the ticket.</li><li className="">If a restaurant does not have an Autofire device: Scheduled orders appear on the device, however the Fire Now button is inactive. When the order is ready to be prepped, the order remains in the Scheduled tab. The order cannot be moved to the Completed tab. The kitchen/prep station printer does not automatically print the ticket. If the restaurant enables a device to Autofire, the scheduled order moves to the Active tab and the kitchen/prep station printer prints the ticket.</li></ul></td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table className="">
  <tbody className="">
    <tr className="">
      <td className=""><strong className="">Q:</strong> </td>
      <td className="">What happens to Scheduled orders if the Autofire device is inoperable?</td>
    </tr>
    <tr className="">
      <td className=""><strong className="">A:</strong> </td>
      <td className="">In the instance that the Autofire device is inoperable, Scheduled orders will stay in the Scheduled tab on the Orders Hub screen. To move orders into the Active tab and ready it for KDS fulfillment, turn on/enable your Autofire device. Once Autofire is enabled, all Scheduled orders automatically move to the Active tab, are readied for KDS fulfillment, and new delivery times are provided. If you cannot enable Autofire on your device, configure a different device to Autofire.</td>
    </tr>
    <tr className="">
      <td className=""><strong className="">Q:</strong> </td>
      <td className="">Do Order Ready messages still get sent if my Orders Hub device goes offline and then comes back online?</td>
    </tr>
    <tr className="">
      <td className=""><strong className="">A:</strong> </td>
      <td className="">Yes, Order Ready messages are sent once your Orders Hub device has come back online and is syncing orders. The Autofire device (can be the same as the Orders Hub device) must also be online and firing orders to the kitchen.</td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table className="">
  <tbody className="">
    <tr className="">
      <td className=""><strong className="">Q:</strong> </td>
      <td className="">What permission do I need to have to use the Manage Online Orders button on the Orders Hub screen?</td>
    </tr>
    <tr className="">
      <td className=""><strong className="">A:</strong> </td>
      <td className="">To use the Manage Online Orders button on the Orders Hub screen, you must have the 3.29 Throttle Online Orders permission. If you do not have the 3.29 Throttle Online Orders permission, you will encounter an error message when trying to access the Manage Online Orders button on the Orders Hub screen. The error message displays: <code className=""><em className="">Manager Passcode or Swipe Card Required</em> </code>. For more information about permissions, see <a href="adminGuide-adminPermissions#adminModePermissions" className="">POS access permissions</a>.</td>
    </tr>
  </tbody>
</table>
</div>


<div className="table-wrapper">
<table className="">
  <tbody className="">
    <tr className="">
      <td className=""><strong className="">Q:</strong> </td>
      <td className="">When do orders clear out of Orders Hub?</td>
    </tr>
    <tr className="">
      <td className=""><strong className="">A:</strong> </td>
      <td className="">Orders clear out of Orders Hub at 4:00 AM local device time.</td>
    </tr>
  </tbody>
</table>
</div>

