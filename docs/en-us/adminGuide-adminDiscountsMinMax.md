---
title: "Configuring required minimum and maximum check totals"
id: adminDiscountsMinMax
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountsOverallAvailabilityOmitChunkFromSearchIndex.md
parentSectionTitle: "Configuring discount availability and status"
previousSectionFile: adminGuide-adminDiscountAvailability.md
previousSectionTitle: "Setting the availability date range for a discount"
nextSectionFile: adminGuide-adminDiscountsActiveInactive.md
nextSectionTitle: "Making a discount active or inactive"
excerpt: "You can configure..."
keywords: [configuring,required,minimum,maximum,check,totals]
procedures: 1
codeExamples: 0
---

### Configuring required minimum and maximum check totals

You can configure minimum and maximum check total thresholds for any type of discount. These thresholds determine if a discount can be applied to a check, based on the pre-tax check total. The check must also meet any other eligibility criteria for the discount.

For example, you can specify that a BOGO discount can be applied to a check only if the pre-tax check total is less than $25.00. If the check total is more than $25.00, the BOGO discount cannot be applied, even if the items on the check would otherwise satisfy the requirements of the discount.

The pre-tax check total is the sum of item prices in the Total column on the check (not in the Balance Due field). In the following example, the pre-tax item prices (outlined in red) total $28.96.

![Toast POS screen that shows an order with the Total column highlighted.](https://doc.toasttab.com/doc/media/discount-min-max-example.png)

To configure the check total criteria, you use the Required Min/Max Check Amount setting in the Advanced Settings section of the discount configuration page.

![Required Min/Max Check Amount fields.](https://doc.toasttab.com/doc/media/discount-min-max.png)

You can specify only a minimum value, only a maximum value, or both a minimum and a maximum value.

**Procedure 9.7. To configure minimum and maximum check totals for a discount**

1. In the Min Value ($) field, enter the minimum currency value for an eligible check total. A check is only eligible for the discount if the check total is greater than this amount.

If you do not specify a minimum value, then there is no required minimum for the check total.


2. In the Max Value ($) field, enter the maximum currency value for an eligible check total. A check is only eligible for the discount if the check total is less than this amount.

If you do not specify a maximum value, then there is no required maximum for the check total.



