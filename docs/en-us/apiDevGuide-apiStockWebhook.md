---
title: "Stock webhook"
id: apiStockWebhook
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalWebhooksReferenceOmitChunkFromSearchIndex.md
parentSectionTitle: "Webhooks reference"
previousSectionFile: apiDevGuide-apiRxOnlineOrderingScheduleWebhook.md
previousSectionTitle: "Restaurant online ordering schedule webhook"
nextSectionFile: apiDevGuide-portalOutboundIntegrationsOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 10. Outbound integrations"
externalReferences: [https://central.toasttab.com/s/article/Quick-Edit-Mode-1492794309057]
excerpt: "The stock webhook allows you to receive updates when the inventory status of a menu item or a modifier (via its item reference) changes."
keywords: [eventCategory,eventType,out_of_stock]
procedures: 0
codeExamples: 0
---

### Stock webhook

The `stock` webhook allows you to receive updates when the inventory status of a menu item or a modifier (via its item reference) changes.



> **Note**
> 
> Modifiers are supported by an underlying menu item, called the modifier item reference. In this section, the term *menu item* refers to both menu items and modifier item references, as the stock webhook reports on their status in the same way. For detailed information on modifier item references, see [Understanding a modifier item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference).


Stock webhook messages follow the [standard message data schema](portalWebhooksOmitChunkFromSearchIndex.html#apiMessageDataSchema). When a message is published to your webhook endpoint for the `stock`event category, the `eventCategory` value is set to `stock` and the `eventType` is set to one of the following:

- [in_stock](apiStockWebhook.html#apiInStock)


- [out_of_stock](apiStockWebhook.html#apiOutOfStock)


- [low_quantity](apiStockWebhook.html#apiLowQuantity)



A menu item's inventory can be changed in the [stock API](apiUpdatingInventoryInformationOmitChunkFromSearchIndex.html#apiUpdatingInventoryInformation), in the Toast app, and in Toast Web, and set to one of the following:

- In Stock: The menu item is in stock. There is no specific quantity associated with the menu item but it is assumed to be available.


- Out of Stock: The menu item is not in stock and cannot be ordered.


- Quantity: A specific quantity for the menu item is defined. As the menu item is ordered, the quantity is decremented. When the quantity dips below the low quantity threshold, the low quantity webhook will fire. When the quantity reaches 0, the menu item's status changes to out of stock. Currently, the low quantity threshold is set to 5 for all menu items and is not configurable.



Stock webhook events reflect changes to these settings or to a menu item's quantity. For example, an `out_of_stock` event is triggered when a menu item's quantity has reached 0 or it has been manually marked as out of stock.

To set a menu item's stock status in the Toast app, a restaurant uses Quick Edit mode (described in this [Toast Central article](https://central.toasttab.com/s/article/Quick-Edit-Mode-1492794309057)). To set it in Toast Web, the restaurant uses the Inventory section of the menu item's details page.

#### in_stock

The menu item has been manually marked as in stock or its quantity has been set to a value that exceeds the low quantity threshold. Currently, the low quantity threshold is set to 5 for all menu items and is not configurable.

Attributes in the `in_stock` event's payload include:

| Value | Description | 
| --- | --- |
| `itemGuid` | A unique identifier for the menu item, assigned by the Toast platform.data type:stringformat:uuid | 
| `multiLocationId` | A consistent identifier that applies to all versions of a menu item that is shared across locations.Requests sent to Toast APIs can use a combination of the `multiLocationId` and `restaurantGuid` values, instead of the `itemGuid` value, to identify a menu item. Integration clients can extract the `multiLocationId` and `restaurantGuid` from stock webhook messages to use in subsequent requests to Toast APIs. This is the recommended method for identifying menu items in Toast API requests. See [Toast identifiers](portalToastIdentifiers.html) for more information.data type:string | 
| `restaurantGuid` | A unique identifier for the restaurant, assigned by the Toast platform.data type:stringformat:uuid | 
| `quantity` | Indicates the quantity of this menu item that is available. This value is included if the `status`attribute is set to `QUANTITY` and omitted if the status attribute is set to `IN_STOCK`.data type:numberformat:double | 
| `status` | `IN_STOCK` or `QUANTITY`data type:string | 
| `versionId` | Reserved for future use. | 

**Example 9.13. Payload for an in_stock event when a menu item is manually marked as In Stock**

```
{
  "timestamp": "<ISO formatted timestamp in UTC>",
  "eventCategory": "stock",
  "eventType": "in_stock",
  "guid": "e445f586-081c-4a2a-bcd6-30717a48e17a",
  "details": {
    "itemGuid": "1e199622-ccbf-4ba8-8c37-111519dca13b",
    "restaurantGuid": "3325cc58-dc6e-4e21-85f9-7de275ffe820",
    "status": "IN_STOCK",
    "multiLocationId": "100000000171238879",
    "versionId": "1e199622-ccbf-4ba8-8c37-111519dca13b"    
  }
}
```

  
**Example 9.14. Payload for an in_stock event when a menu item's quantity is manually set and that quantity exceeds the low quantity threshold**

```
{
  "timestamp": "<ISO formatted timestamp in UTC>",
  "eventCategory": "stock",
  "eventType": "in_stock",
  "guid": "e445f586-081c-4a2a-bcd6-30717a48e17a",
  "details": {
    "itemGuid": "1e199622-ccbf-4ba8-8c37-111519dca13b",
    "restaurantGuid": "3325cc58-dc6e-4e21-85f9-7de275ffe820",
    "status": "QUANTITY",
    "quantity": 10.0,
    "multiLocationId": "100000000171239701",
    "versionId": "1e199622-ccbf-4ba8-8c37-111519dca13b"
  }
}
```

  
#### out_of_stock

The menu item's quantity has reached 0 or it has been manually marked as out of stock.

Attributes in the `out_of_stock` event's payload include:

| Value | Description | 
| --- | --- |
| `itemGuid` | A unique identifier for the menu item, assigned by the Toast platform.data type:stringformat:uuid | 
| `multiLocationId` | A consistent identifier that applies to all versions of a menu item that is shared across locations.Requests sent to Toast APIs can use a combination of the `multiLocationId` and `restaurantGuid` values, instead of the `itemGuid` value, to identify a menu item. Integration clients can extract the `multiLocationId` and `restaurantGuid` from stock webhook messages to use in subsequent requests to Toast APIs. This is the recommended method for identifying menu items in Toast API requests. See [Toast identifiers](portalToastIdentifiers.html) for more information.data type:string | 
| `restaurantGuid` | A unique identifier for the restaurant, assigned by the Toast platform.data type:stringformat:uuid | 
| `status` | `OUT_OF_STOCK`data type: string | 
| `versionId` | Reserved for future use. | 

**Example 9.15. Payload example for the out_of_stock event**

```
{
  "timestamp": "<ISO formatted timestamp in UTC>",
  "eventCategory": "stock",
  "eventType": "out_of_stock",
  "guid": "e445f586-081c-4a2a-bcd6-30717a48e17a",
  "details": {
    "itemGuid": "1e199622-ccbf-4ba8-8c37-111519dca13b",
    "restaurantGuid": "3325cc58-dc6e-4e21-85f9-7de275ffe820",
    "status": "OUT_OF_STOCK",
    "multiLocationId": "100000000171239569",
    "versionId": "1e199622-ccbf-4ba8-8c37-111519dca13b"
  }
}
```

  
#### low_quantity

The `low_quantity` webhook event is triggered when either of the following occurs:

- The menu item's quantity dips below the low quantity threshold. Currently, the low quantity threshold is set to 5 for all menu items and is not configurable. The amount remaining is indicated by the `quantity` value in the event's payload.


- The quantity of the menu item has been manually set to a value that is greater than 0 and less than or equal to 5 (the low quantity threshold). The value it was set to is indicated by the `quantity` value in the event's payload.

If an item is out of stock and the quantity is manually set to an amount that is less than or equal to 5, a `low_quantity`webhook event fires, rather than an `in_stock` event, even though the item has technically gone from out of stock to in stock.

If your integration has the requirement that anytime the quantity of an item is manually set to a value greater than 0, it is considered "in stock", then it must handle both the `in_stock` and `low_quantity` webhook events to cover manually setting a stock quantity of 1 to 5 (`low_quantity`) or greater than 5 (`in_stock`).



Attributes in the `low_quantity` event's payload include:

| Value | Description | 
| --- | --- |
| `itemGuid` | A unique identifier for the menu item, assigned by the Toast platform.data type:stringformat:uuid | 
| `multiLocationId` | A consistent identifier that applies to all versions of a menu item that is shared across locations.Requests sent to Toast APIs can use a combination of the `multiLocationId` and `restaurantGuid` values, instead of the `itemGuid` value, to identify a menu item. Integration clients can extract the `multiLocationId` and `restaurantGuid` from stock webhook messages to use in subsequent requests to Toast APIs. This is the recommended method for identifying menu items in Toast API requests. See [Toast identifiers](portalToastIdentifiers.html) for more information.data type:string | 
| `quantity` | Indicates the quantity of this menu item that is available.data type:numberformat:double | 
| `restaurantGuid` | A unique identifier for the restaurant, assigned by the Toast platform.data type:stringformat:uuid | 
| `status` | `QUANTITY`data type: string | 
| `versionId` | Reserved for future use. | 

**Example 9.16. Payload example for the low_quantity event**

```
{
  "timestamp": "<ISO formatted timestamp in UTC>",
  "eventCategory": "stock",
  "eventType": "low_quantity",
  "guid": "e445f586-081c-4a2a-bcd6-30717a48e17a",
  "details": {
    "itemGuid": "1e199622-ccbf-4ba8-8c37-111519dca13b",
    "restaurantGuid": "3325cc58-dc6e-4e21-85f9-7de275ffe820",
    "status": "QUANTITY",
    "quantity": 5.0,
    "multiLocationId": "100000000171241912",
    "versionId": "1e199622-ccbf-4ba8-8c37-111519dca13b"
  }
}
```

  
