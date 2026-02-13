---
title: "Required scopes to retrieve order data"
id: apiOrdersGetScopes
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingOrdersOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting order information"
previousSectionFile: apiDevGuide-portalApiGettingOrdersOmitChunkFromSearchIndex.md
previousSectionTitle: "Getting order information"
nextSectionFile: apiDevGuide-apiOrdersGetDetailedInfoAboutOneOrder.md
nextSectionTitle: "Getting detailed information about one order"
excerpt: "To retrieve order data from the Toast platform, your Toast API client must at least have the orders:read..."
keywords: ["delivery_info.address:read", "deliveryInfo", "Check.customer", "curbsidePickupInfo"]
procedures: 0
codeExamples: 0
---

To retrieve order data from the Toast platform, your Toast API client
  must at least have the `orders:read` scope. API clients that
  submit orders to the Toast platform must have both the
  `orders:read` scope and the `orders.channel:read`
  scope.

The following scopes allow you to view guest data:



**`delivery_info.address:read`**
: This scope is needed to view the `deliveryInfo`
        information, which provides details about the address to deliver the
        order to.

If your Toast API client does not have the
        `delivery_info.address:read` scope, then the
        `deliveryInfo` value is `null`.



**`guest.pi:read`**
: This scope is needed to view the following values:

- `Check.customer` - Name and contact information
            for the guest.


- `curbsidePickupInfo` - Information about the
            vehicle the guest uses for a curbside pickup.



If your Toast API client does not have the
        `guest.pi:read` scope, then the response does not include
        the `customer` or `curbsidePickupInfo`
        values.





For more information about scopes and how they work, see [Scopes](apiDevGuide-apiScopes).

