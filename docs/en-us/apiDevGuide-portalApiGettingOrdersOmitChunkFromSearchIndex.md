---
title: "Getting order information"
id: portalApiGettingOrdersOmitChunkFromSearchIndex
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 2. Orders"
previousSectionFile: apiDevGuide-apiOrdersOmitChunkFromSearchIndex.md
previousSectionTitle: "Chapter 2. Orders"
nextSectionFile: apiDevGuide-apiOrdersGetDetailedInfoAboutOneOrder.md
nextSectionTitle: "Getting detailed information about one order"
procedures: 0
codeExamples: 0
---

## Getting order information

### Required scopes to retrieve order data

To retrieve order data from the Toast platform, your Toast API client must at least have the `orders:read`scope. API clients that submit orders to the Toast platform must have both the `orders:read`scope and the `orders.channel:read`scope.

The following scopes allow you to view guest data:



**`delivery_info.address:read`**
: This scope is needed to view the `deliveryInfo`information, which provides details about the address to deliver the order to.

If your Toast API client does not have the `delivery_info.address:read`scope, then the `deliveryInfo`value is `null`.



**`guest.pi:read`**
: This scope is needed to view the following values:

- `Check.customer`- Name and contact information for the guest.


- `curbsidePickupInfo`- Information about the vehicle the guest uses for a curbside pickup.



If your Toast API client does not have the `guest.pi:read`scope, then the response does not include the `customer`or `curbsidePickupInfo`values.





For more information about scopes and how they work, see [Scopes](apiScopes.html).

