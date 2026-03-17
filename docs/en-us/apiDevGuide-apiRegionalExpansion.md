---
title: "Technical considerations for regional expansion"
id: apiRegionalExpansion
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-ifYoureAnIntegrationPartnerOmitChunkFromSearchIndex.md
parentSectionTitle: "If you're an integration partner"
previousSectionFile: apiDevGuide-apiEnvironments.md
previousSectionTitle: "Environments"
nextSectionFile: apiDevGuide-ifYoureACustomIntegrationDeveloperOmitChunkFromSearchIndex.md
nextSectionTitle: "If you're a custom integration developer"
externalReferences: [https://doc.toasttab.com/openapi/restaurants/operation/restaurantsRestaurantGuidGet/, https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/labor/tag/Data-definitions/schema/Employee/]
excerpt: "You will use the same Toast API endpoints across regions, but certain configurations and fields may vary. When offering your..."
procedures: 0
codeExamples: 0
---

You will use the same Toast API endpoints across regions, but certain configurations and fields may vary. When offering your integration to new regions, use the guidance below to ensure your integration functions correctly.



> **Note**
> 
> Toast operates in Australia, Canada, Ireland, the United Kingdom, and the United States. Other locations may be added at a later time.


## Restaurants

To view restaurant location configuration information, send a `GET` request to the `[/restaurants](https://doc.toasttab.com/openapi/restaurants/operation/restaurantsRestaurantGuidGet/)`endpoint of the restaurants API. The following values change depending on the geographic region of a location:

- In the `Location` object, the `administrativeArea` value is the name of the geographical region of the location.


- In the `General` object, the `currencyCode `value is the ISO-4217 currency code used at the location. Any monetary value returned from any Toast API will use the `currencyCode`.



## Orders

When submitting orders to the [orders API](https://doc.toasttab.com/openapi/orders/overview/), consider regional variations in formatting.

- If you include guest information when you create orders using the orders API, include a `phoneCountryCode` value in the `Customer` object for non-US phone numbers.


- When updating the `DeliveryInfo` object in the orders API, use the guidance in the [Orders developer guide](apiDevGuide-apiUpdatingDeliveryInfoForAnOrder) to determine whether to use the `state` or `administrativeArea` value.



## Payments

The Toast platform cannot process credit card payments in regions outside of the United States. Instead, use an [alternative payment type](apiDevGuide-apiCreatingAnOrderWithPaymentInformation) when placing an order using the orders API.

## Labor

When adding or updating employee phone number information in the labor API, ensure that the `[phoneNumberCountryCode](https://doc.toasttab.com/openapi/labor/tag/Data-definitions/schema/Employee/)`value is accurate for the region of the employee's location.

## Outbound integrations

If you have a loyalty integration, ensure that your integration can accept the appropriate phone number length for [`LOYALTY_SEARCH`](apiDevGuide-apiLoyaltyTransactionDescriptions)transactions.

