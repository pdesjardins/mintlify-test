---
title: "Updating delivery information for an order"
id: apiUpdatingDeliveryInfoForAnOrder
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiUpdatingTipsInAPayment.md
previousSectionTitle: "Updating the tip amount for a payment"
nextSectionFile: apiDevGuide-apiMarketplaceFacilitatorOrders.md
nextSectionTitle: "Marketplace facilitator orders"
externalReferences: [https://doc.toasttab.com/openapi/orders/operation/ordersOrderGuidDeliveryInfoPatch/]
excerpt: "You can use the orders API to modify the following delivery information:"
keywords: ["/deliveryInfo", "orders.delivery_info:write", "deliveredDate", "dispatchedDate", "deliveryState", "PENDING", "PICKED_UP", "IN_PROGRESS", "DELIVERED", "deliveryEmployee"]
procedures: 0
codeExamples: 0
---



> **Important**
> 
> To use the `/deliveryInfo` endpoint, you'll need access to the `orders.delivery_info:write` scope. For more information about API client scopes, and how to get access to them, see [Scopes](apiDevGuide-apiScopes).


You can use the orders API to modify the following delivery information:


<div className="table-wrapper">
<table>
  <thead>
    <tr>
      <th>Value</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>deliveredDate</code></td>
      <td>The date and time when the delivery employee indicated the order was delivered expressed in ISO 8601 format.</td>
    </tr>
    <tr>
      <td><code>dispatchedDate</code></td>
      <td>The date and time when the delivery employee indicated the order was dispatched expressed in ISO 8601 format.</td>
    </tr>
    <tr>
      <td><code>deliveryState</code></td>
      <td>The status of the delivery order. The available values for <code>deliveryState</code> are:<ul><li><code>PENDING</code>: The delivery order has not been dispatched. Corresponds to the Unassigned tab for deliveries on the Toast POS app.</li><li><code>PICKED_UP</code>: The delivery employee has picked up the order from the restaurant.</li><li><code>IN_PROGRESS</code>: The order is on its way to the destination. Corresponds to the En Route tab for deliveries on the Toast POS app.</li><li><code>DELIVERED</code>: The order was delivered. Corresponds to the Delivered tab for deliveries on the Toast POS app.</li></ul></td>
    </tr>
    <tr>
      <td><code>deliveryEmployee</code></td>
      <td>An object that contains the Toast platform GUID of the employee assigned as the delivery driver.</td>
    </tr>
    <tr>
      <td><code>notes</code></td>
      <td>Delivery notes provided by the guest who placed the order.  <blockquote><strong>Important</strong> Writing to this field overwrites the guest’s original notes and may result in the loss of important order information. Do not replace or remove the guest's notes.</blockquote> </td>
    </tr>
  </tbody>
</table>
</div>



> **Note**
> 
> The delivery location values (for example, street address and city) cannot be updated.


## How to update the delivery information

To update delivery information, you send a `PATCH` request to the `/orders/<em>&#123;orderGuid&#125;</em>/deliveryInfo`endpoint of the orders API. The request must include a JSON `DeliveryInfo` object that provides the updated values.

For more information about the endpoint used in this process, see the [/deliveryInfo reference guide.](https://doc.toasttab.com/openapi/orders/operation/ordersOrderGuidDeliveryInfoPatch/)

**Procedure 2.8. To update the delivery information for an existing order**

1. Locate the Toast platform GUID for the order you are updating. For more information on locating an order GUID see [Finding an order or check GUID](apiDevGuide-apiOrdersFindingAnOrderGuid).


2. If you plan to update an order's `deliveryEmployee`field, locate the Toast platform GUID of the employee to assign as the delivery driver. For information on retrieving employee details, see [Getting all employees of a restaurant](apiDevGuide-api_get_all_employees).


3. Create a JSON `DeliveryInfo` object that contains the delivery information you want to update. For the list of values you can modify see [Delivery values](apiDevGuide-apiUpdatingDeliveryInfoForAnOrder#apiDeliveryInfoValues).

The delivery location values (for example, street address and city) cannot be updated.

For an example `DeliveryInfo` object, see [Example DeliveryInfo object](apiDevGuide-apiUpdatingDeliveryInfoForAnOrder#apiExampleDeliveryInfoObject).


4. Send a `PATCH` request to the `/orders/<em>&#123;orderGuid&#125;</em>/deliveryInfo`endpoint of the orders API.

In the `PATCH` path, include the Toast platform GUID of the order.

In the body of the request, include the `DeliveryInfo` object with the delivery information you want to update.


5. Examine the response data you receive from the orders API. Verify your request is processed successfully with a 200 HTTP code response.

The response contains the full `Order` object. For an example, see [this response](apiDevGuide-apiUpdatingDeliveryInfoForAnOrder#apiExampleResponseDataWhenUpdatingDeliveryInfoForAnOrder).





> **Note**
> 
> Once an order's `deliveryState` is `DELIVERED`, updates are no longer allowed.


## Example DeliveryInfo object

The following example shows the `DeliveryInfo` object for updating delivery information for an order. For definitions of the values below, see [Delivery values](apiDevGuide-apiUpdatingDeliveryInfoForAnOrder#apiDeliveryInfoValues).


```
{
  "deliveredDate": "2021-09-14T17:57:42.263+0000",
  "dispatchedDate": "2021-09-14T17:57:42.263+0000",
  "deliveryState": "DELIVERED",
  "deliveryEmployee": {
    "guid": "e10f2ae0-9690-4ab2-86fe-fa6603d708d0"
  },
    "notes": "Leave order at door."
}

```



    <tr>
      <td><a href="#co-d1e2925533E9A4-9140-47FA-BA5E-B39FCEBDF6B0">(1)</a></td>
      <td>The date and time when the delivery employee indicated the order was delivered.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e2945533E9A4-9140-47FA-BA5E-B39FCEBDF6B0">(2)</a></td>
      <td>The date and time the restaurant indicated the order was available for delivery and was assigned to a delivery employee.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e2965533E9A4-9140-47FA-BA5E-B39FCEBDF6B0">(3)</a></td>
      <td>The state of a delivery order. The possible values are <code>PENDING</code>, <code>IN_PROGRESS</code>, <code>PICKED_UP</code>, or <code>DELIVERED</code>.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e2985533E9A4-9140-47FA-BA5E-B39FCEBDF6B0">(4)</a></td>
      <td>The Toast platform GUID of the delivery employee at the restaurant.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e2085533E9A4-9140-47FA-BA5E-B39FCEBDF6B0">(5)</a></td>
      <td>The delivery notes for the order. For more information, see <a href="apiDevGuide-apiUpdatingDeliveryInfoForAnOrder#apiDeliveryInfoValues">notes</a>.</td>
    </tr>
## Example response when updating delivery information

The following example shows the response for a `PATCH`request to the `/orders/<em>&#123;orderGuid&#125;</em>/deliveryInfo`endpoint of the orders API.


```
{
  "guid": "d16ceaeb-d8a3-4d47-82db-0199d37c0713",
  "entityType": "Order",
 
 [contents omitted]

  "deliveryInfo": {
    "address1": "401 Park Drive",
    "address2": "Suite 801",
    "city": "Boston",
    "state": "MA",
    "zipCode": "02215",
    "latitude": 42.3446671,
    "longitude": -71.1023575,
    "notes": "Leave order at door.",
    "deliveredDate": "2021-09-14T17:57:42.263+0000",
    "dispatchedDate": "2021-09-14T17:57:42.263+0000",
    "deliveryEmployee": {
      "guid": "e10f2ae0-9690-4ab2-86fe-fa6603d708d0",
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "deliveryState": "DELIVERED"
  },

  [contents omitted]

  "diningOption": {
    "guid": "f6cd5b58-27d7-462a-922f-7f919a6f9137",
    "entityType": "DiningOption",
    "externalId": null
  },
 
  [contents omitted]

}
```



    <tr>
      <td><a href="#co-d1e2255533E9A4-9140-47FA-BA5E-B39FCEBDF6B0">(1)</a></td>
      <td>The Toast platform GUID assigned to this order.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e2275533E9A4-9140-47FA-BA5E-B39FCEBDF6B0">(2)</a></td>
      <td>Information about the delivery, including address information and any values you updated.</td>
    </tr>
    <tr>
      <td><a href="#co-d1e2385533E9A4-9140-47FA-BA5E-B39FCEBDF6B0">(3)</a></td>
      <td>The Toast platform GUID of the dining option for this order. For delivery orders, the dining option must have <code>behavior</code> set to <code>DELIVERY</code>.</td>
    </tr>
## Viewing the delivery information in the Toast POS application

The following image shows an order on the Unassigned tab of the Deliveryscreen on a Toast POS device.

![The Delivery screen with the Unassigned tab emphasized.](https://doc.toasttab.com/doc/media/api-orders-view-unassigned-delivery-order.png)

The following image shows the order on the Delivered tab after a `PATCH` request changed the order status to `DELIVERED` and added a delivery employee.

![The Delivery screen with the Delivered tab emphasized.](https://doc.toasttab.com/doc/media/api-orders-view-delivered-delivery-order.png)

