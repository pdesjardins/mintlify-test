---
title: "Toast APIs and the enterprise module"
id: apiToastApisAndTheEnterpriseModule
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-generalToastApiInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "General Toast API information"
previousSectionFile: apiDevGuide-api_dates_and_timestamps.md
previousSectionTitle: "Dates and timestamps"
nextSectionFile: apiDevGuide-apiResponseDataPagination.md
nextSectionTitle: "Paginating response data"
excerpt: "Using Toast Web, you define configuration for how your Toast platform behaves. This includes such tasks as defining menus, kitchen set up, dining area set up, applied tax rates, and so on. You must..."
procedures: 0
codeExamples: 0
---

### Toast APIs and the enterprise module

Using Toast Web, you define configuration for how your Toast platform behaves. This includes such tasks as defining menus, kitchen set up, dining area set up, applied tax rates, and so on. You must publish this configuration to make it available to the Toast POS devices used throughout your restaurant. For information about how to publish configuration changes, see [Publishing updates to restaurant configuration](platformPublishingDocsOmitChunkFromSearchIndex.html#platformPublishingOverview).

The enterprise module is an optional module that allows restaurant chains with multiple locations to share configuration across locations, for example, a common set of menu items. Core to the enterprise module's functionality is the concept of versions, which allow your locations to share some aspects of a configuration entity (a menu, menu item, discount reason, tax rate, and so on) while maintaining the ability to override other aspects. For example, your locations may share a Main Course menu group that includes chicken, salmon, lobster, and steak menu items. One location may not be able to serve lobster, so it would use a version of the Main Course menu group that omits the lobster menu item.

When you publish a restaurant's configuration, the Toast platform resolves which version of each configuration entity to use for each location. The Toast platform stores these resolved entities in its published data store. The published data store only ever includes one instance of each versioned entity for a given location. The Toast APIs use the published data store as their source of data. When you make a call to the Toast APIs, you must specify the restaurant that you are making the call for. The data you receive back from the data store is resolved for that location.

For more information on versions and how the Toast platform resolves which version to use, see [Session restaurant](understandingKeyEnterpriseConceptsOmitChunkFromSearchIndex.html#sessionRestaurant).



> **Note**
> 
> Because they can be shared among locations, employees are managed somewhat differently than other configuration entities. Future documentation will cover how the Toast APIs behave with respect to employees.


