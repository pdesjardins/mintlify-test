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


<table>
  <thead>
    <tr>
      <th>Area</th>
      <th>Task</th>
      <th>Additional information</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Configuration Syncing</td>
      <td>Retrieve employees from the labor API on a recurring basis. <br/> <a href="https://doc.toasttab.com/openapi/labor/operation/employeesGet/">More information</a></td>
      <td>If your reservation functionality assigns reservation orders to specific employees, you need to have up-to-date information about the employees at the restaurant.</td>
    </tr>
    <tr>
      <td>Configuration Syncing</td>
      <td>Retrieve restaurant tables from the configuration API on a recurring basis. <br/> <a href="https://doc.toasttab.com/openapi/configuration/operation/tablesGet/">More information</a></td>
      <td>If your reservation functionality reserves places at specific tables, you need to have up-to-date information about the tables at the restaurant.</td>
    </tr>
    <tr>
      <td>Configuration Syncing</td>
      <td>Retrieve restaurant hours from the restaurants API on a recurring basis. <br/> <a href="https://doc.toasttab.com/openapi/restaurants/operation/restaurantsRestaurantGuidGet/">More information</a></td>
      <td>Having current information about a restaurant's hours allows you to prevent guests from placing reservations at times when the restaurant is not open.</td>
    </tr>
    <tr>
      <td>Configuration Syncing</td>
      <td>Retrieve revenue centers from the configuration API on a recurring basis. <br/> <a href="https://doc.toasttab.com/openapi/configuration/operation/revenueCentersGet/">More information</a></td>
      <td>Including revenue centers on your orders allow restaurants to choose how to categorize your orders in their revenue reporting.</td>
    </tr>
    <tr>
      <td>Configuration Syncing</td>
      <td>Retrieve dining options from the configuration API on a recurring basis. <br/> <a href="https://doc.toasttab.com/openapi/configuration/operation/diningOptionsGet/">More information</a></td>
      <td>The dining option governs certain other elements of how an order should be structured. <br/> To be accepted by the Toast platform, the order must contain the order dining option.</td>
    </tr>
    <tr>
      <td>Order Placement</td>
      <td>Develop the capability to place a reservation order at the reserved table at the reservation time. <br/> Assign a revenue center and server to this order if appropriate. <br/> <a href="apiDevGuide-apiOrderTypeDetails#apiOrdersCreateDinein">More information</a></td>
      <td>By placing an order at a restaurant table at the time of a reservation, the restaurant can take the reserved party's order more quickly, and you can have a direct linkage between your reservation and its associated order. <br/> Consider assigning a server so that the correct employee sees this order in their list of open orders. <br/> Consider assigning a revenue center to the order so that it appears correctly on the restaurant's revenue reports.</td>
    </tr>
    <tr>
      <td>Reporting</td>
      <td>Retrieve all configuration data that you will use in your reporting and analytics. <br/> Examples of configuration data that you may want include discounts, service charges, payment types, sales categories, menu items, and menu groups. <br/> <a href="https://doc.toasttab.com/openapi/configuration/overview/">More information</a></td>
      <td>If your reports allow users to see the names or other attributes of information that is associated with your reservation orders, you need to periodically poll the configuration or menus APIs for the associated data.</td>
    </tr>
    <tr>
      <td>Reporting</td>
      <td>Retrieve updates about orders associated with your reservations using using the <code>startDate</code>/<code>endDate</code> parameters of the <code>/orders</code> endpoint of the orders API. <br/> <a href="https://doc.toasttab.com/openapi/orders/operation/ordersGet/">More information</a></td>
      <td>By retrieving order status updates on a recurring basis, you can know the item selections placed on your order, that total amount spent, and other order data that you can use for your analytics and reporting.</td>
    </tr>
  </tbody>
</table>

