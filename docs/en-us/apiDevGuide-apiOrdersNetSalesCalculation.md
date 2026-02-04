---
title: "Calculating net sales using the orders API"
id: apiOrdersNetSalesCalculation
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting order information"
previousSectionFile: apiDevGuide-apiOrdersGetDetailedInfoAboutMultipleOrders.md
previousSectionTitle: "Getting detailed information about multiple orders"
nextSectionFile: apiDevGuide-apiMarketplaceFacilitatorTaxInformation.md
nextSectionTitle: "Marketplace facilitator tax information"
externalReferences: [https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/]
excerpt: "The reports in Toast Web include net sales values. You can also use amount values from the orders API to calculate the net sales."
procedures: 0
codeExamples: 0
---

The reports in Toast Web include net sales values. You can also use [amount values from the orders API](apiOrdersOrderObjectSummary.html#apiOrderObjectAmounts) to calculate the net sales.

### Orders API information to include in net sales



> **Note**
> 
> The information in this section describes how your integration can calculate net sales using information that you get from the orders API. This section does not describe the behavior of the Toast POS or any reporting functions of the Toast platform.


A typical definition of net sales is the total price paid by guests for menu item selections and services.

Your integration can calculate net sales from orders API information by including:

- Prices of the menu item selections.


- Discounts that were deducted from menu item selections and checks.


- Non-gratuity service charges that were added to checks.



A typical calculation of net sales using orders API information does not include:

- Taxes or other amounts that are paid to other entities, such as gratuity service charges and credit card tips.


- Voided menu item selections, checks, and orders.


- Deleted checks and orders.


- Purchases of gift cards or house account payments.



Include the orders API information for any orders and checks *that are not excluded* in the list above. For example, include open and unpaid orders in the net sales calculation for your integration.

### How to calculate net sales from orders API information



> **Note**
> 
> The information in this section describes how your integration can calculate net sales using information that you get from the orders API. This section does not describe the behavior of the Toast POS or any reporting functions of the Toast platform.


Here is an overview of the process to calculate net sales for a group of orders using information from the orders API:

1. Use the [Get multiple orders](https://doc.toasttab.com/openapi/orders/operation/ordersBulkGet/) request to retrieve the orders that were opened during the period of time that you want to do the calculation for.


2. [Calculate the net sales values for each order](apiOrdersNetSalesCalculation.html#apiOrdersNetSalesSingleOrder).


3. Sum the order net sales values to get the total net sales.



During the calculation:

- Exclude orders and checks where `voided` is `true`.


- Exclude orders and checks where `deleted` is `true`.



**Procedure 2.1. To calculate net sales for an order**

1. Within a check, calculate the net sales amount for each menu item selection.

Exclude the following menu item selections:

- Menu item selections where `voided` is `true`.


- Menu item selections where `displayName` is `Gift Card`.



For the applicable menu item selections:

1. Get the `preDiscountPrice` value for the menu item selection.


2. Subtract the sum of `Discount.nonTaxableDiscountAmount`.




  1. Get the `preDiscountPrice` value for the menu item selection.


  2. Subtract the sum of `Discount.nonTaxableDiscountAmount`.


2. Sum the net sales amounts for the menu item selections in a check. This is the initial check net sales value.


3. Add the non-gratuity service charge amounts to the check net sales value.

1. In the check, sum `ServiceCharge.chargeAmount`.

Exclude service charges where `gratuity` is `true`.


2. Add that total to the check net sales value.




  1. In the check, sum `ServiceCharge.chargeAmount`.

Exclude service charges where `gratuity` is `true`.


  2. Add that total to the check net sales value.


4. Subtract check-level discounts from the check net sales value.

1. In the check, sum `Discount.nonTaxableDiscountAmount`.


2. Subtract that total from the check net sales value.




  1. In the check, sum `Discount.nonTaxableDiscountAmount`.


  2. Subtract that total from the check net sales value.


5. Sum the check net sales values for the checks in the order.



