---
title: "Menu item inventory overview"
id: adminMenuItemInventoryOverview
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminMenuItemInventoryOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu item inventory"
previousSectionFile: adminGuide-adminMenuItemInventoryOmitChunkFromSearchIndex.md
previousSectionTitle: "Menu item inventory"
nextSectionFile: adminGuide-adminInventoryUpdateBackend.md
nextSectionTitle: "Changing inventory status on the menu item details page"
excerpt: "An important task in operating a restaurant is keeping track of the inventory of your restaurant's menu items. If the inventory of a menu item starts to run low or goes out of stock, you must decide..."
keywords: [menu,item,inventory,overview]
procedures: 0
codeExamples: 0
---

### Menu item inventory overview

An important task in operating a restaurant is keeping track of the inventory of your restaurant's menu items. If the inventory of a menu item starts to run low or goes out of stock, you must decide when to reorder. You can check the inventory status value of menu items for information as to their availability.



> **Note**
> 
> The menu item inventory status feature described here is not related to the Toast Inventory module.


Each menu item details page has an Inventoryproperty that lists the status of the menu item's inventory:

![The Inventory property of a menu item.](https://doc.toasttab.com/doc/media/item-inventory-status.png)

The menu item's inventory status will be one of these values:

- In Stock - the menu item is in stock in the restaurant and can be selected for an order. In Stock is the default value when you add a new menu item to a menu. The menu item's status remains as In Stock until you manually change the status.


- Out of Stock - the menu item is no longer in stock in the restaurant. The number `0` (zero) displays on the menu item's button on the Toast POS device, which indicates that you cannot select the menu item for an order. The menu item's status remains as Out of Stock until you manually change the status. Changing the inventory status of a menu item to Out of Stock is known as 86ing the menu item.


- Quantity - the menu item is in limited supply. The amount of remaining menu items is indicated by a Quantity field in the Inventory section. The quantity number also displays on the menu item's button on the Toast POS device.

After you manually set the Quantity status for a menu item, the quantity amount is automatically decreased by the Toast platform each time you order that menu item. For example, if you set a quantity of 8 for a hamburger menu item and then you order two hamburgers, the number in the Quantity field automatically decreases to 6 when you send the order to the kitchen. When the quantity amount reaches 0 (zero), the Toast platform automatically changes the inventory status to Out of Stock for the menu item.



You should monitor the inventory status to make sure the availability of menu items is correctly shown on the menu item buttons on the Toast POS device. For example, if a food item suddenly goes out of stock during rush hour, you can 86 the item and the new remaining quantity of 0 is communicated to the restaurant's Toast POS devices when you publish the change. The menu item's button then displays a `0`and the Toast platform will not allow the server to add the menu item to an order.

The following sections describe how to change the inventory status of menu items and how to quickly find out which menu items are out of stock or low in quantity.

