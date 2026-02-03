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
> To use the `/deliveryInfo` endpoint, you'll need access to the `orders.delivery_info:write` scope. For more information about API client scopes, and how to get access to them, see [Scopes](apiScopes.html).


You can use the orders API to modify the following delivery information:

| Value | Description | 
| --- | --- |
| `deliveredDate` | The date and time when the delivery employee indicated the order was delivered expressed in ISO 8601 format. | 
| `dispatchedDate` | The date and time when the delivery employee indicated the order was dispatched expressed in ISO 8601 format. | 
| `deliveryState` | The status of the delivery order. The available values for `deliveryState` are:- `PENDING`: The delivery order has not been dispatched. Corresponds to the Unassignedtab for deliveries on the Toast POS app.
- `PICKED_UP`: The delivery employee has picked up the order from the restaurant.
- `IN_PROGRESS`: The order is on its way to the destination. Corresponds to the En Routetab for deliveries on the Toast POS app.
- `DELIVERED`: The order was delivered. Corresponds to the Delivered tab for deliveries on the Toast POS app.

 | 
| `deliveryEmployee` | An object that contains the Toast platform GUID of the employee assigned as the delivery driver. | 
| `notes` | Delivery notes provided by the guest who placed the order. 

> **Important**
> 
> Writing to this field overwrites the guest’s original notes and may result in the loss of important order information. Do not replace or remove the guest's notes.


 | 



> **Note**
> 
> The delivery location values (for example, street address and city) cannot be updated.


#### How to update the delivery information

To update delivery information, you send a `PATCH` request to the `/orders/<em>\{orderGuid\}</em>/deliveryInfo`endpoint of the orders API. The request must include a JSON `DeliveryInfo` object that provides the updated values.

For more information about the endpoint used in this process, see the [/deliveryInfo reference guide.](https://doc.toasttab.com/openapi/orders/operation/ordersOrderGuidDeliveryInfoPatch/)

**Procedure 2.8. To update the delivery information for an existing order**

1. Locate the Toast platform GUID for the order you are updating. For more information on locating an order GUID see [Finding an order or check GUID](apiOrdersFindingAnOrderGuid.html).


2. If you plan to update an order's `deliveryEmployee`field, locate the Toast platform GUID of the employee to assign as the delivery driver. For information on retrieving employee details, see [Getting all employees of a restaurant](api_get_all_employees.html).


3. Create a JSON `DeliveryInfo` object that contains the delivery information you want to update. For the list of values you can modify see [Delivery values](apiUpdatingDeliveryInfoForAnOrder.html#apiDeliveryInfoValues).

The delivery location values (for example, street address and city) cannot be updated.

For an example `DeliveryInfo` object, see [Example DeliveryInfo object](apiUpdatingDeliveryInfoForAnOrder.html#apiExampleDeliveryInfoObject).


4. Send a `PATCH` request to the `/orders/<em>\{orderGuid\}</em>/deliveryInfo`endpoint of the orders API.

In the `PATCH` path, include the Toast platform GUID of the order.

In the body of the request, include the `DeliveryInfo` object with the delivery information you want to update.


5. Examine the response data you receive from the orders API. Verify your request is processed successfully with a 200 HTTP code response.

The response contains the full `Order` object. For an example, see [this response](apiUpdatingDeliveryInfoForAnOrder.html#apiExampleResponseDataWhenUpdatingDeliveryInfoForAnOrder).





> **Note**
> 
> Once an order's `deliveryState` is `DELIVERED`, updates are no longer allowed.


#### Example DeliveryInfo object

The following example shows the `DeliveryInfo` object for updating delivery information for an order. For definitions of the values below, see [Delivery values](apiUpdatingDeliveryInfoForAnOrder.html#apiDeliveryInfoValues).

```
\{
  "deliveredDate": "2021-09-14T17:57:42.263+0000",
  "dispatchedDate": "2021-09-14T17:57:42.263+0000",
  "deliveryState": "DELIVERED",
  "deliveryEmployee": \{
    "guid": "e10f2ae0-9690-4ab2-86fe-fa6603d708d0"
  \},
    "notes": "Leave order at door."
\}

```



(1) The date and time when the delivery employee indicated the order was delivered.

(2) The date and time the restaurant indicated the order was available for delivery and was assigned to a delivery employee.

(3) The state of a delivery order. The possible values are PENDING, IN_PROGRESS, PICKED_UP, or DELIVERED.

(4) The Toast platform GUID of the delivery employee at the restaurant.

(5) The delivery notes for the order. For more information, see notes.

#### Example response when updating delivery information

The following example shows the response for a `PATCH`request to the `/orders/<em>\{orderGuid\}</em>/deliveryInfo`endpoint of the orders API.

```
\{
  "guid": "d16ceaeb-d8a3-4d47-82db-0199d37c0713",
  "entityType": "Order",
 
 [contents omitted]

  "deliveryInfo": \{
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
    "deliveryEmployee": \{
      "guid": "e10f2ae0-9690-4ab2-86fe-fa6603d708d0",
      "entityType": "RestaurantUser",
      "externalId": null
    \},
    "deliveryState": "DELIVERED"
  \},

  [contents omitted]

  "diningOption": \{
    "guid": "f6cd5b58-27d7-462a-922f-7f919a6f9137",
    "entityType": "DiningOption",
    "externalId": null
  \},
 
  [contents omitted]

\}
```



(1) The Toast platform GUID assigned to this order.

(2) Information about the delivery, including address information and any values you updated.

(3) The Toast platform GUID of the dining option for this order. For delivery orders, the dining option must have behavior set to DELIVERY.

#### Viewing the delivery information in the Toast POS application

The following image shows an order on the Unassigned tab of the Deliveryscreen on a Toast POS device.

![The Delivery screen with the Unassigned tab emphasized.](https://doc.toasttab.com/doc/media/api-orders-view-unassigned-delivery-order.png)

The following image shows the order on the Delivered tab after a `PATCH` request changed the order status to `DELIVERED` and added a delivery employee.

![The Delivery screen with the Delivered tab emphasized.](https://doc.toasttab.com/doc/media/api-orders-view-delivered-delivery-order.png)

