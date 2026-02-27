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
      <th className=""><div className="">Eligibility Criteria</div></th>
      <th className=""><div className="">Settings and Description</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">Service charge threshold</strong> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed italic">[Complex content omitted - see <a href="https://doc.toasttab.com/doc/platformguide/index.html" className="underline">current documentation</a>]</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">Delivery dining option</strong> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For delivery orders, a delivery service charge is applied automatically to a check when the Dining Option is set to Delivery and the service charge meets its configured thresholds.</p> <p className="text-base leading-relaxed">Delivery service charges have the following additional configuration options:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">The Waive Fee Threshold setting waives the service charge if the pre-discount amount of the check is greater than or equal to a configured amount. For example, you might waive the delivery fee for orders greater than $50.00.</p> <p className="text-base leading-relaxed">The Waive Fee Threshold and Apply After Amount Threshold settings are mutually exclusive. If you set one, you cannot set the other.</p> <p className="text-base leading-relaxed">If you configured Apply After Amount Threshold for the service charge, then you cannot configure Waive Fee Threshold for that service charge.</p></li><li className=""><p className="text-base leading-relaxed">The Delivery Distance Threshold setting allows you to apply a service charge if the delivery distance is equal to or greater than a specified length.</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">Take Out dining option</strong> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For takeout orders, a takeout service charge is automatically applied to a check when the Dining Option is set to Take Out and the service charge meets its configured thresholds.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">Dine-In dining option</strong> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">For dine-in orders, a dine-in service charge is automatically applied to a check when the Dining Option is set to Dine-In and the service charge meets its configured thresholds.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><strong className="font-semibold">Service area</strong> </p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">If you have service areas, then you can assign a gratuity service charge to be applied automatically to orders that are taken in a specific service area.</p> <p className="text-base leading-relaxed">The gratuity service charge is applied when the restaurant employee sets Auto-apply gratuity to Yes.</p> <p className="text-base leading-relaxed">You configure the service charge for a service area from the Service areas page. The configuration includes the service charge to apply, and whether to apply the charge based on a minimum party size. For example, you might only apply the service charge for parties of six or larger.</p> <p className="text-base leading-relaxed">To configure a service charge for a service area:</p><ol className="list-decimal space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed">Choose Front of house &gt; Tables & sections &gt; Service areas.</p></li><li className=""><p className="text-base leading-relaxed">Click the name of the service area that you want to edit.</p></li><li className=""><p className="text-base leading-relaxed">To choose the service charge to use, click Select Service Charge.</p></li><li className=""><p className="text-base leading-relaxed">From the Minimum Party Size dropdown, select the minimum party size for which to apply the service charge.</p></li></ol></div></td>
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

