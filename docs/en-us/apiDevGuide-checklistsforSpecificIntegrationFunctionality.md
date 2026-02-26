---
title: "Checklists for specific integration functionality"
id: checklistsforSpecificIntegrationFunctionality
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalChecklistsAndTestPlansOmitChunkFromSearchIndex.md
parentSectionTitle: "Checklists and test plans"
previousSectionFile: apiDevGuide-apiIntegrationChecklists.md
previousSectionTitle: "Checklist and test plans overview"
nextSectionFile: apiDevGuide-integrationTestPlans.md
nextSectionTitle: "Integration test plans"
externalReferences: [https://doc.toasttab.com/openapi/labor/operation/employeesGet/, https://doc.toasttab.com/openapi/configuration/operation/tablesGet/, https://doc.toasttab.com/openapi/restaurants/operation/restaurantsRestaurantGuidGet/, https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/, https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/, https://doc.toasttab.com/openapi/configuration/overview/, https://doc.toasttab.com/openapi/orders/operation/ordersGet/]
excerpt: "Toast provides the following integration checklists."
procedures: 0
codeExamples: 0
---

Toast provides the following integration checklists.

## Reservation integration checklist

This section provides a checklist you can use to build a reservation integration with the Toast POS system.

**This checklist is a guideline, not a definitive list of what you need to do to build your integration.** Please consider whether you need to incorporate things into your integration that are not on this list, or whether any items on this list do not apply to your integration.

You can [download a CSV version of the checklist](toast-api-integration-checklist-reservation.csv).

| Area | Task | Additional information | 
| --- | --- | --- |
| Configuration Syncing | Retrieve employees from the labor API on a recurring basis.[More information](https://doc.toasttab.com/openapi/labor/operation/employeesGet/) | If your reservation functionality assigns reservation orders to specific employees, you need to have up-to-date information about the employees at the restaurant. | 
| Configuration Syncing | Retrieve restaurant tables from the configuration API on a recurring basis.[More information](https://doc.toasttab.com/openapi/configuration/operation/tablesGet/) | If your reservation functionality reserves places at specific tables, you need to have up-to-date information about the tables at the restaurant. | 
| Configuration Syncing | Retrieve restaurant hours from the restaurants API on a recurring basis.[More information](https://doc.toasttab.com/openapi/restaurants/operation/restaurantsRestaurantGuidGet/) | Having current information about a restaurant's hours allows you to prevent guests from placing reservations at times when the restaurant is not open. | 
| Configuration Syncing | Retrieve revenue centers from the configuration API on a recurring basis.[More information](https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/) | Including revenue centers on your orders allow restaurants to choose how to categorize your orders in their revenue reporting. | 
| Configuration Syncing | Retrieve dining options from the configuration API on a recurring basis.[More information](https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/) | The dining option governs certain other elements of how an order should be structured.To be accepted by the Toast platform, the order must contain the order dining option. | 
| Order Placement | Develop the capability to place a reservation order at the reserved table at the reservation time.Assign a revenue center and server to this order if appropriate.[More information](docs/en-us/apiDevGuide-apiOrderTypeDetails#apiOrdersCreateDinein) | By placing an order at a restaurant table at the time of a reservation, the restaurant can take the reserved party's order more quickly, and you can have a direct linkage between your reservation and its associated order.Consider assigning a server so that the correct employee sees this order in their list of open orders.Consider assigning a revenue center to the order so that it appears correctly on the restaurant's revenue reports. | 
| Reporting | Retrieve all configuration data that you will use in your reporting and analytics.Examples of configuration data that you may want include discounts, service charges, payment types, sales categories, menu items, and menu groups.[More information](https://doc.toasttab.com/openapi/configuration/overview/) | If your reports allow users to see the names or other attributes of information that is associated with your reservation orders, you need to periodically poll the configuration or menus APIs for the associated data. | 
| Reporting | Retrieve updates about orders associated with your reservations using using the `startDate`/`endDate` parameters of the `/orders` endpoint of the orders API.[More information](https://doc.toasttab.com/openapi/orders/operation/ordersGet/) | By retrieving order status updates on a recurring basis, you can know the item selections placed on your order, that total amount spent, and other order data that you can use for your analytics and reporting. | 

