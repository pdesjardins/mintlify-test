---
title: "Viewing refunds in Toast receipts, reports, and order details"
id: adminViewingRefundsInToastReports
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminRefundsOmitChunkFromSearchIndex.md
parentSectionTitle: "Refunds"
previousSectionFile: adminGuide-adminRefundedItemsInTheKitchen.md
previousSectionTitle: "Effect of refunds in the kitchen"
nextSectionFile: adminGuide-adminCashManagementOmitChunkFromSearchIndex.md
nextSectionTitle: "Cash management"
excerpt: "You can view refund information on receipts, in reports, and in order details."
keywords: ["viewing", "refunds", "toast", "receipts", "reports", "order", "details"]
procedures: 0
codeExamples: 0
---

You can view refund information on receipts, in reports, and in order details.

In reports, refunds affect the overall sales, tax, gratuity, and tip values. There are also specific entries for refunds.

## Viewing refunds on receipts

Refund information is printed at the bottom of the receipt.

The refund information includes:

- Refund date


- Refund items and amounts


- Refund total


- For refunds on items or the entire check, the payment that received the refund



## Net sales, tax, gratuity, and tip values

Refunds do not affect financial data on the day of the original order. Refunds only affect financial data on the day of the refund.

Refunds affect financial data in Toast reporting in the following ways:



****Net Sales****
: Net Sales figures decrease by the amount of the refund.

For item-level refunds, this includes both the total Net Sales and the Net Sales for sales categories, revenue centers, dining options, tax rates, discounts, service charges, service periods, and service areas.



****Tips****
: Refunded credit card tips decrease the Tips field by the refunded amount.

Refunds on gratuity service charges do not affect tip amounts in reports, because these charges are accounted for as part of the check total, not as part of the tip.



****Tax****
: Refunded tax amounts decrease the tax. This includes both the tax amount on refunded items and taxes that are refunded using the Tax only refund type.



****Gratuity service charges****
: Refunded gratuity service charges decrease the Gratuity figures.





The following example illustrates the effect of refunds on financial data.

A dine-in check from Lunch in the Main Dining Room on December 14 contains the following items, service charges, and tip.


<table>
  <thead>
    <tr>
      <th>Check item, service charge, or tip</th>
      <th>Price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Cheeseburger</td>
      <td>$6.50 ($5 price + $1.50 tax)</td>
    </tr>
    <tr>
      <td>Non-gratuity service fee</td>
      <td>$5.00</td>
    </tr>
    <tr>
      <td>Gratuity</td>
      <td>$2.00</td>
    </tr>
    <tr>
      <td>Tip</td>
      <td>$3.00</td>
    </tr>
  </tbody>
</table>

These were all refunded on December 15.

On December 15, the following figures decrease:


<table>
  <thead>
    <tr>
      <th>Finance value</th>
      <th>Decrease</th>
      <th>Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Total Net Sales</td>
      <td>-$10.00</td>
      <td>$5 Cheeseburger + $5 Non-Gratuity Service Fee</td>
    </tr>
    <tr>
      <td>Gratuity</td>
      <td>-$2.00</td>
      <td> </td>
    </tr>
    <tr>
      <td>Food Sales Category</td>
      <td>-$5.00</td>
      <td>Cheeseburger</td>
    </tr>
    <tr>
      <td>Tax</td>
      <td>-$1.50</td>
      <td> </td>
    </tr>
    <tr>
      <td>Tips</td>
      <td>-$3.00</td>
      <td> </td>
    </tr>
    <tr>
      <td>Dine In</td>
      <td>-$10.00</td>
      <td>$5 Cheeseburger + $5 Non-Gratuity Service Fee</td>
    </tr>
    <tr>
      <td>Revenue center for this check</td>
      <td>-$10.00</td>
      <td>$5 Cheeseburger + $5 Non-Gratuity Service Fee</td>
    </tr>
    <tr>
      <td>Lunch service period</td>
      <td>-$10.00</td>
      <td>$5 Cheeseburger + $5 Non-Gratuity Service Fee</td>
    </tr>
    <tr>
      <td>Main Dining Room service area</td>
      <td>-$10.00</td>
      <td>$5 Cheeseburger + $5 Non-Gratuity Service Fee</td>
    </tr>
  </tbody>
</table>

## Reports

Refunds are reported in the following reports.

### Sales summary

In the Reports &gt; Sales &gt; Sales summary report, refunds are reported as follows:

- Non-tip refund amounts appear in the Refunds column for each payment type.


- Refunded tip amounts are displayed in the Tips Refunded field.


- The Total column is equal to the sum of the Amount and Tipscolumns, minus the Refunds column.



![Excerpt from the Reports > Sales > Sales summary report.](https://doc.toasttab.com/doc/media/refunds-payment-summary.png)

A custom amount refund is shown as a unique line item in the Sales Category table, with a negative value in the Net Sales column. This ensures that the figures in this report add up to equal the total Net Sales amounts in other Toast reports.

Payments refunded using the custom amount refund type still appear in the Payments Summary table.

### Refunds report

In the Reports &gt; Cash and loss management &gt; Refunds report, on the Refunds tab, a line is shown for each payment that was refunded.

![Entry in the Reports > Cash and loss management > Refunds report.](https://doc.toasttab.com/doc/media/refunds-sales-exceptions-refunds.png)

If multiple payments were refunded during a refund transaction, a line is shown for each refunded payment.

This report includes the following details:

- Date and time of the refund


- Payment type


- Non-tip refund amount


- Tip refund amount


- The user who issued the refund


- The approver of the refund, if the user did not have the necessary permission


- The amount of the original payment


- Any comments that were entered at the time of the refund



### Accounting by day or location

Toast’s configurable GL Account report can be viewed in Reports &gt; Accounts &gt; Accounting by day or Reports &gt; Accounts &gt; Accounting by location.

To configure this report, use the Reports &gt; Accounts &gt; General Ledger Accounts settings. To ensure that all financial figures are represented in the Accounting report, all entities should be mapped to a GL account code. To add a GL account code, select Add GL Account.

![Add GL Account button.](https://doc.toasttab.com/doc/media/refunds-acctg-by-location-or-day-1.png)

To ensure that refunds do not cause an Over/Short amount in this report, map the following entities to a manually generated GL code.

- Credit Card Refunds


- Cash Refunds


- Custom Amount Refunds



Toast recommends that you create at least one GL code that is specific to refunds, and that you map this code to these entities. For example, you might create a GL Code called `Refunds`.​​

### Drawer history

In Reports &gt; Cash and loss management &gt; Drawer history, on the Cash Drawer Historytab:

- Cash refunds appear as a row under the Pay Out row. If no cash refunds are issued, this row does not appear.


- Cash refunds are subtracted from the Expected Closeout Cash on the day of the refund.



If a cash refund is issued on a device that is not associated with a cash drawer, then the refund is not included in a cash drawer report. There will be no record of the cash refund in your reports.

### Cash activity audit

On the day of the refund, each cash refund appears as an entry in Reports &gt; Cash and loss management &gt; Cash activity audit, on the Cash Activity Audit tab.

## Order details

The order details include the refunds associated with the order.

To view the details for an order:

1. On the home page, scroll to the Quick Action section.


2. Select Find a check & issue refund.


3. [Locate the check](adminGuide-adminIssuingARefund#adminToLocateACheckInToastAdminBackend).


4. Select the blue check number in the upper-left corner.

![Link to the order details for a selected check.](https://doc.toasttab.com/doc/media/refunds-order-details-1.png)



In the Items and Service Charges tables, if a menu item or service charge was refunded, the Refund Qty column contains the refunded quantity. The Refund column contains the amount of the refund.

In the Payments table, the amount refunded to a payment is displayed in the Refund column.

![Order details page with refund values.](https://doc.toasttab.com/doc/media/refunds-order-details-2.png)

## Custom amount refunds

Because custom amount refunds do not require the selection of items or service charges, they only affect the total Net Sales and Tip amounts in reports.

Custom amount refunds do not affect the following:

- Revenue centers


- Dining options


- Tax rates


- Discounts


- Service periods


- Service areas



A custom refund is shown as a unique line item in the Sales Category table of the Reports &gt; Sales &gt; Sales summary report, with a negative value in the Net Sales column. This ensures that the figures in this report add up to equal the total Net Salesamounts in other Toast reports.

![Sales Category table that contains an entry for custom amount refunds.](https://doc.toasttab.com/doc/media/refunds-reports-and-custom-amt-refunds.png)

Payments that are refunded using the custom amount refund type still appear in the [Payments Summary](adminGuide-adminViewingRefundsInToastReports#adminSalesSummaryPaymentsSummary)table.

Finally, when you refund a custom amount, you also specify whether to also refund any portion of the check's tip. If you refund the tip when you refund a custom amount, then tip amounts in reports also decrease.

