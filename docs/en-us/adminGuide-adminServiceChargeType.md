---
title: "Service charge components"
id: adminServiceChargeType
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminServiceChargesOmitChunkFromSearchIndex.md
parentSectionTitle: "Service charges"
previousSectionFile: adminGuide-adminServiceChargeOverview.md
previousSectionTitle: "Service charge overview"
nextSectionFile: adminGuide-adminServiceChargeEligibility.md
nextSectionTitle: "Service charge eligibility"
excerpt: "The service charge configuration includes the amount of the service charge, how to apply the service charge, and whether to apply tax to the service charge."
keywords: ["service", "charge", "components"]
procedures: 0
codeExamples: 0
---

The service charge configuration includes the amount of the service charge, how to apply the service charge, and whether to apply tax to the service charge.

## How the service charge type determines the service charge amount

The service charge type determines the amount of the service charge:

- Fixed Percent: The service charge is a percent of the check price. This service charge is calculated as a percentage of the pre/post-discount and pre/post-tax total amount of a check, depending on its configuration.


- Fixed Amount: The service charge is a set currency amount.


- Open Amount: The service charge does not have a predetermined amount. The currency amount is entered each time this service charge is applied to a check.



## How the service charge is applied

The following service charge settings affect how the service charge is applied and assigned:

- Assign to check owner (Gratuity): Assigns the revenue of the service charge in one of two ways:

- As a gratuity paid to the check owner. Examples of check owners include the server, bartender, or the driver on delivery orders.

See [Effects of gratuity service charges](adminGuide-adminServiceChargeType#adminGratuityServiceChargeEffects).


- As a non-gratuity that is collected by the restaurant and added to the restaurant's [*net sales*](adminGuide-adminGlossary.html#glossNetSales) amount.




- Apply After Amount Threshold: Sets the minimum currency amount that a check must have before the service charge automatically applies.

When the check amount is equal to or greater than the threshold, the service charge is applied automatically.

If the threshold is 0.00 or is blank, then the service charge is not applied automatically based on the amount of the check. You can configure the service charge to be applied automatically based on the type of order, or the service charge can be applied manually.


- Delivery?: Controls whether to apply the service charge to delivery orders. You cannot configure an Open Amount service charge to be automatically applied to delivery orders.


- Take Out?: Controls whether to apply the service charge to takeout orders. You cannot configure an Open Amount service charge to be automatically applied to takeout orders.


- Dine-In?: Controls whether to apply the service charge to dine-in orders. You cannot configure an Open Amount service charge to be automatically applied to dine-in orders.



You should configure separate service charges for each dining option (delivery, takeout, dine-in). It is not recommended to use the same service charge for different dining options.

## Whether to apply tax to the service charge

Optionally, you can configure the service charge to be [taxed](adminGuide-adminServiceChargeCalculation#adminServiceChargeTaxes), using one or more of your configured tax rates.

## Effects of gratuity service charges

For gratuity service charges, be aware of the following:


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className=""><p className="text-base leading-relaxed">Part of service charges affected</p></div></th>
      <th className=""><div className=""><p className="text-base leading-relaxed">Important information</p></div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Location of gratuity service charges on a check</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">On the Toast POS device, gratuity service charge amounts are listed as Fees and Charges in the payment section of the check.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Suggested tip amounts</p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">When a gratuity service charge is applied to a check, it affects the suggested tip amounts shown on digital receipts.</p> <p className="text-base leading-relaxed">The Toast platform overrides the suggested tip percentages that you configure with a set of pre-defined percentages. For example, on the UI Options page, you may have set the <a href="adminGuide-adminUiOptionsReference#confCustomizeTipPercentages" className="">Customize Tip Percentages</a> option to 20%, 22%, and 25%. However, if a gratuity service charge is applied, then on digital receipt the suggested tip percentages are 3%, 5%, and 7%. To open the UI Options page, choose Front of House &gt; Order screen setup &gt; UI options.</p> <p className="text-base leading-relaxed">The same behavior occurs with printed receipts if you enabled the Display Tip Percentages on Customer Receipts option on the Receipt Setup page. To open the Receipt Setup page, choose Payments &gt; Checks & receipt setup &gt; Guest receipt setup.</p> <p className="text-base leading-relaxed">Non-gratuity service charges do not affect the configured suggested tip percentages.</p> <p className="text-base leading-relaxed"><strong className="font-semibold">Not supported on Toast Mobile Order & Pay </strong> On Toast Mobile Order & Pay, suggested tip amounts are not overridden when a gratuity service charge is added.</p></div></td>
    </tr>
  </tbody>
</table>
</div>

