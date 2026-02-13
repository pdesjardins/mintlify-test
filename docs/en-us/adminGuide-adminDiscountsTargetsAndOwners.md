---
title: "Discount configurations for multi-location restaurants"
id: adminDiscountsTargetsAndOwners
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminDiscountsIntroOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 9. Discounts"
previousSectionFile: adminGuide-adminBulkDiscounts.md
previousSectionTitle: "Bulk discounts"
nextSectionFile: adminGuide-platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 10. Kitchen operations and fulfillment"
excerpt: "The discount..."
keywords: ["discount", "configurations", "multilocation", "restaurants"]
procedures: 0
codeExamples: 0
---

The discount configuration page includes specific settings for restaurants that use the multi-location module (previously the enterprise module). You can configure the locations that can use or configure the discount. You can also create other versions of the discount.

![The Edit Discount page showing settings for multi-location restaurants.](https://doc.toasttab.com/doc/media/discount-multilocation-fields.png)

The settings for restaurants with the multi-location module are the following:



**New Version**
: For restaurants that use the multi-location module, the discount number is a multi-location ID that the Toast platform uses to determine versions for all of the restaurant locations.

You use the New Version button to create a new version of the discount. For details about managing versions, see [Creating a version of a configuration entity](adminGuide-creatingAVersionOfAConfigurationEntity).



**Target**
: The restaurant or restaurant group that can use a discount. The discount is available at the restaurant or restaurant group that you choose.

If you choose a restaurant group, the discount is also available at any of that restaurant group's children, which may include other restaurant groups or individual locations.



**Owner**
: Controls which restaurant employees can edit the discount.

Employees of the selected restaurant or group who have the 6. Web Setup &gt; 6.1 Discounts Setup[permission](adminGuide-adminPermissions#adminWebSetupAccessPermissionsReferenceTable)can edit the discount.





