---
title: "Marketplace facilitator tax payments"
id: adminMarketplaceFacilitatorTaxPayments
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminTaxesOmitChunkFromSearchIndex.md
parentSectionTitle: "Taxes"
previousSectionFile: adminGuide-adminSmartTax.md
previousSectionTitle: "Smart tax"
nextSectionFile: adminGuide-adminReceiptSetup.md
nextSectionTitle: "Configuring customer printed receipts"
excerpt: "For Toast restaurants, a marketplace facilitator is a business that:"
procedures: 0
codeExamples: 0
---



> **Note**
> 
> The Toast platform functionality described in this section is in
    limited release.


For Toast restaurants, a marketplace facilitator is a business
  that:

- Takes guest orders, processes guest payments, and then directly
      submits those orders to a Toast restaurant for fulfillment.


- Is required by a taxing authority to pay tax amounts for the
      orders they process.



For example, a restaurant ordering service like the Local by Toast
  app, Toast Local, Grubhub™, Uber
  Eats™, or DoorDash® that
  accepts orders for a large number of restaurants might take guest orders and
  payments and then submit the order to the Toast platform for fulfillment at
  a Toast restaurant. The ordering service receives the guest payment and then
  remits the applicable tax amounts.

A marketplace facilitator might not remit all tax amounts for a Toast
  platform order. For example, a marketplace facilitator might remit all state
  tax amounts but not remit local tax amounts. You can determine whether a
  marketplace facilitator has remitted tax amounts for your restaurant's
  orders by checking the tax information in Toast platform reports. For more
  information, see [Tax payment reporting information](adminGuide-adminMarketplaceFacilitatorTaxPayments#adminMpfTaxPaymentReportingInformation). Marketplace
  facilitators might calculate tax amounts differently than the Toast platform
  does.



> **Important**
> 
> The tax remittance and tax amount reporting information in the Toast
    platform is not intended to be guidance for complying with tax
    requirements. Seek qualified tax guidance if you need assistance.


The marketplace facilitator tax amount behavior described in this
  section only applies to orders that are *directly
  submitted* from the marketplace facilitator to the Toast platform.
  Your restaurant might receive orders that originated at a marketplace
  facilitator but then passed through another order handling service before
  being digitally submitted to the Toast platform. For example, if your Toast
  platform restaurant uses a direct integration with a marketplace facilitator
  ordering partner, the orders you receive through that integration are
  included in marketplace facilitator tax amount handling and reporting.
  Orders you receive *indirectly* from a marketplace
  facilitator, through a different ordering service, *are*
  included in reporting using tax rates configured in the Toast platform and
  *are not* included in marketplace facilitator
  reporting.

If your restaurant uses a Toast API integration that gets information
  about orders, the order information that you get from Toast APIs includes
  information about tax amounts remitted on behalf of your restaurant. For
  more information, see [Marketplace facilitator tax information](apiDevGuide-apiMarketplaceFacilitatorTaxInformation).

The following sections provide more information about marketplace
  facilitator tax payments:

- [Tax payment reporting information](adminGuide-adminMarketplaceFacilitatorTaxPayments#adminMpfTaxPaymentReportingInformation)


- [Tax amounts are aggregated for all items and checks](adminGuide-adminMarketplaceFacilitatorTaxPayments#adminMpfTaxAmountsAggregated)


- [Marketplace facilitator orders are protected from changes](adminGuide-adminMarketplaceFacilitatorTaxPayments#adminMpfOrdersProtectedFromChanges)



## Tax payment reporting information

You can see the tax amount that a marketplace facilitator remitted
    for an order in the Toast platform reporting information for your
    restaurant.

The tax amount information for those orders is presented in
    categories that indicate whether the marketplace facilitator has remitted
    the tax amounts for a guest payment on behalf of your restaurant or has
    not remitted those tax amounts.

**Marketplace facilitator tax information reporting
      categories**

- Marketplace Facilitator Taxes Paid - tax
        amounts for which the marketplace facilitator *has*
        remitted tax payments on behalf of your restaurant


- Toast Marketplace Facilitator Taxes Paid -
        tax amounts for which Toast *has* remitted tax
        payments for your restaurant. For Local by Toast app and Toast Local
        orders only.


- Marketplace Facilitator Taxes Not Paid -
        tax amounts for which the marketplace facilitator *has
        not* remitted tax payments on behalf of your
        restaurant.

You will only see tax amounts categorized as
        Marketplace Facilitator Taxes Not Paid if the
        following conditions are met:

- Your restaurant location is in a taxing jurisdiction that
            only requires marketplace facilitators to remit the taxes for that
            jurisdiction and not taxes for other jurisdictions (for example
            local or municipal taxes).


- The marketplace facilitator organization chooses to remit
            *only the taxes that are required* by the
            marketplace facilitator laws for the taxing jurisdiction. Some
            marketplace facilitators might choose to remit all taxes, even if
            they are not required to do that.



For information about how a marketplace facilitator organization
        remits tax amounts in a specific taxing jurisdiction, contact that
        marketplace facilitator directly.



Marketplace facilitator tax payment information is available in the
    following reporting resources.

- The tax table section of the Sales Summary
        report. Choose Reports > Sales > Sales
        summary to open the Sales Summary
        report tab.


- The Taxes table of the Accounting
        Overview report. Choose Reports > Accounts
        > Accounting overview to open the Accounting
        Overview report.



The following diagram shows marketplace facilitator tax amounts in
    the Sales Summary report.



> **Note**
> 
> Toast Marketplace Facilitator Taxes Paid only appear in the
      Sales Summary report. For a cumulative total of all
      Marketplace Facilitator Taxes Paid, see the Accounting
      Overview report.


![Marketplace facilitator order tax amounts appear in Toast platform reporting information.](https://doc.toasttab.com/doc/media/marketplace-facilitator-tax-amount-reporting.png)



> **Note**
> 
> Toast platform reporting information includes many aggregated tax
      calculations that are not broken down by marketplace facilitator tax
      payment categories. This excludes Local by Toast and Toast Local which
      can be found in the Sales Summary Report.
      Aggregated tax amount calculations other than the ones described in this
      section include *both paid and unpaid* marketplace
      facilitator tax amounts.


### Calculating tax amounts

To calculate the amounts used for taxes, refer to the orders API
      `AppliedTaxRate` object. For more information about this
      object and how it applies to marketplace facilitators, see [Reviewing marketplace facilitator tax calculations](apiDevGuide-apiMarketplaceFacilitatorTaxInformation#apiOrdersGetMarketplaceFacilitatorCalculateTax).

For instructions on how to calculate the total
      marketplace facilitator tax paid for an order, see [Calculating total marketplace facilitator tax paid](apiDevGuide-apiMarketplaceFacilitatorTaxInformation#apiOrdersGetMarketplaceFacilitatorCalculateTotalTaxPaid).

## Tax amounts are aggregated for all items and checks

The tax amounts for marketplace facilitator orders are aggregated
    for each guest check in an order. Tax amounts that apply to specific items
    in an order are not reported separately from other items. For example, if
    an item in an order is subject to an alcoholic beverage tax, that tax
    amount is aggregated with the other tax amounts for the order in Toast
    platform reporting information.

Marketplace facilitators report the tax amounts for each order when
    they submit the orders to the Toast platform. The Toast platform divides
    the sum of all tax amounts proportionately by item price among all items
    in all checks in an order.

The following diagram shows the tax amount aggregation for a
    marketplace facilitator order that includes items that are taxed at
    different rates. In this example the item prices are all equal.

![Marketplace facilitator orders sum the tax amounts for all items in all checks and then divide the total tax amount proportionately by item price among all items when the data is stored in the Toast platform. This includes item types that are taxed at different rates.](https://doc.toasttab.com/doc/media/marketplace-facilitator-tax-aggregation.png)

## Marketplace facilitator orders are protected from changes

When your Toast restaurant receives an order from a marketplace
    facilitator, you cannot make changes to the order. The Toast platform
    protects marketplace facilitator orders from changes because those orders
    match information that originated in the marketplace facilitator
    transaction.

You cannot refund a marketplace facilitator order. The marketplace
    facilitator who processed the original order and received the guest's
    payment must refund the guest.



> **Note**
> 
> Orders that originate from the Local by Toast app and Toast Local
      can be changed and refunded.


