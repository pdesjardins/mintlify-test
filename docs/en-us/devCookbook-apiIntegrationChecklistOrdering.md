---
title: "Building an online ordering integration"
id: apiIntegrationChecklistOrdering
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookOrderingOmitChunkFromSearchIndex.md
parentSectionTitle: "Ordering"
previousSectionFile: devCookbook-cookbookOrderingOmitChunkFromSearchIndex.md
previousSectionTitle: "Ordering"
nextSectionFile: devCookbook-apiBuildingDigitalSignage.md
nextSectionTitle: "Building a digital menu signage integration"
externalReferences: [https://doc.toasttab.com/openapi/configuration/overview/, https://doc.toasttab.com/openapi/packaging/overview/, https://central.toasttab.com/s/article/86-an-Item, https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/, https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/]
excerpt: "Follow the steps below to build an online ordering integration with the Toast platform."
procedures: 0
codeExamples: 0
---

Follow the steps below to build an online ordering integration with the Toast platform.

After you complete and test these steps, you can complete an end-to-end test of your integration functionality.

## Required scopes

To follow these instructions, you must have the following [scopes](apiDevGuide-apiScopes):

- `config:read`


- `credit_cards.authorization:write`


- `digital_schedule:read`


- `menus.channel:read`


- `orders.delivery_info:write`


- `orders.orders:write`


- `packaging:read`


- `restaurants:read`


- `stock:read`



## Initial setup and testing

### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](devCookbook-apiIntegrationChecklistGeneral).

### Learn menu hierarchy concepts

To familiarize yourself with restaurants' menu structure, read the [menu hierarchy documentation](adminGuide-adminMenuHierarchy).

Then use the [menus API](apiDevGuide-apiMenusApiReturnsFullyResolvedJson_V2) to retrieve the full menu from a test location so that you understand the menu structure.

Review [menu hierarchy](adminGuide-adminUnderstandingTheMenuHierarchy)information before you begin development related to menus.

### Retrieve configuration components

Use the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/) to retrieve the configuration you will need to place successful orders. Configuration options you may need include:

- Dining options


- Discounts


- Revenue centers


- Service charges


- Tax rates


- Alternative payment types



Use the [packaging configuration API](https://doc.toasttab.com/openapi/packaging/overview/) to retrieve the packaging preference configurations you need for takeout or delivery orders.

### Place a test order

To learn how Toast platform orders are structured, place an order using [example API requests](apiDevGuide-apiExampleRequests).

To place a successful test order, you will need to retrieve an authentication token and replace the entity identifiers in the test order with entity identifiers at your test restaurant. You use the configuration and menu APIs to retrieve these identifiers.

## Functionality planning

### Determine how you will use free-text fields

You can set check tab names and display numbers in the way you choose.

Toast support recommends using these fields in the following ways:

- Use the following **tab name**structure: “Your company name - order number”, where “order number” represents the order number in your own system.


- Do not include a custom **display number** when you submit orders. This way, the Toast platform automatically sets the check number to the integer that follows the previous check number.


- To provide the ability to include **order-level notes**, submit a special request as an item selection on an order. For example, guests might use this selection to request specific packaging.



### Decide which menu item pricing strategies you will support

Most Toast Online Ordering integrations support [base price](adminGuide-adminBasePrice), [menu-specific pricing](adminGuide-adminMenuSpecificPrice), and [size pricing](adminGuide-adminSizePrice).

Supporting [time-specific pricing](adminGuide-adminTimeSpecificPrice) is recommended and will be a differentiator for your integration.

### Decide which modifier group pricing strategies you will support

In addition to the menu item pricing strategies described above, modifier groups can also use [sequence pricing](adminGuide-adminSequencePrice) and [size/sequence pricing](adminGuide-adminSizeSequencePrice).

Using these pricing strategies is a recommended differentiator for your online ordering integration.

## Voiding an order

You can void an order using the orders API `void`endpoint. For more information, see [Void an order](apiDevGuide-apiVoidOrder).

## Menu display

### Build your menu display

Your menu should display at least:

- Menu entity names, at all levels of the menu hierarchy


- Item descriptions


- Item images


- Prices



Displaying item tags is recommended and optional. Common item tags include “gluten free” and “vegetarian”.

For more information about the menus API, see the [reference documentation](apiDevGuide-apiGettingMenuInformationFromTheMenusAPI).



> **Important**
> 
> Ordering partner integrations should use version 3, not version 2, of the menus API.


Be sure your menu display allows:

- Multiple menus


- Multiple menu groups within a menu


- Subgroups within menu groups


- Menu items shared by multiple groups



### Only display a menu while it is configured to be available

Restaurants can configure menus to only be available at certain times of day, such as a brunch or happy hour menu.

Your integration should only display menus when their corresponding `Availability` object in the `/menus` endpoint of the [menus API](apiDevGuide-apiGettingMenuInformationFromTheMenusAPI)says that they should be visible.

Consider [daylight savings time](apiDevGuide-api_dates_and_timestamps#apiDaylightSavingsTime) when building menu display times.

### Update menus on a near-real-time basis

The [menus webhook](apiDevGuide-apiMenusWebhook) and the `/metadata` endpoint of the menus API tells you the timestamp of the most recent change to a restaurant's published menu.

If you do not use the menus webhook, your integration should poll the `/metadata` endpoint once every 1-5 minutes and retrieve new menu information if and only if the webhook or `/metadata` endpoint says that the menu has changed since you last retrieved it.

For more information about menu syncing, see [Determining if a restaurant's menu data has gone stale](apiDevGuide-apiDeterminingIfYourMenuJsonIsOutdated_V2).

### Avoid infinite loops when parsing menus

There is a rare but possible menu configuration that can send your integration into an infinite loop when parsing a restaurant menu.

To avoid this problem, see [Detecting and avoiding infinite loops in the menus API JSON](apiDevGuide-apiDetectingAndAvoidingInfiniteLoopsInTheMenusApiJson).

## Handling out of stock Items (86'ing)

### Display item stock information

Your menu display should prevent guests from ordering items that are out of stock. Use the [stock webhook](apiDevGuide-apiUsingTheStockWebhook) to receive real-time notifications about item stock updates.

Fall back to the [stock API](apiDevGuide-apiUsingTheStockApi) if you miss a webhook update. 

See [this Toast Central article](https://central.toasttab.com/s/article/86-an-Item) for information about how to test out of stock items.

## Handling dining option behavior

### Review dining option behaviors

The behavior value on a dining option controls the order data that you are required to submit.

For more information about dining option behaviors, see [Types of dining options](apiDevGuide-apiOrderTypeDetails#apiOrdersDiningOptionTypes).

### Build dine-in order interface

When a guest submits a dine-in order, you must include a table with the order.

For more information about submitting dine-in orders, see [Creating a dine-in order](apiDevGuide-apiOrderTypeDetails#apiOrdersCreateDinein).

#### Providing table information for a dine-in order

To include table information for a dine-in order, see [Providing table information for a dine-in order](apiDevGuide-apiOrderTypeDetails#apiOrdersCreateDineinTable).

#### Adding items to existing checks

If your integration allows guests to add items to existing checks, see [Adding items to an existing check](apiDevGuide-apiAddingItemsToACheck).

#### Prevent guests from leaving the restaurant without paying for their meal

You are responsible for implementing functionality to ensure guests do not leave the restaurant without paying for their meal. For example, you could require payment at the time the order is placed.

### Build takeout order interface

When a guest submits a takeout order, you must submit the guest name, phone number, and email address with the order.

For more information about submitting takeout orders, see [Creating a takeout order](apiDevGuide-apiOrderTypeDetails#apiOrdersCreateTakeout).

### Build curbside pickup order interface

When a guest submits a curbside pickup order, you must submit the guest name, phone number, and email address with the order, as well as information about the guest’s mode of transport.

For more information about submitting curbside pickup orders, see [Creating a curbside pickup order](apiDevGuide-apiOrderTypeDetails#apiOrdersCreateCurbside).

### Build delivery order interface

When a guest submits a delivery order, you must submit the guest name, phone number, email address, and delivery address with the order.

For more information about submitting delivery orders, see [Creating a delivery order](apiDevGuide-apiOrderTypeDetails#apiOrdersCreatingDelivery).

### Validate guest information format

Guest phone numbers must contain ten numeric digits.

Guest email addresses must be unique per individual guest and must contain an at-sign (`@`) and a period (`.`).

## Handling modifiers

### Handle default modifiers

The `isDefault` boolean value on modifier options indicates whether or not a modifier option is included with its parent menu item by default. If a modifier option is a default modifier on its parent item, your integration should display it by default and guests should have the option to remove it.

For example, a hamburger menu item may include lettuce or tomato modifier options by default, but guests may want to remove one or both of these default options.

### Handle minimum and maximum selection options

Modifier groups have `minSelection` and `maxSelection` values that describe the minimum and maximum number of selections a guest may make from a modifier group.

Your ordering integration must enforce these values.

### Handle duplicate selections from a modifier group

The `allowsDuplicates` boolean value on a modifier group indicates whether a guest can select the same option from a modifier group multiple times on the same menu item selection.

For example, if `allowsDuplicates` is `true`for a pepperoni modifier option on a pizza menu item, a guest may add two servings of pepperoni to their pizza. If `allowsDuplicates` is `false`, the guest may only add one serving of pepperoni to their pizza.

See [Requirements for modifier quantities](apiDevGuide-apiSpecifyingModifiersAndInstructions#requirementsforModifierQuantities) for information about how to apply multiple quantities of the same modifier option on a menu item selection.

### Handle nested modifiers

Restaurant employees can nest modifiers as deeply as they want in a menu. For example, a “burger” menu item may have an “add-ons” modifier group, which includes a modifier option of “cheese.” The “cheese” modifier option may include its own modifier group of “cheese type,” which contains modifier options of “American” and “Swiss.”

Your integration should be able to handle at least three layers of nested modifiers, meaning an item and three layers of modifiers.

### Handle pre-modifiers

Modifier groups can have associated pre-modifiers. Common examples of pre-modifiers include “no,” “light,” “extra,” or “on the side.”

As a differentiator, it is beneficial for your integration to allow guests to include pre-modifiers in the ordering process.

### Handle special requests

Orders can have free-text special requests on menu items and modifiers.

To add special request functionality to your ordering integration, see [Special requests and instructions](apiDevGuide-apiSpecifyingModifiersAndInstructions#apiOrderSpecialInstructions).

## Handling packaging preferences

### Review packaging preferences

Packaging preferences configured by restaurants indicate options for packaging takeout and delivery orders, such as utensils, napkins, or straws. Your integration is responsible for reviewing the available packaging preferences from the packaging configuration API and including guest-selected options when submitting orders. For more information on available packaging preferences, see [Getting packaging preference configuration options](apiDevGuide-apiOrdersPackagingPreferences#apiOrdersPackagingPreferencesGetGuid).

### Build packaging preferences functionality

Your ordering interface should include packaging preference options for takeout and delivery orders. For more information about including packaging preferences in guest orders, see [Creating an order with packaging preferences](apiDevGuide-apiOrdersPackagingPreferences#apiOrdersPackagingPreferencesUsingTheOrdersApi).

## Order timing

When developing functionality related to order timing, review the [Daylight Savings Time](apiDevGuide-api_dates_and_timestamps#apiDaylightSavingsTime) documentation.

### Display restaurant hours

Use the [`/orderingSchedule`endpoint](apiDevGuide-apiGettingOnlineOrderingSchedules) to retrieve a restaurant location’s hours of operation.

Display these hours on the restaurant's ordering site.

Use these hours to control the times at which you submit orders. You are responsible for preventing order submission while the restaurant is closed. The orders API does not enforce restaurant hours.

### Build future order functionality

If your integration will support future order submission (for example, placing a catering order on Monday to be fulfilled on Friday), review the instructions in [Scheduling future orders](apiDevGuide-orders_api_future_orders).

In particular, ensure that the `openedDate` and `promisedDate` on a future order match one another and are both the expected time of order fulfillment.

Use the [order management configuration API](apiDevGuide-apiGettingOnlineOrderingSchedules) to determine whether a restaurant accepts future orders and the number of days in the future that guests may schedule orders.

Also be sure to accommodate [daylight savings time](apiDevGuide-api_dates_and_timestamps#apiDaylightSavingsTime) when building future order submission functionality.

## Pricing

### Charge prices calculated by the Toast platform

Before you charge a guest for an order, call the `/prices` endpoint of the orders API to get the price of each item selection calculated by the Toast platform.

For an order to arrive fully paid, the payment you submit must match the Toast platform price for the item selection, including taxes. It is critical that you charge the order and tax price returned in the `/prices` endpoint.

For more information, see [Getting check prices before you submit an order](apiDevGuide-apiOrderPrices#apiGettingCheckPrices).

### Display correct prices in your interface

The Toast platform has many pricing strategies. You need to display accurate prices to guests.

For more information about the Toast platform’s more complex pricing strategies, see [Using PricingRules and PricingStrategy to calculate prices](apiDevGuide-apiUsingPricingRulesAndPricingStrategyToCalculatePrices_V2).

### Calculate taxes

The `/prices` endpoint of the orders API provides the taxes associated with an order.

To calculate taxes yourself for display purposes, use [these instructions](apiDevGuide-apiOrderPrices#apiTaxRounding).

### Handle discounts

The `isDiscountable` value on `MenuItem`objects in the [menus API](apiDevGuide-apiGettingMenuInformationFromTheMenusAPI)indicates whether or not an item can be discounted. Do not allow guests to apply discounts to menu items that have an `isDiscountable` value of `false`.

If your integration will allow guests to use discounts, see [Applying discounts to a new order](apiDevGuide-apiDiscountingOrders#apiApplyingDiscount) for more information.

### Service charges

Restaurants may add service charges to orders. Examples of service charges include delivery fees and automatic gratuities.

For more information about adding services charges, see [Service charges for checks](apiDevGuide-apiOrderPrices#apiServiceCharges).

## Payments

### Encrypt card data

This step only applies to ordering integrations that use the Toast credit cards API.

Before you submit an authorization request, you must create an encrypted card data string using the credit card encryption key that Toast support provides.

For more information about encrypting card data, see [Encrypting credit card information](apiDevGuide-authorizingCcPayments#apiEncryptingCreditCardInformation).

### Authorize credit cards

This step only applies to ordering integrations that use the Toast credit cards API.

After you create an encrypted card data string, you submit the string in a credit card authorization request with the other required metadata.

For more information about credit card authorization, see [Authorizing a credit card payment](apiDevGuide-authorizingCcPayments#apiAuthorizingACreditCardPayment).

### Distinguish between new and saved cards

This step only applies to ordering integrations that use the Toast credit cards API.

The `cardNumberOrigin` value on credit card authorization requests must distinguish between new and saved credit cards.

When a guest pays by manually entering credit card information, `cardNumberOrigin` should be `END_USER`.

When a guest pays with a credit card using saved information that is stored in an external vaulting service, `cardNumberOrigin`should be `PARTNER_VAULT`.

For more information, see [Optimizing fraud detection](apiDevGuide-authorizingCcPayments#apiCreditCardsOptimizingFraudDetection).

### Submit payments

If you use the Toast credit cards API, you should submit the payment you authorized using [these instructions](apiDevGuide-authorizingCcPayments#apiApplyingCCPaymentToOrder).

If you do not use the Toast credit cards API, you submit payments using [alternative payment types](apiDevGuide-apiCreatingAnOrderWithPaymentInformation). A restaurant's alternative payment types can be found in the [configuration API](https://doc.toasttab.com/openapi/configuration/operation/alternatePaymentTypesGet/).

### Submit tips

To submit tips, populate the `tipAmount` value on your [payment authorization](apiDevGuide-authorizingCcPayments#apiAuthorizingACreditCardPayment).

Include a `tipAmount` on the payment that you submit with an order.

### Document your refund workflow

If you use the Toast credit cards API, servers can refund guests using the Toast POS.

If you do not use the credit cards API, servers must separately refund guests out of the Toast POS and your credit card processing system.

In either case, you need to explain how to process refunds for restaurant employees.

## Delivery dispatch

### Update delivery status over time

If your online ordering application supports delivery orders, and your organization manages the employees who deliver them, you can update the orders' delivery information when that information becomes available.

You can update the order's delivery status, dispatch and delivery timestamps, and assigned delivery employee.

For more information, see [Updating delivery information for an order](apiDevGuide-apiUpdatingDeliveryInfoForAnOrder).

## Reporting

### Submit revenue centers

To make it easier for restaurants to report on which orders came from your integration, submit revenue centers on your orders.

You can retrieve revenue centers from the [configuration API](https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/). Follow these [instructions for adding revenue centers to orders](apiDevGuide-apiOrdersRevenueCenters).

## Configuration syncing

### Sync configuration regularly

After your integration goes live, restaurants may add, change, or remove configuration such as dining options and revenue centers.

Your integration should check the configuration information that is available from the [configuration API](https://doc.toasttab.com/openapi/configuration/overview/). If a restaurant has deleted any configurations your integration relies on, your integration should alert your organization.

