---
title: "Restaurant closeoutHour and business dates"
id: apiRestaurantBusinessDate
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiRestaurantInfo.md
parentSectionTitle: "Restaurant information overview"
previousSectionFile: apiDevGuide-apiRestaurantInfo.md
previousSectionTitle: "Restaurant information overview"
nextSectionFile: apiDevGuide-apiGettingRestaurantInfoOmitChunkFromSearchIndex.md
nextSectionTitle: "Getting restaurant info"
externalReferences: [https://doc.toasttab.com/openapi/orders/overview/, https://doc.toasttab.com/openapi/labor/overview/]
excerpt: "The..."
keywords: ["restaurant", "closeouthour", "business", "dates", "closeoutHour", "businessDate"]
procedures: 0
codeExamples: 0
---

The restaurant API's `closeoutHour` determines your restaurant's `businessDate` value in other Toast APIs. The `closeoutHour` is a value from 0-12 (midnight (0) to noon (12)), which represents your restaurant's **Business Day Cutoff** configuration in Toast Web. For example, if your restaurant's **Business Day Cutoff** field is set to **4 AM**, the `closeoutHour` value will be `4`. The time zone for the **Business Day Cutoff** is determined by your restaurant's **Time Zone** configuration in Toast Web.



> **Note**
> 
> Your restaurant's **Business Day Cutoff** and **Time Zone** configurations can only be updated by Toast Support.


## Toast Web business closeout operations

When your restaurant's `closeoutHour` time has been reached, the following operations occur in Toast Web:

- Any employees who are still clocked in are automatically clocked out.


- Card payments that have not been captured yet are automatically captured. This is typically the entire day's card payments.





> **Note**
> 
> The Toast platform will not close unpaid orders. Unpaid orders remain open until they are resolved either by being paid or voided.


## Toast API business closeout operations

When your restaurant's `closeoutHour` time has been reached, the following operations occur in Toast APIs.

**Orders API **

- `closeDate`: The `closeDate` value is set to a time after the `closeoutHour`.


- `modifiedDate`: The `modifiedDate`value is set to a time after the `closeoutHour`.



For more information about the orders API, see [Toast orders API](https://doc.toasttab.com/openapi/orders/overview/).

**Labor API **

- `outDate`: Any time entries without an `outDate` value are automatically closed and the `outDate` value is set to the business cut-off time.


- `modifiedDate`: The `modifiedDate`value is set to the business cut-off time for any time entries closed at the business cut-off time.



 For more information about the labor API, see [Toast labor API](https://doc.toasttab.com/openapi/labor/overview/).

