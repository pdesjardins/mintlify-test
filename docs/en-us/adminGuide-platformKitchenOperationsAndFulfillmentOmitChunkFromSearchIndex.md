---
title: "Chapter 10. Kitchen operations and fulfillment"
id: platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex
type: chapter
documentId: adminGuide
parentSectionFile: adminGuide-index.md
parentSectionTitle: "Platform guide"
previousSectionFile: adminGuide-adminDiscountsTargetsAndOwners.md
previousSectionTitle: "Discount configurations for multi-location restaurants"
nextSectionFile: adminGuide-adminItemRoutingOmitChunkFromSearchIndex.md
nextSectionTitle: "Item and order routing"
externalReferences: [https://central.toasttab.com/s/article/Customize-the-Appearance-of-KDS-Tickets, https://central.toasttab.com/s/article/Send-Text-Message-when-Order-is-Fulfilled-1492800294544]
procedures: 0
codeExamples: 0
---

# Chapter 10. Kitchen operations and fulfillment

## Kitchen configuration

### Adding a prep station

When you add a prep station, you have the option of choosing whether items are also sent to the expediter using the Send to Expediter setting. With this setting, items are sent to both the prep station and the expediter. This applies to both KDS and printed tickets.



> **Note**
> 
> The limited release Send to setting allows you to choose whether items for that prep station go to that prep station, the expediter, or both. The options are:
- Prep station and expediter: Items are sent to the prep station and the expediter.


- Expediter only: Items are only sent to the expediter. Items are not sent to the prep station.

If you choose to require fulfillment at prep station KDS devices before expediter KDS devices using the Sequenced KDS fulfillment setting, items assigned a prep station with the Send to setting set to Expediter only do not require fulfillment at prep stations, because they are not sent to the prep station at all.

They also do not appear as an option when assigning prep stations to a KDS device. For more information, see [Assigning a KDS device to a prep station](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminAssignPrepStationKDS).


- Prep station only: Items are only sent to the prep station. Items are not sent to the expediters.





When you add a prep station, you also assign a printer to it.

- If you use kitchen printers, assign kitchen printers to each prep station when you add the prep station.


- If you use KDS devices, assign a single, backup printer to every prep station.



To add a prep station, you must have the 6. Web Setup > 6.2 Kitchen / Dining Room Setup access permission.

**Procedure 10.1. To add a prep station**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Kitchen > Kitchen stations > Prep stations.


3. Select the + Add button. The Toast platform adds a row to the interactive grid.


4. Enter an identifying name for the prep station.


5. To print or display the prep station's tickets at an expediter printer or KDS, check Send to Expediter.

For example, your expediter needs the tickets for your Hot and Cold stations, but not for your Bar station. You check Send to Expediter for the Hot and Cold prep stations, but not for the Bar. For more information, see [Configure the expediter workflow](adminUsingExpo.html#adminConfigureExpediter).



> **Note**
> 
> If you have the limited release Send tosetting, you will see this instead of the Send to Expediter setting. Choose to send items to prep station, expediter, or both.



6. To monitor items sent to another station or stations by printing them on kitchen tickets, select the Other Stations. This option affects printed kitchen tickets only. For more information, see [Monitoring items at other prep stations](adminMonitoringTicketsOtherPrepStations.html).


7. Select the kitchen printer that you want to print this prep station's tickets.

- If the prep station uses a [KDS](adminRoutingOrdersKitchen.html), assign the backup printer.


- If the prep station is a [virtual or "no print" prep station](adminPreventingTicketsFromPrinting.html#adminNoPrintPrepStation), do not select a printer.




8. If the prep station primarily uses a kitchen printer, check Always Print Tickets. Every ticket sent to this prep station prints at the specified printer.

If the prep station uses a KDS, clear Always Print Tickets. Tickets print only when the system is in offline mode.


9. Save and publish your changes.



Repeat these steps to add your other prep stations.

After you set up your prep stations, you can [assign KDS devices](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminAssignPrepStationKDS) to them (if applicable) and [add them to your menus](adminRoutingToPrepStations.html#adminAssignPrepStationMenu).

### Creating an assembly line

An assembly line is created using prep stations that are then moved into the correct sequence. Before you create an assembly line, make sure that:

- You [created prep stations](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminAddPrepStation).


- You set the [Fulfillment Method](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configFulfillmentMethod) setting to Fulfill at each station independently.


- You verified that the menu entity and the assembly line you plan to assign to that menu entity use at least one of the same prep stations.



After you verify that these prerequisites are complete, you can create the assembly line and then assign the [assembly line to the relevant menus, menu groups, and menu items](platformKDSRoutingUsingAssemblyLines.html#platformKDSAssignAssemblyLinesToMenuEntities).

There is no maximum number of prep stations that you can use in an assembly line, but you can only use a prep station once in an assembly line.

The following procedure is for creating an assembly line for a single-restaurant location. For information about how to create assembly lines for multi-location restaurants, see [Assembly lines for multi-location restaurants](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#platformKDSCreatingAssemblyLinesMultiLocation).

**Procedure 10.2. To create an assembly line**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Kitchen > Kitchen stations > Assembly lines. The Assembly Lines page opens.


3. Select the Add new button in the top right. The New assembly line dialog opens.


4. Using the Name text box, assign a name to the assembly line and select Okay. The assembly line page opens.


5. Under the Sequence Prep Stations section, use the Prep stations dropdown menu to select the prep stations you want to use in the assembly line. You can also use the search box within the dropdown menu to find a specific prep station.


6. Use the reorder icon to hold and move the prep stations into the order you want items to travel through when using the assembly line.


7. Select the Save button. The assembly line page closes.


8. Publish your changes.



#### Assembly lines for multi-location restaurants

Assembly lines use versioning and targets for multi-location restaurants. The following procedure is for creating an assembly line for a multi-location restaurant. For information about versions, see [Versions](versions.html). For information about targets, see [Targets](targets.html).

**Procedure 10.3. To create an assembly line for multi-location restaurants**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Kitchen > Kitchen stations > Assembly lines. The Assembly Lines page opens.


3. Use the locations dropdown menu to select which locations you want to view.


4. Select the Add new button in the top right. The New assembly line dialog opens.


5. Using the Name text box, assign a name to the assembly line.


6. Select the Target dropdown menu. The Select Target dialog opens.


7. Using either the Restaurant groups or Locations tab, select the location you want to have access to this assembly line. You can only choose one location.



> **Note**
> 
> The Owner setting automatically defaults to the Target setting.



8. Select Okay. The assembly line page opens.



> **Note**
> 
> The Location specific variant option is currently unavailable.



9. Under the Sequence Prep Stations section, use the Prep stations dropdown menu to select the prep stations you want to use in the assembly line. You can also use the search box within the dropdown menu to find a specific prep station.


10. Use the reorder icon to hold and move the prep stations into the order you want items to travel through when using the assembly line.


11. Select the Save button. The assembly line page closes.


12. Publish your changes.



### Adding a kitchen printer

Every restaurant that uses the Toast platform has at least one kitchen printer.

- In a restaurant that primarily uses kitchen printers, there are usually at least two printers. Each printer acts as the backup for the other.


- In a restaurant that primarily uses KDS devices, you add a kitchen printer to act as the backup when the system is in *offline mode*. For more information about KDS devices in offline mode, see [KDS devices](platformKitchenOpsOfflineSupportOmitChunkFromSearchIndex.html#platformOfflineKDSDevices).


- You can route items that do not require tickets for fulfillment to a ["no print" prep station](adminPreventingTicketsFromPrinting.html#adminNoPrintPrepStation)that does not have an associated printer.


- In a restaurant that adds labels to items for off-premise dining, you can add an Epson L90 or TLP400 printer to print item labels.



Before you add a printer to the system, you must know the printer's IP address. Each printer shipped by the Toast configuration center is labeled with its configured IP address. IP addresses are formatted as a series of four numbers separated by periods, such as 192.168.1.171.

There are two methods to adding a new kitchen printer to your kitchen setup: through Toast Web or your Toast POS device. Toast support recommends adding kitchen printers through your Toast POS device to follow the setup workflow.



> **Important**
> 
> To add a kitchen printer, you must have the 6. Web Setup > 6.10 Printer and Cash Drawer Setup access permission.


Repeat these steps to add other kitchen printers, or to update the information for a printer by adding its backup printer. After you set up your printers, you can assign them to your prep stations.

#### To add a printer on the Toast POS app

1. Navigate to the Toast POS app home screen.


2. In the Setup section, select Printer Setup.



> **Note**
> 
> If this is the first printer added to your restaurant, move to [step 5](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#AddPrinterOnPOSAppStep).



3. Select + Add or replace printer.


4. Select Install a new printer and then Continue.


5. Select Wired or Wireless depending on your printer model.


6. Follow the workflow on the Toast POS app to find your printer.


7. Once found, select the printer model and then Continue.


8. Select the primary function for the printer. For kitchen printers, this is typically Kitchen Tickets, Both (Guest Receipts and Kitchen Tickets), or Item Labels.



> **Note**
> 
> This step is skipped if you are using a TLP400 printer. TLP400 uses Item Labels automatically.



9. If you selected Item Labels as the primary function for the printer, or use a TLP400 printer:



> **Note**
> 
> The following steps are available only to Epson L90 and TLP400 printers.


1. Select the label size you want to use. The options are:

- Small - Vertical : A 1.5 by 3 inch ticket. This label is printed sideways to optimize paper usage.


- Small - Horizontal : A 3 by 1.5 inch ticket.


- Medium - Horizontal : A 3 by 2 inch ticket.


- Large - Square : A 3 by 3 inch ticket.



Small and medium-sized tickets do not include custom logos or footers and summarize the number of modifiers not visible on the ticket (for example, "+2 modifiers").

For the Epson L90 printer, small vertical, small horizontal, and medium horizontal label sizes **must** use existing 76-80mm label printer paper.

For the TLP400 printer, small vertical and small horizontal label sizes **must** use 3 inch by 1.5 inch label printer paper, and medium horizontal label sizes **must** use 3 inch by 2 inch label printer paper.


2. Select either the guest name or ticket number to be displayed prominently at the top of the label and then Continue.



> **Note**
> 
> This configuration is only available for small and medium item label sizes.





10. Select the prep stations that will use the printer and then Continue.


11. Print a test ticket and continue the printer setup workflow.


12. Return to the Printer Setup screen, select the printer you added.


13. Select Printer Name, update the printer name, and select Save Changes. As a best practices, use the following naming convention for kitchen printers:

- Prep station name


- KP


- (Last number in the IP address)



For example, "Cold Station KP (171)" or "Backup KP (170)".


14. Select Backup Printer, choose a backup printer, and select Save Changes. If printing fails at this printer, the system redirects tickets to the backup printer.



#### To add a printer on Toast Web

1. [Access Toast Web ](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Payments > Checks & receipt setup > Printers and cash drawers.


3. Select the + Add button and then enter an identifying name for the kitchen printer. As a best practice, use the following naming convention for kitchen printers.

- Prep station name


- KP


- (Last number in the IP address)



For example, "Cold Station KP (171)" or "Backup KP (170)".


4. Specify the printer's model. For example, Epson U220.



> **Note**
> 
> The configuration options are specific to the printer model.



5. Enter the printer's IP address.


6. Depending on the printer make and model you may also have the following configurations:



> **Note**
> 
> Label configurations are only available for item label printers Epson L90 and TLP400.


- Ticket Type : Configures the type of ticket that the printer is printing, either Kitchen ticket or Item label.


- Label Size : Configures the size of the ticket for Item label ticket types. The ticket size options are:

- Small Vertical : A 1.5 by 3 inch ticket. This label is printed sideways to optimize paper usage.


- Small Horizontal : A 3 by 1.5 inch ticket.


- Medium Horizontal : A 3 by 2 inch ticket.


- Large Square : A 3 by 3 inch ticket.



Small and medium-sized tickets do not include custom logos or footers and summarize the number of modifiers not visible on the ticket (for example, "+2 modifiers").

For the Epson L90 printer, small vertical, small horizontal, and medium horizontal label sizes **must** use existing 76-80mm label printer paper.

For the TLP400 printer, small vertical and small horizontal label sizes **must** use 3 inch by 1.5 inch label printer paper, and medium horizontal label sizes **must** use 3 inch by 2 inch label printer paper.


- Label Format : Places either the Guest Name or Ticket Number at the top of the ticket. This is only available for small and medium item label sizes.


- Custom footer : Adds a custom footer to the end of the printed ticket.




7. Set the Kitchen Ticket Font Size.

The Customer Receipt Font Size does not apply to kitchen-only printers and can be left at the default setting.


8. Verify that the paper width is set to Wide.

The Narrow setting applies only to legacy printer models that Toast no longer supplies.



> **Important**
> 
> Item labels only use the Wide paper width.



9. To print kitchen tickets in English, set the Character Set to Western.

Currently, the only other character set that Toast supports is Chinese, for Toast TLP400, Epson U220 - Chinese, and Epson L90 printers. Note that if you use a Chinese printer, you must translate and enter all menu names and kitchen names into Chinese characters.


10. After you identify at least one printer, you can specify another printer as its Backup. If printing fails at this printer, the system redirects tickets to the backup.


11. Verify that the Cash Drawer option is set correctly. Typically, you set prep stations other than bar stations to No Cash Drawer.


12. Save and publish your changes.



### Assigning a KDS device to a prep station

If you use KDS devices to display tickets, you must have the 6. Web Setup > 6.2 Kitchen / Dining Room Setupaccess permission to configure each device to display the tickets for a specific prep station. Before you add a prep station to a KDS device, consider whether you want or need to display the items sent to that prep station on that device.



> **Note**
> 
> The Send to and Sequenced KDS fulfillment settings are in limited release.


Prep stations with the Send to setting set to Expediter only do not print or show items on prep station KDS devices. Prep stations with the Send tosetting set to Prep station and expediter or Prep station only display on prep station KDS devices. If you use Sequenced KDS fulfillment and require fulfillment at prep stations before expediter devices with this setting, items must be fulfilled at a prep station first. If you set the Send to setting to Prep station only, however, items do not require fulfillment at the expediter.



> **Note**
> 
> If a prep station uses the Send to setting set to Expediter only, the prep station cannot be assigned to a KDS device. Items sent to this prep station appear on the expediter KDS device and do not require fulfillment at prep stations first.


For more information about the Send to setting, see [Sequencing fulfillment by station type and level](platformKitchenUnderstandingItemFulfillmentKDS.html#platformKDSSequencingFulfillmentByStationTypeAndLevel). For more information about the Sequenced KDS fulfillmentsetting, see [Sending items to prep stations, expediters, or both](adminRoutingToPrepStations.html#platformKitchenSendingToPrepStationExpediterBoth).

**Procedure 10.4. To assign a prep station to a KDS device**

1. [Access the Toast POS Device Setup screen](adminConfigureDevice.html).


2. In the Kitchen Setup section, select Prep Stations.


3. To display tickets for a listed prep station on this KDS device, check the prep station's name.


4. Select Continue. The system saves the prep station assignment.



Repeat these steps for each of your prep station KDS devices.

#### About production items

When you [configure production items](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminConfigureProductionItem) for your restaurant, you create a customized system for tracking your most critical ingredients. The KDS reports a continuously updated total across fired orders for each production item below the individual tickets, including when the count is zero (0). You specify which production items you want to track on each of your KDS devices.

For example, the manager at a sports bar sets up production items to track their specialties, chicken tenders and chicken wings. They identify each menu item and modifier that uses chicken tenders, chicken wings, or both, and update the Toast platform to indicate how many tenders or wings each one requires.

- Chicken tenders come in two sizes: small (2) and large (6).


- Chicken wings come in two sizes: small (3) and large (6).



Finally, they configure the KDS devices at the Fry prep station and expediter station to show real-time totals for these production items.

![A KDS showing total counts for chicken wings and chicken tenders production items below the order tickets.](https://doc.toasttab.com/doc/media/kitchen-kds-production-items.png)

The KDS device displays the production items and totals below the tickets continuously, including when a total is zero (0). The number includes production items that are not yet fulfilled.

If you decide to enable the production item feature for your kitchen employees, note the following considerations.

- You can define one or more production items for each menu item or modifier.

For example, when the sports bar adds a combo appetizer that includes both tenders and wings to the menu, they assign both the Chicken Tenders production item and the Chicken Wings production item to that new menu item.


- When you define the quantity for a production item, you can enter whole numbers or halves.

For example, a production item for ribs can be assigned to a full rack menu item with a quantity of 1, and to a rack-and-a-half menu item with a quantity of 1.5.


- You can define one quantity for each production item that is assigned to a menu item or modifier. As a result, when you assign a production item to a menu item that uses size pricing, you can only define one quantity for it.

If you need to define different quantities for different item sizes, you must set up the sizes as modifiers and then assign the production item to each option.


- You cannot assign production items to pre- or post-modifiers.


- Production items provide real-time information on the KDS. Production item totals are not included in reports or contribute to inventory tracking.



#### Configure a production item

To configure a production item, you must have the following access permissions.

- 4. Restaurant Admin > 4.5 Edit Full Menu


- 6. Web Setup > 6.2 Kitchen / Dining Room Setup


- 7. Device Setup > 7.3 KDS and Order Screen Setup



Then, you complete this series of tasks.

1. [Create a production item](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminCreateProdItem) for each ingredient that you want to track on the KDS.


2. [Assign the production item](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminAssignProdItemQuantity) and its quantity to a menu item or modifier.


3. [Specify the production items](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminSpecifyProdItemDevice) that you want to see totaled on your KDS device.



Follow these procedures to complete the configuration of a production item.

**Procedure 10.5. To create a production item**

1. Identify an ingredient that you want your kitchen employees to track on KDS devices.


2. [Access Toast Web ](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


3. Choose Kitchen > Kitchen stations > Production items to open the Production itemspage.


4. Select the + Add button and then enter the name of the production item.


5. Repeat this procedure to create another production item.

For example, you set up production items for chicken tenders and chicken wings.

![The Production Items page in Toast Web, with items set up for chicken tenders and chicken wings.](https://doc.toasttab.com/doc/media/kitchen-tw-add-production-item.png)


6. To change the sequence in which production items display, both on this page and along the bottom of the KDS ticket screen, select Order. An Order column appears in the table so that you can enter a sequence number next to each production item.

For example, if you want the Chicken Tenders total to appear before the Chicken Wings total on your KDS, enter 1 next to Chicken Tenders and then select Done.


7. Save and publish your changes.



After you create one or more production items, you can assign them to menu items and modifiers.

**Procedure 10.6. To assign production item quantities to a menu item or modifier**

1. Identify a menu item or modifier that uses one of your production items and the quantity that it uses.


2. [Access Toast Web ](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend)and then choose Menus > Bulk management > Advanced properties.


3. (Multi-location restaurants only) Choose the locations you want to view from the You are viewing dropdown menu.


4. Select the name of the menu item.

- To add a production item to this menu item, scroll down to the Preparation section of the page.


- To add the production item to a modifier, scroll down to the Modifiers section of the page, select the name of the modifier group, select the name of the modifier, and then select Edit Item. You can then scroll down to the Preparation section of the page.




5. If you are editing a menu item, select its name to see its classic details page. If you are editing a modifier option, select its name, then select Edit Item to see the classic details page for the modifier's [item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference).


6. Scroll down to the Preparation section of the page.


7. In the Production Items field, select the plus (+) button and then use the dropdown list to select the production item.


8. Enter the quantity of the ingredient your kitchen uses to prepare this menu item or modifier.

For example, you update the "Small Wings" modifier to identify the number of chicken wings in a small order of wings, and the "Small Tenders" modifier to identify the number of chicken tenders in a small order of tenders.

![The Production Items field with a count of 3 chicken wings identified.](https://doc.toasttab.com/doc/media/kitchen-tw-add-production-item-count-for-item.png)


9. Repeat this procedure to assign another production item and its quantity to a menu item or modifier.


10. Save and publish your changes.



After you assign one or more production items to menu items or modifiers, you can set up your KDS devices to report the totals for specific production items.

**Procedure 10.7. To specify the production items to report on a KDS device**

1. Identify the prep stations and expediter seats that need to see the real-time totals for production items.


2. On a Toast POS device, select the Toast logo or left arrow in the top corner until the Toast POS home screen appears.


3. In the Setup section, select Device Setup and go to the Kitchen Setup section.


4. Select Production Items, and then select each production item that you want to display.


5. Select Continue, and then select the Toast logo or left arrow to return to the Toast POS home screen.


6. To verify that production item totals appear as expected, in the Mode section select Kitchen Display System.


7. Repeat this procedure to configure another KDS device to report production items.



### Configuring tickets

This section provides procedures and information about configuring kitchen tickets.

#### Color-coding items and modifiers on KDS tickets

Preparing orders accurately and efficiently can be an ongoing challenge, and errors can be expensive. With the KDS, you can use color to make the differences and similarities between menu items or modifiers easier to identify and act on.

In addition, this [Toast Central article](https://central.toasttab.com/s/article/Customize-the-Appearance-of-KDS-Tickets) provides an overview of customizing colors for KDS devices.

##### Using KDS colors

Examples of how you can use color-coding on your KDS tickets follow.

- You can identify a critical difference between menu items, such as the item size, by assigning a different color to each item. The following illustration shows KDS tickets for an order with large and small pizza items, before and after you assign different KDS colors to the items.

![A comparison of a pair tickets, each with a large pizza and a small pizza. The first ticket does not have color-coding for large or small, the second ticket does.](https://doc.toasttab.com/doc/media/KDS_color_add_item.png)


- You can alert employees to a guest's health concerns by assigning colors to your allergy modifiers. The following illustration shows KDS tickets for a pizza order that includes an allergy alert, before and after you assign a KDS color to the allergy modifier.

![A comparison of two tickets. The first does not have color-coding for an allergy modifier, the second does.](https://doc.toasttab.com/doc/media/KDS_color_allergy_mod.png)


- You can make the assembly of an item that contains multiple ingredients faster and more accurate by assigning colors to each modifier or to each category of modifiers. The following illustration shows KDS tickets for pizza items that have multiple toppings, before and after you assign different KDS colors to the cheeses, sauces, vegetables, and meats in your toppings modifier group.

![A comparison of two tickets, each with a large pizza. The first ticket does not have color-coding for modifiers, the second ticket does.](https://doc.toasttab.com/doc/media/KDS_color_add_mod.png)


- You can make items and modifiers that get sent to multiple prep stations easier to identify and assign. The following illustration shows a ticket for sandwiches and salads that gets sent to both your Grill/Fry and Cold prep stations, before and after you assign a KDS color to the salad items and modifiers that are the responsibility of the Cold station.

![A comparison of two tickets, each with a burger and a salad. The first ticket does not have color-coding for salad items and sides, the second ticket does.](https://doc.toasttab.com/doc/media/KDS_color_cold.png)

In this example, you could also assign colors to the different salad dressing submodifiers—yellow for ranch and blue for blue cheese, say—to make them easier to distinguish and fulfill accurately.





> **Note**
> 
> You cannot configure KDS colors for pre and post modifiers.


##### Configure KDS colors

To configure your menu items and modifiers to include a custom color background, you must have the 4. Restaurant Admin > 4.5 Edit Full Menu access permission.

Follow one of these procedures.

**Procedure 10.8. To configure a KDS color for a menu item**

1. [Access Toast Web ](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend)and then choose Menus > Menu manager.


2. Select Full menu view, then navigate to the menu item you want to edit. Select the item to see its side panel.


3. In the Kitchen section, select the KDS color tile. The color palette opens.


4. Select a color from either the Light mode or the Dark mode palette. A corresponding color is automatically selected in the other palette.


5. Select Save.


6. Publish your changes.



**Procedure 10.9. To configure a KDS color for a modifier**

1. Determine the modifiers that you want to highlight with color coding, and the color you want to assign to each one.


2. [Access Toast Web ](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend)and then choose Menus > Bulk management > Advanced properties.


3. (Multi-location restaurants only) Choose the locations you want to view from the You are viewingmenu.


4. Expand the advanced properties table to find the modifier you want to edit, select its name, then select Edit Item to see the classic details page for the modifier's [item reference](adminPricingModifierOptions.html#adminUnderstandingAModifierOptionsItemReference).


5. Next to the KDS Color, select the square tile. The [color palette](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminKdsColorPalette)opens.


6. Select the color that you want to assign to the modifier.


7. Save and publish your changes.



#### Sorting order for items and modifiers

The Toast platform allows you to specify how you want items and modifiers to be listed on kitchen tickets. The logic used to sort items is different from modifiers.

##### Sorting items on kitchen tickets

You can choose to sort items by assigned seat numbers, assigned sort order, or by how the items are entered on the order screen. You can use the [Item Sorting Priority](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configItemSortingPriority) setting to sort items on kitchen tickets.

- To sort by assigned seat numbers, you must enable the seat numbers modifier group with the Additional Modifier Groups setting, and assign the Seat Number modifier group to the menu item. If two items have the same seat number, they are sorted by Sort Order, if available. If no Sort Order is available, the items are sorted by how they were added to the order. For more information, see [Additional Modifier Groups](devPortalPlatformGuideUiOptionsOmitChunkFromSearchIndex.html#configAdditionalModifierGroups).


- To sort by sort order, you must assign a Sort Order value to the menu item. The Sort Order determines how the item is sorted against all other items. If two items have the same Sort Order, they are sorted by Seat Number if available. If no Seat Number is available, the items are sorted by how they were added to the order. If a Sort Order for an item is empty, it is listed after those that have a Sort Order assigned, then by Seat Number if available, and then how they were added to the order. This sorting also affects how items appear on order screens.


- To sort by how items are added to the order on an order screen, no additional configuration is needed.



##### Sorting modifiers on kitchen tickets

For modifiers, there are several settings that can be used to choose how modifiers are sorted on kitchen tickets:

- Modifier display mode


- Sort Order



> **Note**
> 
> Using the Sort Order setting to sort modifiers on kitchen tickets is in limited release. To access this feature, send an email to `<[kitchenfeedback@toasttab.com](mailto:kitchenfeedback@toasttab.com)>`.



- Modifier ordering priority


- Modifier group sorting 





> **Note**
> 
> The Sort Order setting only affects modifiers on kitchen tickets. The Modifier display mode, Modifier ordering priority, and Modifier group sorting settings affect modifiers on both kitchen tickets and order screens.


How these settings are prioritized depends on several factors. The following is an ordered list detailing the hierarchy of how these settings are applied.

1. If [Modifier display mode](devPortalPlatformGuideUiOptionsOmitChunkFromSearchIndex.html#configModifierDisplayMode) is set to:

- Vertical or Horizontal: The other settings affecting modifier sorting order apply as expected.


- Legacy or Legacy - Flatten: The option and its conditions override all other settings affecting the modifier sorting order.




2. If a modifier has a Sort Orderconfigured, that takes precedence and overrides Modifier ordering priority and Modifier group sorting settings. Modifiers that have a Sort Order assigned are listed before the modifiers that do not have a Sort Order.



> **Note**
> 
> For Sort Order to apply, Modifier display mode must be set to either Vertical or Horizontal.



3. If no Sort Order is configured for modifiers and [Modifier ordering priority](devPortalPlatformGuideUiOptionsOmitChunkFromSearchIndex.html#configModifierOrderingPriority) is set to On, the modifiers are sorted by modifier group.



> **Note**
> 
> For printed kitchen tickets and KDS tickets for dynamic view, Modifier ordering priority is always treated as if it is set to On.


The order in which the modifier groups are displayed is determined by the modifier group’s Display Ordering Priority setting:

- If the modifier group has a Display Ordering Priority assigned: These modifier groups are listed first, with the lowest Display Ordering Priority number assigned displayed first, and the highest displayed last.


- If two modifier groups have the same Display Ordering Priority assigned: The modifier group is sorted based on how it’s ordered within the item’s modifier groups list on Toast Web.


- If a modifier group does not have a Display Ordering Priority assigned: The modifier group appears after modifier groups that do have a Display Ordering Priority assigned. The modifier groups are then sorted based on how they are ordered within the item’s modifier groups list on Toast Web.




4. The modifiers are then ordered based on the [Modifier group sorting](devPortalPlatformGuideUiOptionsOmitChunkFromSearchIndex.html#configModifierGroupSorting) setting option:

- Display in order modifiers were added: The modifiers are listed the way they were added by an employee on the order screen.


- Display in order modifiers are listed in their modifier group: The modifiers are listed the same way that they appear within the modifier group on Toast Web.





#### Individual item kitchen tickets



> **Note**
> 
> This setting is in limited release.


The Toast platform allows you to have separate tickets for each item in an order, or to have an order ticket with all items in an order. For example, you have an order with two items, Panini and Burger that both route to the Hot prep station. If using individual item tickets, this results in two tickets, one with Panini and another with Burger. If not using individual item tickets, this results in a single ticket with two items, Panini and Burger. The Individual Item Tickets setting has separate configurations for both [printed](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#platformKitchenIndividualItemTicketsPrinted)and [KDS tickets](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#platformKitchenIndividualItemTicketsKDS). Individual item tickets can apply to printed prep station tickets, and to KDS prep station and expediter tickets, depending on your setup.



> **Note**
> 
> Individual tickets apply differently for items with multiple quantities. Depending on your Individual Item Tickets setting options, you can choose to specify whether items with multiple quantities are consolidated into a single item with a multiple quantity, or as separate items each with a quantity of one. For more information, see [Consolidate identical items](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#platformKitchenConsolidateIdenticalItems).


The Individual Item Tickets setting has two parts for [Print Settings](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#platformKitchenIndividualItemTicketsPrinted) and [KDS Settings](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#platformKitchenIndividualItemTicketsKDS).

##### Print settings

You can choose to print individual item tickets for prep station printed tickets, and also choose to include a prep station ticket that includes all items sent to that prep station for that course, called an *overview ticket*. An overview ticket may also be referred to as a *master* ticket on printed tickets.



> **Note**
> 
> Individual item tickets and overview tickets only apply to printed prep station tickets. Printed expediter tickets always include all items in a course for an order, when configured to [Send to Expediter](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configSendToExpediter).


When configuring how items appear on printed prep station tickets, there are three Print Settings options to choose from:

- Print all items from an order on a single ticket: A single prep station ticket with all items sent to that prep station for that course and order.

![An example of a printed ticket showing all items.](https://doc.toasttab.com/doc/media/kitchen-individual-item-ticket-printed-single.png)


- Print individual tickets with an overview ticket at each prep station: Individual tickets for each item sent to that prep station for that course and order, along with an overview ticket that includes all items sent to that prep station for that course and order.

![An example of printed individual tickets with an overview ticket.](https://doc.toasttab.com/doc/media/kitchen-individual-item-ticket-printed-individual-w-master.png)


- Print individual tickets without an overview ticket at each prep station: Individual tickets for each item sent to that prep station for that course and order. No overview ticket is printed.

![An example of a printed individual tickets.](https://doc.toasttab.com/doc/media/kitchen-individual-item-ticket-printed-individual-wo-master.png)



When using individual tickets, overview tickets, or both, the prep station ticket prints the ticket type at the top, marking it as *Individual* or *Master*.

##### KDS settings

You can choose whether to have all items appear on the same ticket for prep station and expediter KDS devices, only expediter KDS devices, or neither prep station or KDS devices.



> **Note**
> 
> Items only appear on the expediter KDS device if the prep station they are assigned to is configured to [Send to Expediter](platformKitchenConfigReferenceOmitChunkFromSearchIndex.html#configSendToExpediter).


When configuring how items appear on KDS tickets, there are three KDS Settings options to choose from:

- Display all items from an order on a single ticket: A single prep station KDS ticket with all items sent to that prep station for that course and order and a single expediter KDS ticket with all items for that course and order.

![Examples of all items on a single ticket on prep station and expediter KDS devices.](https://doc.toasttab.com/doc/media/kitchen-individual-item-ticket-kds-single.png)


- Display each item on individual tickets at both prep stations and expos: Individual tickets for each item for that course and order sent to that prep station or expediter KDS device.

![Examples of individual item tickets on prep station and expediter KDS devices.](https://doc.toasttab.com/doc/media/kitchen-individual-item-ticket-kds-individual-ps-expo.png)


- Display each item on individual tickets at prep stations only: Individual tickets for each item for that course and order sent to that prep station KDS device and a single expediter KDS ticket with all items for that course and order.

![Examples of individual item tickets on a prep station KDS device and a single ticket on an expediter KDS device.](https://doc.toasttab.com/doc/media/kitchen-individual-item-ticket-kds-individual-ps-only.png)



##### Configuring individual item tickets

Choosing how to configure individual items for printed and KDS tickets can affect how identical items are consolidated. For more information, see [Consolidate identical items](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#platformKitchenConsolidateIdenticalItems)Consolidating identical items.

**Procedure 10.10. To configure individual item tickets for printed and KDS tickets**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Navigate to the Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setuppage.


3. Under the Printed Tickets and Ticket Screen section, navigate to the Individual Item Tickets setting.


4. Select an option for Print Settings.

- Print all items from an order on a single ticket


- Print individual tickets with an overview ticket at each prep station


- Print individual tickets without an overview ticket at each prep station



For more information about these options, see [Print settings](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#platformKitchenIndividualItemTicketsPrinted).


5. Select an option for KDS Settings.

- Display all items from an order on a single ticket


- Display each item on individual tickets at both prep stations and expos


- Display each item on individual tickets at prep stations only



For more information about these options, see [KDS settings](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#platformKitchenIndividualItemTicketsKDS).


6. Save and publish your changes.



#### Consolidate identical items



> **Note**
> 
> This setting is in limited release.




> **Note**
> 
> If you have the [Consolidate menu items](devPortalPlatformGuideUiOptionsOmitChunkFromSearchIndex.html#configCombineItems) setting set to Off, your items appear as they are entered on the order screen and the Consolidate Item with Multiple Quantities setting is ignored. For example, if you enter two individual Panini, they cannot be consolidated at the kitchen level and appear as two individual Panini. If you enter Panini with a quantity of two, they cannot be unconsolidated at the kitchen level and appear as Panini with a quantity of two.


When you send items to the kitchen, you can choose whether multiple of the same item appear as a single line with an indicated quantity, or as individual lines of one item each. For example, if you enter an order with two Panini, consolidating the items appears as one line for Panini with a quantity of two. By not consolidating, the ticket has two Panini items, each with a quantity of one.

The Consolidate Items with Multiple Quantities setting is available on the Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup page under the Printed Tickets and Ticket Screens section.

Here is an example of a consolidated ticket at prep station and expediter KDS devices.

![An example a ticket with consolidated items.](https://doc.toasttab.com/doc/media/kitchen-multi-item-consolidated.png)

Here is an example of non-consolidated tickets at prep station and expediter KDS devices.

![An example of a ticket with items that are not consolidated.](https://doc.toasttab.com/doc/media/kitchen-multi-item-unconsolidated.png)

If you choose to use [individual item kitchen tickets](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#platformKitchenIndividualItemKitchenTickets), each item has a ticket. For this example, consolidated items appear as one ticket for Panini with a quantity of two, while unconsolidated items appear as two tickets for Panini with a quantity of one.

##### Configuring consolidated items with multiple quantities

For the Consolidate Items with Multiple Quantities setting, choose Yes to group all identical items into one item line with a multiple quantity. Choose No to separate identical items into separate lines with a quantity of one each.

**Procedure 10.11. To configure consolidated items with multiple quantities**

1. [Access Toast Web](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Navigate to the Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setuppage.


3. Under the Printed Tickets and Ticket Screen section, navigate to the Consolidate Items with Multiple Quantities setting.


4. Select the best option for your restaurant.

- Yes, consolidate items with multiple quantities as a single entity with an indicated quantity.


- No, show items with multiple quantities as separate entities, each with a quantity of one.




5. Save and publish your changes.



### Text messaging

This section provides procedures and information about sending text messages when an order is fulfilled.

#### Sending text messages on expediter fulfillment

If your kitchen includes a KDS for one or two expediters, you can configure the Toast POS to automatically send SMS text messages when the expediters mark the order fulfilled. For example, to encourage timely pickup, a quick service restaurant might decide to send text messages to guests who place online orders.

Text messages are sent for orders that meet these criteria.

- The order must be entered on a Toast POS device in Table Service or Quick Order mode, on a Toast kiosk, or via the Toast Online Ordering website.


- Recipients for the text messages must be [configured](platformKitchenOperationsAndFulfillmentOmitChunkFromSearchIndex.html#adminConfigureTextMessage) in the Toast Web.


- The order must be fulfilled on an expediter KDS.





> **Note**
> 
> You cannot configure text messages to be sent after fulfillment on a prep station KDS, or for orders entered through the orders API.


When you configure SMS text messaging, you make the following selections.

- Who receives the text message?

You can send text messages to restaurant *guests*, the restaurant *employees* who place the orders, or both. For orders placed on a kiosk, text messages can only be sent to the guests.


- How was the order placed?

You can send text messages for *online orders*, orders placed using *Quick Order* mode or *Table Service* mode, orders placed at a Toast *kiosk*, or any combination.


- What should the message say?

You can customize the default message text that is provided by the Toast POS to meet your needs. To ensure relevance to who receives the message and how the order was placed, you can configure up to seven different messages.



If your kitchen workflow has [two expediters](adminUsingExpo.html), you also specify when to send text messages: only after fulfillment on the level 2 expediter KDS, or after fulfillment on either expediter KDS.

If your kitchen is configured to Enable individual item fulfillment, the text message is sent after all items are marked fulfilled.

In addition, this [Toast Central article](https://central.toasttab.com/s/article/Send-Text-Message-when-Order-is-Fulfilled-1492800294544) provides an overview of sending text messages.

#### Configure text messaging on expediter fulfillment

To configure text messaging, you must have the 6. Web Setup > 6.2 Kitchen / Dining Room Setup access permission. Then, follow these steps.

1. [Access Toast Web ](platformToastPlatformConceptsOmitChunkFromSearchIndex.html#adminAccessToastAdminBackend).


2. Choose Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup to open the Kitchen page. Scroll down to theOrder Ready Text Messaging section.


3. If your restaurant uses two-level fulfillment, you set the Fulfillment Text Level as follows.

- To send a text message after the Level 2 expediter KDS fulfills the order only, select Level 2.


- To send the text message after either expediter KDS fulfills the order, select Level 1. Only one message is sent for each order, and it is triggered by whichever expediter KDS fulfills the order first.




4. The Send Text Message option presents a set of interactive grids for orders placed in different ways. You use each grid to indicate who should receive messages: guests, servers, or both.

For example, to send text messages to guests who place online orders, in the For Online Orders grid you check To Guest. To send text messages to servers who use Quick Order mode to place orders, in the For Quick Orders grid you check To Server.



> **Note**
> 
> For messages to be received, the Toast POS must have an accurate telephone number for an SMS-enabled device.
- Guests supply or confirm a telephone number when they place an order. An example is for an order with a dining option of takeout.


- You enter server telephone numbers with other employee profile information in Toast Web. Servers receive text messages on expediter fulfillment even if they are not signed in to a Toast POS device.






5. Optionally, customize the content of each type of message. To include order-specific information in the messages, you can use the following variables.

- Guest name: `$GUEST` or `$CUSTOMER`


- Restaurant name: `$RESTAURANT`


- Order number: `$ORDER`


- Table number: `$TABLE`



For example, you might want the message for guests who place online orders to read, `$GUEST, your $RESTAURANT order is
          ready.`


6. Save and publish your changes.



