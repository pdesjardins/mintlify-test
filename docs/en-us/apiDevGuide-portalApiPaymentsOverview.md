---
title: "Payments overview"
id: portalApiPaymentsOverview
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingPaymentInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 3. Payments"
previousSectionFile: apiDevGuide-portalApiGettingPaymentInformationOmitChunkFromSearchIndex.md
previousSectionTitle: "Chapter 3. Payments"
nextSectionFile: apiDevGuide-apiGettingPaymentInformationOmitChunkFromSearchIndex.md
nextSectionTitle: "Getting payment information"
excerpt: "You can use the orders API to get information about payments made for checks at your restaurant."
procedures: 0
codeExamples: 0
---

You can use the orders API to get information about payments made for checks at your restaurant.

- You send a `GET` request to the `/payments` endpoint to get a list of the payments made in one business day.


- You send a `GET` request to the `/payments/<em>&#123;guid&#125;</em>` endpoint to get detailed information about one payment, specified by its GUID.



