---
title: "Managing first-party delivery orders"
id: platformManagingDeliveryOrders
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformOrdersHubOmitChunkFromSearchIndex.md
parentSectionTitle: "Orders Hub"
previousSectionFile: adminGuide-platformUsingOrdersHub.md
previousSectionTitle: "Using Orders Hub"
nextSectionFile: adminGuide-platformOrdersHubFAQs.md
nextSectionTitle: "FAQs"
externalReferences: [https://central.toasttab.com/s/article/Toast-Delivery-Services-Troubleshooting-FAQ, https://central.toasttab.com/s/article/Delivery-Mode-1493048871021#DispatchDriver]
excerpt: "The..."
keywords: ["managing", "firstparty", "delivery", "orders", "You don’t have permission to complete delivery orders or delivery orders you are not assigned to."]
procedures: 1
codeExamples: 0
---



> **Note**
> 
> If the delivery drivers for your restaurant are employees of the restaurant, you will not be able use Toast Delivery Services (TDS). For more information, see [this Toast Central article](https://central.toasttab.com/s/article/Toast-Delivery-Services-Troubleshooting-FAQ). For TDS orders, you can only Redispatch a driver. You will not be able to assign and dispatch a driver from the Delivery screen on the Toast POS app.


The Delivery mode on the Toast POS app, has a built-in function that allows you to manage delivery orders, dispatch drivers, and mark orders as complete. The Delivery mode is different from TDS, as Deliverymode uses your own drivers and not an on-demand delivery service.



> **Note**
> 
> To use the Delivery Mode screen, you must have the 2. Delivery Access permission. From Toast Web, choose Employees &gt; Employee management &gt; Jobs to open the Jobs page. Select the job title to edit the permissions.For more information about permissions, see [POS access permissions](adminGuide-adminPermissions#adminModePermissions).


An Order Ready order must be assigned to a driver before it can be marked as complete. To assign and dispatch a driver from the Orders Hub screen:

1. On the Order Ready entry, select the Complete button. If the order has not been paid for yet, select the Pay $ button to complete payment before assigning a driver. If the order has been paid for, a dialog box appears prompting you to select the Dispatch driver button. Select the Cancelbutton to cancel out of the dialog box.


2. Selecting the Dispatch driver button opens the Delivery screen. On this screen, you can select the DISPATCH DRIVER button at the top right to [dispatch a driver](https://central.toasttab.com/s/article/Delivery-Mode-1493048871021#DispatchDriver). Select your driver and then select the OK button.

After you dispatch a driver, the order moves to the EN ROUTE tab on the Delivery screen. The order status changes from Unassigned to En Routeon the Orders Hub screen.



> **Note**
> 
> You must have the 2. Delivery Accesspermission or be assigned the driver to be able to mark the order as complete. If you do not have permission or are not the driver, an error message appears on the Orders Hub screen. The error message displays: `You don’t have permission to complete delivery orders or delivery orders you are not assigned to.`



3. On the Orders Hub screen, you can mark an order as complete by selecting the Complete button. This moves the order to the Completed tab on the Orders Hub screen and moves the order to the DELIVERED tab on the Delivery screen.



## Toast Delivery Services statuses

When your restaurant fulfills a guest delivery order using Toast Delivery Services (TDS), the Orders Hub screen displays one of the following blue status indicators to show fulfillment progress:


<table>
  <thead>
    <tr>
      <th>Status</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>DRIVER REQUESTED </td>
      <td>A new delivery person has been requested and dispatched to pick up and deliver the order. </td>
    </tr>
    <tr>
      <td>EN ROUTE TO RESTAURANT - ETA HH:MM </td>
      <td>A delivery person has been assigned to the order and is on their way to pick up the order.</td>
    </tr>
    <tr>
      <td>HERE FOR PICKUP </td>
      <td>The delivery person has arrived at the restaurant and is ready to pick up the order.</td>
    </tr>
    <tr>
      <td>DRIVING TO DROP OFF </td>
      <td>The delivery person is on their way to drop off the guest’s order.</td>
    </tr>
    <tr>
      <td>DROPPING OFF - ETA HH:MM</td>
      <td>The delivery person is to drop off the guest’s order by an estimated time. </td>
    </tr>
    <tr>
      <td>DELIVERED </td>
      <td>The delivery person delivered the guest’s order at the requested address.</td>
    </tr>
    <tr>
      <td>DELIVERY CANCELLED </td>
      <td>The delivery person who was previously assigned to pick up this order has cancelled the pick up. <br/> Select the Redispatch button to request a new delivery person for the order. An additional delivery fee may be charged. </td>
    </tr>
    <tr>
      <td>UNDELIVERABLE</td>
      <td>The delivery person was unable to locate your delivery location. </td>
    </tr>
  </tbody>
</table>

