---
title: "Service charge calculations"
id: adminServiceChargeCalculation
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminServiceChargesOmitChunkFromSearchIndex.md
parentSectionTitle: "Service charges"
previousSectionFile: adminGuide-adminServiceChargeEligibility.md
previousSectionTitle: "Service charge eligibility"
nextSectionFile: adminGuide-adminServiceChargeCreate.md
nextSectionTitle: "Configuring service charges"
excerpt: "Before a service charge can be automatically applied to a check, the Toast platform has to make a variety of calculations, including the following:"
keywords: ["service", "charge", "calculations"]
procedures: 0
codeExamples: 0
---

Before a service charge can be automatically applied to a check, the Toast platform has to make a variety of calculations, including the following:

- Calculate whether the service charge is eligible to be automatically applied to a check. See [Service charge eligibility](adminGuide-adminServiceChargeEligibility). Keep in mind that you can manually apply a service charge to a check.


- Calculate how the application of discounts affects the service charge fee. See [Post-discount and pre-discount calculations](adminGuide-adminServiceChargeCalculation#adminPostDiscount).


- For fixed percent service charges, calculate the monetary amount of the service charge fee by multiplying the check amount by the Charge Percent field of the service charge.


- Calculate the tax on the service charge (if it is configured for taxation). See [Service charge taxes](adminGuide-adminServiceChargeCalculation#adminServiceChargeTaxes).



## Post-discount and pre-discount calculations

A fixed percent service charge calculates the service charge amount based on the pre-discount or post-discount check total amount, depending on the configuration of the Calculated on pre-discount or post-discount total option. The following example shows how each configuration affects the check's final total amount.

Service charge and check example:


```
Check total before service charge and discount are applied = $10.00
Discount = $2.00 OFF
Service charge percent amount: 10%
Apply After Amount threshold: $10.00
```

For this example, the calculations for pre-discount and post-discount configurations are as follows:

**Procedure 6.16. Service charge configuration = Pre-discount Total**

1. Calculate the service charge on the pre-discount check total: $10.00 * 10% = $1.00


2. Add the service charge of $1.00 to the check total: $10.00 + $1.00 = $11.00


3. Deduct the $2.00 discount from the adjusted check total: $11.00 - $2.00 = $9.00 (final check total)



**Procedure 6.17. Service charge configuration = Post-discount Total**

1. Deduct the $2.00 discount from the check total: $10.00 - $2.00 = $8.00


2. Calculate the service charge on the post-discount adjusted check total: $8.00 * 10% = $0.80


3. Add the service charge of $0.80 to the check total: $8.00 + $0.80 = $8.80 (final check total)



Note that the service charge is applied in both cases because the Apply After Amount Threshold ($10.00 in this example) is always evaluated against the check amount *before* any discounts have been applied (therefore, the check amount is $10.00 in both cases).

## Service charge taxes

You can optionally configure a service charge to be taxed, using one or more of your existing tax rates. The following example of a service charge configuration page shows that the Taxed option is set to Yesand the Applicable Taxes option (in the Taxes section) is using the `State Tax` rate of 9% for the service charge:

![The Taxes configuration option for a service charge.](https://doc.toasttab.com/doc/media/taxes-service-charges-taxed.png)

When the tax is calculated on the service charge amount, the service charge tax amount is added to the check's tax amount (that is, it is included in the Tax field on the payment screen). The following two tax calculation examples show how a service charge tax is calculated depending on whether the service charge has one or two applicable tax rates.

**Procedure 6.18. Tax calculation example for one tax rate**

If the service charge has one applicable tax rate, the tax rate is calculated on the service charge amount and then added to the check's total tax amount. This example uses the following values for the check, service charge, and tax rate:


```
Check total amount before service charge is applied = $50.00
Check total tax amount before service charge is applied = $2.50
Service charge fixed amount: $10.00
State tax rate: 5.00%
```

1. Calculate the state tax on the service charge amount: $10.00 (service charge amount) * 5% (tax rate) = $0.50 (total service charge tax)


2. Add the service charge tax amount to the check tax amount: $0.50 (service charge tax) + $2.50 (check tax amount) = $3.00 (total tax amount on the check)



**Procedure 6.19. Tax calculation example for two tax rates**

If the service charge has two or more applicable tax rates, each tax rate is calculated separately on the service charge amount and then those tax amounts are added to the check's tax amount. This example uses the following values for the check, service charge, and tax rates:


```
Check total amount before service charge is applied = $50.00
Check total tax amount before service charge is applied = $2.50
Service charge fixed amount: $10.00
State tax rate: 5.00%
Local tax rate: 1.00%
```

1. Calculate the state tax on the service charge amount: $10.00 (service charge amount) * 5% (state tax rate) = $0.50 (total state tax)


2. Calculate the local tax on the service charge amount: $10.00 (service charge amount) * 1% (local tax rate) = $0.10 (total local tax)


3. Add the tax amounts on the service charge: $0.50 (service charge state tax) + $0.10 (service charge local tax) = $0.60 (service charge total tax)


4. Add the service charge total tax to the check tax amount: $0.60 (service charge total tax) + $2.50 (check tax amount) = $3.10 (total tax amount on the check)



For **fixed amount** and **open amount** service charges, the service charge amount is known before the tax is calculated. Therefore, the tax calculation is straightforward: calculate the service charge amount and then include it in the Tax field on the payment screen.

For **fixed percent** service charges, the Tip / Tax option (in the [Tipping](adminGuide-adminUiOptionsReference#adminTippingRef)section of the Front of house &gt; Order screen setup &gt; UI options page) affects how fixed percent service charges are taxed. The option lets you specify whether a fixed percent service charge is calculated on a pre-tax basis (that is, first calculate the service charge on the net amount and then add the tax afterwards) or on a post-tax basis (that is, first add the tax to the net amount and then calculate the service charge on that amount). The calculated tax is then included in the Tax field on the payment screen.

