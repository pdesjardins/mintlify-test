---
title: "Chapter 3. Payments"
id: portalApiGettingPaymentInformationOmitChunkFromSearchIndex
type: chapter
documentId: apiDevGuide
parentSectionFile: apiDevGuide-index.md
parentSectionTitle: "Developer guide"
previousSectionFile: apiDevGuide-apiOrdersDeferredMenuItems.md
previousSectionTitle: "Deferring menu items"
nextSectionFile: apiDevGuide-apiGettingPaymentInformationOmitChunkFromSearchIndex.md
nextSectionTitle: "Getting payment information"
procedures: 0
codeExamples: 0
---

# Chapter 3. Payments

## Payments overview

You can use the orders API to get information about payments made for checks at your restaurant.

- You send a `GET` request to the `/payments` endpoint to get a list of the payments made in one business day.


- You send a `GET` request to the `/payments/`{guid}`` endpoint to get detailed information about one payment, specified by its GUID.



