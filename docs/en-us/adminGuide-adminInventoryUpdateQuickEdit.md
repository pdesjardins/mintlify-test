---
title: "Changing inventory status in Quick Edit mode"
id: adminInventoryUpdateQuickEdit
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminMenuItemInventoryOmitChunkFromSearchIndex.md
parentSectionTitle: "Menu item inventory"
previousSectionFile: adminGuide-adminInventoryUpdateBackend.md
previousSectionTitle: "Changing inventory status on the menu item details page"
nextSectionFile: adminGuide-plartformAutomaticallyRefreshingInventory.md
nextSectionTitle: "Automatically refreshing inventory"
excerpt: "You can change a menu item's inventory status in Quick Edit mode on the Toast POS device. This method is especially useful for quickly 86ing a menu item that has suddenly gone out of stock."
keywords: ["changing", "inventory", "status", "quick", "edit", "mode"]
procedures: 1
codeExamples: 0
---

You can change a menu item's inventory status in Quick Edit mode on the Toast POS device. This method is especially useful for quickly 86ing a menu item that has suddenly gone out of stock.

**Procedure 8.140. To update the menu item's inventory status in Quick Edit mode**

1. Use a manager passcode to log in to the Toast POS device.


2. Enter Quick Edit mode as follows:

1. On the Order screen, press and hold the button of the menu item whose status you want to change.


2. On the Quick Edit mode prompt, tap **Enter Quick Edit**.




3. On the **Quick Edit** screen, the **Inventory** section shows the current inventory status for the menu item (which is **In Stock** in this example). Tap the **Inventory** drop-down list box to display the inventory status selections:

![A Quantity inventory status for a menu item.](https://doc.toasttab.com/doc/media/item-inventory-quick-edit-screen.png)


4. Select an inventory status for this menu item:

- If you select the **In Stock** status, the **Quantity** field is cleared if it has a number.


- If you select the **Out of Stock** status, a 0 (zero) is automatically entered in the **Quantity** field. Use this status to 86 the menu item.


- If you select the **Quantity** status, you also enter a number in the **Quantity** field that represents the remaining amount of menu items.




5. Tap **Save** and then **Done**.



If you selected **Out of Stock**, the menu item button shows a `0` and you cannot select the item. If you selected **Quantity**, the menu item button shows the quantity amount that you specified.

