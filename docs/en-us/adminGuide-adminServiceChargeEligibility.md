---
title: "Service charge eligibility"
id: adminServiceChargeEligibility
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminServiceChargesOmitChunkFromSearchIndex.md
parentSectionTitle: "Service charges"
previousSectionFile: adminGuide-adminServiceChargeType.md
previousSectionTitle: "Service charge components"
nextSectionFile: adminGuide-adminServiceChargeCalculation.md
nextSectionTitle: "Service charge calculations"
excerpt: "Service charges can be applied automatically based on eligibility criteria. Service charges also can be applied manually."
keywords: ["service", "charge", "eligibility"]
procedures: 0
codeExamples: 0
---

Service charges can be applied automatically based on eligibility criteria. Service charges also can be applied manually.

## Criteria for applying a service charge automatically

The Toast platform uses the following criteria to determine whether a service charge can be automatically applied to a check.


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className="">Eligibility Criteria</th>
      <th className="">Settings and Description</th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><strong className="">Service charge threshold</strong> </td>
      <td className="">The Apply After Amount Threshold configuration option sets a threshold (as a currency amount) that determines whether the service charge is applied automatically to the check. <br/> If the pre-discount amount of a check is equal to or greater than this amount, then the service charge is applied automatically. <br/> For example, if the threshold is $10.00, the service charge is applied automatically if the check total is $10.00 or $25.00. It is not automatically applied if the check total is $8.00. <br/> If the threshold is 0.00 or blank, then the service charge is not applied automatically based on the amount of the check. You can configure the service charge to be applied automatically based on the type of order, or the service charge can be applied manually. <blockquote><strong>Note</strong> The threshold is always compared against the pre-discount amount of the check, regardless of whether the service charge is configured as a pre-discount or post-discount service charge.</blockquote> </td>
    </tr>
    <tr className="">
      <td className=""><strong className="">Delivery dining option</strong> </td>
      <td className="">For delivery orders, a delivery service charge is applied automatically to a check when the Dining Option is set to Delivery and the service charge meets its configured thresholds. <br/> Delivery service charges have the following additional configuration options:<ul className=""><li className="">The Waive Fee Threshold setting waives the service charge if the pre-discount amount of the check is greater than or equal to a configured amount. For example, you might waive the delivery fee for orders greater than $50.00. <br/> The Waive Fee Threshold and Apply After Amount Threshold settings are mutually exclusive. If you set one, you cannot set the other. <br/> If you configured Apply After Amount Threshold for the service charge, then you cannot configure Waive Fee Threshold for that service charge.</li><li className="">The Delivery Distance Threshold setting allows you to apply a service charge if the delivery distance is equal to or greater than a specified length.</li></ul></td>
    </tr>
    <tr className="">
      <td className=""><strong className="">Take Out dining option</strong> </td>
      <td className="">For takeout orders, a takeout service charge is automatically applied to a check when the Dining Option is set to Take Out and the service charge meets its configured thresholds.</td>
    </tr>
    <tr className="">
      <td className=""><strong className="">Dine-In dining option</strong> </td>
      <td className="">For dine-in orders, a dine-in service charge is automatically applied to a check when the Dining Option is set to Dine-In and the service charge meets its configured thresholds.</td>
    </tr>
    <tr className="">
      <td className=""><strong className="">Service area</strong> </td>
      <td className="">If you have service areas, then you can assign a gratuity service charge to be applied automatically to orders that are taken in a specific service area. <br/> The gratuity service charge is applied when the restaurant employee sets Auto-apply gratuity to Yes. <br/> You configure the service charge for a service area from the Service areas page. The configuration includes the service charge to apply, and whether to apply the charge based on a minimum party size. For example, you might only apply the service charge for parties of six or larger. <br/> To configure a service charge for a service area:<ol className=""><li className="">Choose Front of house &gt; Tables & sections &gt; Service areas.</li><li className="">Click the name of the service area that you want to edit.</li><li className="">To choose the service charge to use, click Select Service Charge.</li><li className="">From the Minimum Party Size dropdown, select the minimum party size for which to apply the service charge.</li></ol></td>
    </tr>
  </tbody>
</table>
</div>

## Manually adding and removing service charges

If a service charge is not automatically applied to a check, a restaurant employee can manually add the service charge. To add the service charge:

1. Tap Svc Charge on the Order screen.


2. In the Update Service Charge dialog box, select the check box for the service charge from the list.


3. For an open amount service charge, specify the currency amount.



From the Update Service Charge dialog box, the restaurant employee can also remove applied service charges from the order.

