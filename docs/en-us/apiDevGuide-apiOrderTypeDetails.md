---
title: "Order details based on the order dining option"
id: apiOrderTypeDetails
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalCreatingAndUpdatingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Updating order information"
previousSectionFile: apiDevGuide-apiUsingMultiLocationIdsInOrders.md
previousSectionTitle: "Using multi-location IDs in orders"
nextSectionFile: apiDevGuide-apiSpecifyingModifiersAndInstructions.md
nextSectionTitle: "Specifying modifiers and instructions for menu item selections"
externalReferences: [https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/, https://doc.toasttab.com/openapi/configuration/operation/tablesGet/, https://doc.toasttab.com/openapi/labor/operation/employeesGet/]
excerpt: "Some of the required order details are based on the selected dining option."
keywords: ["Order", "Check", "diningOption"]
procedures: 0
codeExamples: 1
---

Some of the required order details are based on the selected dining option.

A dining option describes a customizable workflow for an order. Restaurants define their dining options. The selected dining option affects the required values in the `Order` and `Check`objects.

In each order, the `diningOption` object specifies the GUID of the dining option to use. For example:


```
"diningOption": {
  "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
  "entityType": "DiningOption"
},
```

You use the configuration API to retrieve the available dining option GUIDs.

## Types of dining options

The restaurant defines the available dining options. For more information about dining options and how to configure them, see [Dining options](adminGuide-adminDiningOptions) in the *Platform Guide*.

Each dining option includes a `behavior` field that indicates the type of dining option.

The available dining behaviors are:



**`DINE_IN`**
: Used for dining options where the guest orders and remains at the restaurant.

For dine-in orders, you can provide table and server values.



**`TAKE_OUT`**
: Used for dining options where the guest picks up the order from the restaurant.

Orders with takeout dining options must provide `customer` information.

A takeout option can have `curbside` set to `true`, which indicates it is a curbside pickup option. Curbside pickup orders should also provide `curbsidePickupInfo`.

Note that in Toast Web, the dining option configuration lists takeout and curbside as separate options for the dining behavior.



**`DELIVERY`**
: Used for dining options where the order is delivered to the guest.

Orders with delivery dining options must provide `customer` and `deliveryInfo`information.





Restaurants can configure multiple dining options for a given behavior. For example, they can have different delivery options to help to differentiate between orders that are delivered by the restaurant and orders that are delivered by a service.

## Retrieving the available dining options

When you create an order, the `diningOption` value must specify the GUID of the dining option to use for the order.

To get a list of the available dining options for a restaurant, send a `GET` request to the `/diningOptions`endpoint of the configuration API. For more information, see [Get dining options](https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/) in the API reference.

Here is an example of the request results:


```
{
  "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
  "entityType": "DiningOption",
  "externalId": null,
  "name": "Curbside pickup",
  "curbside": true,
  "behavior": "TAKE_OUT"
},
{
  "guid": "7c6843f3-db7d-4096-bdd2-4eefd99b900f",
  "entityType": "DiningOption",
  "externalId": null,
  "name": "Takeout",
  "curbside": false,
  "behavior": "TAKE_OUT"
},
{
  "guid": "23fc2559-fc37-46ce-a963-cc5fdb88af0c",
  "entityType": "DiningOption",
  "externalId": null,
  "name": "Dine-in",
  "curbside": false,
  "behavior": "DINE_IN"
},
{
  "guid": "b1b10604-a8f9-4a21-ae86-7db974ee9dbf",
  "entityType": "DiningOption",
  "externalId": null,
  "name": "Delivery",
  "curbside": false,
  "behavior": "DELIVERY"
}
```

## Creating a dine-in order

A dine-in order uses a dining option where `behavior` is `DINE_IN`. For a dine-in order, in addition to the menu item selections, you can provide information about the table and server.

### Providing table information for a dine-in order

You can create a dine-in order at a specific restaurant table.

When you create an order for a specific table, you can also provide customer information for the check that is associated with the order. For example, to reserve a table for a guest, a reservation service might `POST` a scheduled order that specifies the restaurant table and guest information but does not specify any menu item selections.

To specify the table for an order, provide a `Table`object that specifies the Toast platform GUID of the table. For example:


```
"table": {
  "guid": "170b5f39-060e-45c3-89f0-4907c16ab12c",1
  "entityType": "Table"
},
```

To retrieve the GUIDs of the available tables, send a `GET` request to the `/tables` endpoint of the configuration API. For more information, see [Get tables](https://doc.toasttab.com/openapi/configuration/operation/tablesGet/) in the API reference.

When you use the orders API to create an order at a restaurant table, that order is available from a Toast POS device in the table layout and open orders displays. The behavior of the table layout screen depends on whether the table has an existing open order.

- If the table does not have an existing order, selecting the table opens the order that you created in the orders API.


- If the table does have an existing order, then the order you created in the orders API is not visible at the table until the previous order is closed.



### Providing server information for a dine-in order

You can specify the restaurant employee who is responsible for the order.

To specify the restaurant employee, provide a `server`object that specifies the Toast platform GUID of the employee. For example:


```
"server": {
  "guid": "dc9b7cd6-4389-4a6d-83c3-2fde7f033567",
  "entityType": "RestaurantUser"
},
```

The employee must be an active employee at the current restaurant location. The orders API does not prevent you from specifying a deleted employee.

To retrieve information about restaurant employees, send a `GET` request to the `/employees` endpoint of the labor API. For more information, see [Get employees](https://doc.toasttab.com/openapi/labor/operation/employeesGet/) in the API reference.

### Example POST message body for a dine-in order

The following example shows the message body for a `POST`request to the `/orders` endpoint to create a dine-in order at a restaurant table.


```
{
  "entityType": "Order",
  "table": {
    "guid": "170b5f39-060e-45c3-89f0-4907c16ab12c",
    "entityType": "Table"
  },
  "server": {
    "guid": "dc9b7cd6-4389-4a6d-83c3-2fde7f033567",
    "entityType": "RestaurantUser"
  },
  "diningOption": {
    "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
    "entityType": "DiningOption"
  },
  "revenueCenter": {
    "guid": "908f0483-ac03-4c9a-a5a4-43c37786e237",
    "entityType": "RevenueCenter"
  },
  "checks": [
    {
      "entityType": "Check",
      "customer": {
        "entityType": "Customer",
        "firstName": "Severe",
        "lastName": "Thibault",
        "phone": "555-555-5555",
        "email": "severe@example.com"
      }
    }
  ]
}
```



(1) The table value provides the GUID of the table to create the order at. You can get the GUIDs of restaurant tables from the configuration API. Specifying a table is optional.

(2) The server value provides the GUID of the restaurant employee who is responsible for the order. Specifying an employee is optional.

(3) To create an order at a table, the behavior of the selected dining option must be DINE_IN.

 You can specify the revenue center associated with the order. Specifying a revenue center is optional.

(5) You must include a checks value with at least one Check object. The check does not need to include any menu item selections. You can optionally include a customervalue with information about the restaurant guest.

 In a Customer object, the email value is the unique identifier for a guest. email must be unique for each individual guest.

## Creating a takeout order

A takeout order uses a dining option where `behavior` is `TAKE_OUT`.

For takeout orders, in addition to the menu item selections, you provide information about the guest who will pick up the order.

### Providing guest information for a takeout order

For a takeout order, the `Check` object must include a `customer` object that contains name and contact information for the guest.

In the `customer` object, the `firstName`, `lastName`, `phone`, and `email` fields are required.

### Example POST message body for a takeout order

The following example shows the message body for a `POST`request to the `/orders` endpoint to create a takeout order.


```
{
  "entityType": "Order",
  "diningOption": {
    "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
    "entityType": "DiningOption"
  },
  "checks": [
    {
      "entityType": "Check",
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "75cd1156-c33a-4842-9cbd-717aebbf069e",
            "entityType": "MenuGroup"
          },
          "item": {
            "entityType": "MenuItem",
            "guid": "2478cec3-bca2-4956-a3aa-eda571d5518a"
          },
          "quantity": 1,
          "modifiers": []
        }
      ],
      "customer": {
          "entityType": "Customer",
          "firstName": "Jack",
          "lastName": "Jones",
          "phone": "333-555-5555",
          "email": "jack@example.com"
      }
    }
  ]
}
```



(1) The GUID of the dining option for the order. The dining option must have a behavior of TAKE_OUT.

(2) The selections object contains the menu item selections for the order.

(3) The customer object contains information about the guest who will pick up the order. This information is mandatory for takeout orders. The firstName, lastName, phone, and email fields are required. The data must be correctly formatted. For example, the phone number must have exactly 10 digits.

 In a customer object, the email value is the unique identifier for a guest. email must be unique for each individual guest.

### Example response to a takeout order POST request

The following example shows the response from the `/orders` endpoint for a takeout order.


```
{
  "guid": "df8cd211-c5c9-4fe4-b56b-fa0db87eb80b",
  "entityType": "Order",
  "externalId": null,
  "revenueCenter": null,
  "server": null,
  "deliveryInfo": null,
  "serviceArea": null,
  "numberOfGuests": 1,
  "diningOption": {
    "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
    "entityType": "DiningOption",
    "externalId": null
  },
  "source": "API",
  "voidDate": null,
  "openedDate": "2017-10-04T13:54:00.969+0000",
  "duration": null,
  "businessDate": 20171004,
  "voidBusinessDate": null,
  "checks": [
    {
      "guid": "602d2cec-eb97-4be0-948f-4a38f614c1f1",
      "entityType": "Check",
      "externalId": null,
      "displayNumber": "51",
      "amount": 9.99,
      "tabName": null,
      "taxExempt": false,
      "payments": [],
      "appliedDiscounts": [],
      "voidDate": null,
      "openedDate": "2017-10-04T13:54:00.970+0000",
      "totalAmount": 10.69,
      "selections": [
        {
          "guid": "13ae0536-bff4-4d24-a13a-722508a2556a",
          "entityType": "MenuItemSelection",
          "externalId": null,
          "itemGroup": {
            "guid": "75cd1156-c33a-4842-9cbd-717aebbf069e",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "deferred": false,
          "item": {
            "guid": "2478cec3-bca2-4956-a3aa-eda571d5518a",
            "entityType": "MenuItem",
            "externalId": null
          },
          "quantity": 1,
          "preDiscountPrice": 9.99,
          "voidReason": null,
          "optionGroup": null,
          "displayName": "Egg Sandwich",
          "appliedDiscounts": [],
          "tax": 0.7,
          "modifiers": [],
          "voidDate": null,
          "fulfillmentStatus": "NEW",
          "salesCategory": null,
          "selectionType": "NONE",
          "voidBusinessDate": null,
          "createdDate": "2017-10-04T13:54:00.997+0000",
          "preModifier": null,
          "price": 9.99,
          "modifiedDate": "2017-10-04T13:54:00.997+0000",
          "voided": false,
          "appliedTaxes": [
            {
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "92c6c470-74bb-4f84-b31f-2c144b70a285",
                "entityType": "TaxRate"
              },
              "name": "Local Tax",
              "rate": 0.0075,
              "taxAmount": 0.075,
              "type": "PERCENT"
            },
            {
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "d5b88c05-1348-42ef-b1d3-577a83d70a80",
                "entityType": "TaxRate"
              },
              "name": "State Tax",
              "rate": 0.0625,
              "taxAmount": 0.625,
              "type": "PERCENT"
            }
          ]
        }
      ],
      "voidBusinessDate": null,
      "deleted": false,
      "paidDate": null,
      "closedDate": null,
      "deletedDate": null,
      "modifiedDate": "2017-10-04T13:54:01.022+0000",
      "appliedLoyaltyInfo": null,
      "voided": false,
      "taxAmount": 0.7,
      "appliedServiceCharges": [],
      "paymentStatus": "OPEN",
      "customer": {
        "guid": "3d4b9481-4e96-42dd-8dea-d59184819cbb",
        "entityType": "Customer",
        "firstName": "Jack",
        "lastName": "Jones",
        "phone": "3335555555",
        "email": "jack@example.com"
      }
    }
  ],
  "deleted": false,
  "paidDate": null,
  "closedDate": null,
  "deletedDate": null,
  "restaurantService": null,
  "modifiedDate": "2017-10-04T13:54:01.024+0000",
  "promisedDate": null,
  "voided": false,
  "estimatedFulfillmentDate": "2017-10-04T14:24:00.969+0000",
  "table": null
}
```



(1) The unique identifier that the Toast platform assigns to the order.

(2) The payment information is empty because the order request was made without a payments value. This means that the guest did not make any payments for this check.

(3) The total amount (including tax) of this check.

(4) The date and time are null because the guest did not make a payment for the check.

(5) Information about the guest who will pick up the order.

## Creating a curbside pickup order

A curbside pickup order is a variation of a takeout order. Instead of the guest entering the restaurant to pick up the order, a restaurant employee brings the order out to the guest's vehicle.

A curbside pickup order uses a dining option where `behavior` is `TAKE_OUT` and `curbside` is `true`.

In addition to the required `customer` value for a takeout order, you can also provide `curbsidePickupInfo` to identify the vehicle that is picking up the order.

### Providing curbside pickup information for a curbside pickup order

When you place an order that specifies a dining option with curbside behavior, the request body can include the `curbsidePickupInfo`object.


```
"curbsidePickupInfo": {
  "entityType": "CurbsidePickup",
  "notes": "Convertible with top down",
  "transportColor": "blue",
  "transportDescription": "Street Cruiser"
},
```

The `curbsidePickupInfo` object is not required, but it is recommended, to help restaurant staff to identify a guest when they arrive to pick up their order.

The `curbsidePickupInfo` object must at a minimum contain `transportDescription`. The `transportDescription`value accepts string input and contains information about a guest's mode of transportation. For example, you can specify the make and model of their vehicle.

You can also optionally provide `transportColor` and `notes`.

On Toast POS devices, the curbside pickup information is displayed at the top of a check on the order screen. The information is also printed on kitchen tickets and guest receipts. The following example shows the guest's name, vehicle description, and phone number displayed at the top of a check on the order screen.

![An orders screen with the guest's curbside information emphasized.](https://doc.toasttab.com/doc/media/api-orders-create-curbside-order.png)

### Example POST message body for a curbside pickup order

The following example shows the message body for a `POST`request to the `/orders` endpoint to create a curbside pickup order.


```
{
  "entityType": "Order",
  "diningOption": {
    "guid": "18855a26-40d4-4a8f-b484-c6af211dd597",
    "entityType": "DiningOption"
  },
  "curbsidePickupInfo": {
    "entityType": "CurbsidePickup",
    "notes": "Convertible with top down",
    "transportColor": "blue",
    "transportDescription": "Street Cruiser"
  },

  "checks": [
    {
      "entityType": "Check",
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "75cd1156-c33a-4842-9cbd-717aebbf069e",
            "entityType": "MenuGroup"
          },
          "item": {
            "entityType": "MenuItem",
            "guid": "2478cec3-bca2-4956-a3aa-eda571d5518a"
          },
          "quantity": 1,
          "modifiers": []
        }
      ],
      "customer": {
          "entityType": "Customer",
          "firstName": "Alice",
          "lastName": "Patron",
          "phone": "333-555-5555",
          "email": "alice@example.com"
      }
    }
  ]
}
```



(1) The GUID of the dining option for the order. For a curbside pickup dining option, behavior is TAKE_OUTand curbside is true.

(2) The curbsidePickupInfo object contains information about the guest's mode of transportation. The restaurant uses the information in the transportDescription, transportColor, and notes fields to identify the guest when they arrive to pick up the order. transportDescription is required for curbside pickup orders.

(3) The selections object contains menu item selections for the order.

(4) The customer object contains information about the guest who will pick up the order. customer is mandatory for curbside pickup orders. firstName, lastName, phone, and email are required. The data must be correctly formatted. For example, the phone number must have exactly 10 digits.

(5) In a customer object, the email value is the unique identifier for a guest. email must be unique for each individual guest.

### Example response to a curbside pickup order POST request

The following example shows the response from the `/orders` endpoint to a curbside pickup order request.


```
{
    "guid": "db3acf81-e63e-47ed-aa1b-cba97e15549f",
    "entityType": "Order",
    "externalId": null,
    "revenueCenter": null,
    "server": {
        "guid": "fbfb15e0-cc32-44f1-9239-195324d6be76",
        "entityType": "RestaurantUser",
        "externalId": null
    },
    "lastModifiedDevice": {
        "id": null
    },

    [contents omitted]

    "deliveryInfo": null,
    "serviceArea": null,
    "curbsidePickupInfo": {
        "guid": "0ca623cb-c1eb-4881-8222-67a393e00b5c",
        "entityType": "CurbsidePickup",
        "transportColor": "blue",
        "notes": "Convertible with top down",
        "transportDescription": "Street Cruiser"
    },
    "numberOfGuests": 1,
    "diningOption": {
        "guid": "162a8c8d-4ca9-4cf1-b1bd-88470cc0d928",
        "entityType": "DiningOption",
        "externalId": null
    },
    "openedDate": "2020-06-17T19:14:56.348+0000",
    "voidBusinessDate": null,
    "checks": [
        {
            "guid": "682b5aaf-d4e3-4e7b-ac53-f897ea5cad2d",
            "entityType": "Check",
            "externalId": null,
            "displayNumber": "3",
            "payments": [],
            "appliedDiscounts": [],
            "lastModifiedDevice": {
                "id": null
            },
            "voidDate": null,
            "paidDate": null,
            "appliedLoyaltyInfo": null,
            "voided": false,
            "paymentStatus": "OPEN",
            "amount": 15.98,
            "tabName": null,
            "taxExempt": false,
            "openedDate": "2020-06-17T19:14:56.348+0000",
            "totalAmount": 17.1,
            "selections": [
                {
                    [contents omitted]
                }
            ],
                [contents omitted]
            },
            "closedDate": null,
            "deletedDate": null,
            "modifiedDate": "2020-06-17T19:14:56.565+0000",
            "taxAmount": 1.12,
            "appliedServiceCharges": [],
            "customer": {
                "guid": "84f4ac23-e05b-46a9-99d9-16a2a8516bb8",
                "entityType": "Customer",
                "firstName": "Alice",
                "lastName": "Patron",
                "phone": "3335555555",
                "email": "alice@example.com"
            }
        }
    ],
    "deleted": false,
    "createdDevice": {
        "id": null
    },
    
    [contents omitted]
}
```



(1) The unique identifier that the Toast platform assigns to the order.

(2) Information about the mode of transportation that the guest will use when they arrive to pick up their order.

(3) The payment information is empty because the order request was made without a payments value. This means that the guest did not make any payments for this check.

(4) The date and time are null because the guest did not make a payment for the check.

(5) The total amount (including tax) of this check.

(6) Information about the guest who will pick up the order.

## Creating a delivery order

A delivery order uses a dining option where behavior is `DELIVERY`.

For delivery orders, in addition to the menu item selections, you must provide guest information and delivery information.

### Providing guest information for a delivery order

For a delivery order, the `Check` object must include a `customer` object that contains name and contact information for the guest.

In `customer`, the `firstName`, `lastName`, `phone`, and `email` fields are required.

### Providing delivery information for a delivery order

For a delivery order, the order object must include a `deliveryInfo` object that provides details about the address to deliver the order to.

In `deliveryInfo`, you must provide the `address1`, `city`, `state`, and `zipCode` fields. The `state` value must use the state abbreviation, not the state full name. For example, use `TX` instead of `Texas`.

You can also optionally use the `notes` value to provide notes for the delivery. For example, you can indicate where to leave the delivery or how to contact the guest when the delivery arrives.

### Example POST message body for a delivery order

The following example shows the message body for a `POST`request to the `/orders` endpoint to create a delivery order.


```
{
  "entityType": "Order",
  "diningOption": {
    "guid": "b1b10604-a8f9-4a21-ae86-7db974ee9dbf",
    "entityType": "DiningOption"
  },
  "deliveryInfo": {
    "address1": "401 Park Drive",
    "address2": "Suite 801",
    "city": "Boston",
    "state": "MA",
    "zipCode": "02215",
    "notes": "Send text message to 555-555-5555 when you arrive at the building."
  },
  "checks": [
    {
      "entityType": "Check",
      "selections": [
        {
          "entityType": "MenuItemSelection",
          "itemGroup": {
            "guid": "75cd1156-c33a-4842-9cbd-717aebbf069e",
            "entityType": "MenuGroup"
          },
          "item": {
            "entityType": "MenuItem",
            "guid": "2478cec3-bca2-4956-a3aa-eda571d5518a"
          },
          "quantity": 1,
          "modifiers": []
        }
      ],
      "customer": {
          "entityType": "Customer",
          "firstName": "Sarah",
          "lastName": "Gomez",
          "phone": "555-555-5555",
          "email": "sarah@example.com"
      }
    }
  ]
}
```



(1) The GUID of the dining option for the order. For a delivery dining option, behavior must be DELIVERY.

(2) The deliveryInfo object contains information about the address to deliver the order to. This information is required for delivery orders. The address1, city, state, and zipCode fields are required. The state value must use the state abbreviation instead of the state full name. For example, "TX" instead of "Texas".

(3) The customer object contains information about the guest who will receive the order. The customer object is required for delivery orders. The firstName, lastName, phone, and emailvalues are required. The data must be formatted correctly.

 In a customer object, the email value is the unique identifier for the guest. The email value must be unique for each individual guest.

### Example response to a delivery order POST request

When you use the orders API to create a delivery order, the response includes information about the order preparation and delivery.

The following example shows the message body for an endpoint response to a delivery order request.


```
{
  "guid": "4f0dbb70-46e8-4e02-bd22-9444cf9dc96b",
  "entityType": "Order",
  "externalId": null,
  "revenueCenter": null,
  "server": null,
  "deliveryInfo": {
    "address1": "401 Park Drive",
    "address2": "Suite 801",
    "city": "Boston",
    "state": "MA",
    "zipCode": "02215",
    "latitude": 42.3446671,
    "longitude": -71.1023575,
    "notes": "",
    "deliveredDate": null,
    "dispatchedDate": null,
    "deliveryEmployee": null
  },
  "serviceArea": null,
  "numberOfGuests": 1,
  "diningOption": {
    "guid": "b1b10604-a8f9-4a21-ae86-7db974ee9dbf",
    "entityType": "DiningOption",
    "externalId": null
  },
  "source": "API",
  "voidDate": null,
  "openedDate": "2017-10-04T19:31:34.480+0000",
  "duration": null,
  "businessDate": 20171004,
  "voidBusinessDate": null,
  "checks": [
    {
      "guid": "5a967d3f-b80a-41dc-8223-80665255dd9a",
      "entityType": "Check",
      "externalId": null,
      "displayNumber": "53",
      "amount": 9.99,
      "tabName": null,
      "taxExempt": false,
      "payments": [],
      "appliedDiscounts": [],
      "voidDate": null,
      "openedDate": "2017-10-04T19:31:34.482+0000",
      "totalAmount": 10.69,
      "selections": [
        {
          "guid": "25679951-23fa-4e29-a9e2-18b7f1c25cfb",
          "entityType": "MenuItemSelection",
          "externalId": null,
          "itemGroup": {
            "guid": "75cd1156-c33a-4842-9cbd-717aebbf069e",
            "entityType": "MenuGroup",
            "externalId": null
          },
          "deferred": false,
          "item": {
            "guid": "2478cec3-bca2-4956-a3aa-eda571d5518a",
            "entityType": "MenuItem",
            "externalId": null
          },
          "quantity": 1,
          "preDiscountPrice": 9.99,
          "voidReason": null,
          "optionGroup": null,
          "displayName": "Egg Sandwich",
          "appliedDiscounts": [],
          "tax": 0.7,
          "modifiers": [],
          "voidDate": null,
          "fulfillmentStatus": "NEW",
          "salesCategory": null,
          "selectionType": "NONE",
          "voidBusinessDate": null,
          "createdDate": "2017-10-04T19:31:34.510+0000",
          "preModifier": null,
          "price": 9.99,
          "modifiedDate": "2017-10-04T19:31:34.510+0000",
          "voided": false,
          "appliedTaxes": [
            {
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "92c6c470-74bb-4f84-b31f-2c144b70a285",
                "entityType": "TaxRate"
              },
              "name": "Local Tax",
              "rate": 0.0075,
              "taxAmount": 0.075,
              "type": "PERCENT"
            },
            {
              "entityType": "AppliedTaxRate",
              "taxRate": {
                "guid": "d5b88c05-1348-42ef-b1d3-577a83d70a80",
                "entityType": "TaxRate"
              },
              "name": "State Tax",
              "rate": 0.0625,
              "taxAmount": 0.625,
              "type": "PERCENT"
            }
          ]
        }
      ],
      "voidBusinessDate": null,
      "deleted": false,
      "paidDate": null,
      "closedDate": null,
      "deletedDate": null,
      "modifiedDate": "2017-10-04T19:31:34.547+0000",
      "appliedLoyaltyInfo": null,
      "voided": false,
      "taxAmount": 0.7,
      "appliedServiceCharges": [],
      "paymentStatus": "OPEN",
      "customer": {
        "guid": "479ad7e0-1942-42a5-874e-8cab3871190b",
        "entityType": "Customer",
        "firstName": "Sarah",
        "lastName": "Gomez",
        "phone": "5555555555",
        "email": "sarah@example.com"
      }
    }
  ],
  "deleted": false,
  "paidDate": null,
  "closedDate": null,
  "deletedDate": null,
  "restaurantService": null,
  "modifiedDate": "2017-10-04T19:31:34.549+0000",
  "promisedDate": null,
  "voided": false,
  "estimatedFulfillmentDate": "2017-10-04T20:31:34.480+0000",
  "table": null
}
```



(1) The unique identifier that the Toast platform assigns to the order.

(2) Information about the address to which the order will be delivered.

(3) The date and time that the delivery employee indicated that the order was delivered. The value is null because the order is not yet delivered.

(4) The date and time that the restaurant indicated that the order was available for delivery and assigned to a delivery employee. The value is null because the order is not yet available for delivery.

(5) The Toast GUID or external identifier of the delivery employee. The value is null because a delivery employee is not yet assigned to this order.

(6) The date and time that the order was created.

(7) A status indicating where the selection currently is in the preparation workflow. A status of NEW means that the menu item selection was added to a check but was not yet sent to the KDS (Kitchen Display System) for preparation.

(8) Any restaurant-configured service charges that applied to this check, such as a gratuity or a delivery fee. For information on service charges, see Service charges for checks.

(9) Information about the guest to whom the order will be delivered.

(10) The date and time that the order is expected to be ready to be delivered.

