---
title: "Assigning a KDS device to a prep station"
id: adminAssignPrepStationKDS
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenConfigurationOmitChunkFromSearchIndex.md
parentSectionTitle: "Kitchen configuration"
previousSectionFile: adminGuide-adminAddKitchenPrinter.md
previousSectionTitle: "Adding a kitchen printer"
nextSectionFile: adminGuide-platformKitchenConfiguringTickets.md
nextSectionTitle: "Configuring tickets"
excerpt: "If you use KDS devices to display tickets, you must have the 6. Web Setup > 6.2 Kitchen / Dining Room Setup access permission to configure each device to display the tickets for a specific prep..."
keywords: ["assigning", "device", "prep", "station"]
procedures: 1
codeExamples: 0
---

If you use KDS devices to display tickets, you must have the
    6. Web Setup > 6.2 Kitchen / Dining Room Setup
    access permission to configure each device to display the tickets for a
    specific prep station. Before you add a prep station to a KDS device,
    consider whether you want or need to display the items sent to that prep
    station on that device.



> **Note**
> 
> The Send to and Sequenced KDS
      fulfillment settings are in limited release.


Prep stations with the Send to setting set to
    Expediter only do not print or show items on prep
    station KDS devices. Prep stations with the Send to
    setting set to Prep station and expediter or
    Prep station only display on prep station KDS
    devices. If you use Sequenced KDS fulfillment and
    require fulfillment at prep stations before expediter devices with this
    setting, items must be fulfilled at a prep station first. If you set the
    Send to setting to Prep station
    only, however, items do not require fulfillment at the
    expediter.



> **Note**
> 
> If a prep station uses the Send to setting
      set to Expediter only, the prep station cannot be
      assigned to a KDS device. Items sent to this prep station appear on the
      expediter KDS device and do not require fulfillment at prep stations
      first.


For more information about the Send to setting,
    see [Sequencing fulfillment by station type and level](adminGuide-platformKitchenUnderstandingItemFulfillmentKDS#platformKDSSequencingFulfillmentByStationTypeAndLevel). For
    more information about the Sequenced KDS fulfillment
    setting, see [Sending items to prep stations, expediters, or both](adminGuide-adminRoutingToPrepStations#platformKitchenSendingToPrepStationExpediterBoth).

**Procedure 10.4. To assign a prep station to a KDS device**

1. [Access the Toast POS Device
        Setup screen](adminGuide-adminConfigureDevice).


2. In the Kitchen Setup section, select Prep
        Stations.


3. To display tickets for a listed prep station on this KDS device,
        check the prep station's name.


4. Select Continue. The system saves the prep
        station assignment.



Repeat these steps for each of your prep station KDS devices.

## About production items

When you [configure production
      items](adminGuide-adminAssignPrepStationKDS#adminConfigureProductionItem) for your restaurant, you create a customized system for
      tracking your most critical ingredients. The KDS reports a continuously
      updated total across fired orders for each production item below the
      individual tickets, including when the count is zero (0). You specify
      which production items you want to track on each of your KDS
      devices.

For example, the manager at a sports bar sets up production items
      to track their specialties, chicken tenders and chicken wings. They
      identify each menu item and modifier that uses chicken tenders, chicken
      wings, or both, and update the Toast platform to indicate how many
      tenders or wings each one requires.

- Chicken tenders come in two sizes: small (2) and large
          (6).


- Chicken wings come in two sizes: small (3) and large
          (6).



Finally, they configure the KDS devices at the Fry prep station
      and expediter station to show real-time totals for these production
      items.

![A KDS showing total counts for chicken wings and chicken tenders production items below the order tickets.](https://doc.toasttab.com/doc/media/kitchen-kds-production-items.png)

The KDS device displays the production items and totals below the
      tickets continuously, including when a total is zero (0). The number
      includes production items that are not yet fulfilled.

If you decide to enable the production item feature for your
      kitchen employees, note the following considerations.

- You can define one or more production items for each menu item
          or modifier.

For example, when the sports bar adds a combo appetizer that
          includes both tenders and wings to the menu, they assign both the
          Chicken Tenders production item and the Chicken Wings production
          item to that new menu item.


- When you define the quantity for a production item, you can
          enter whole numbers or halves.

For example, a production item for ribs can be assigned to a
          full rack menu item with a quantity of 1, and to a rack-and-a-half
          menu item with a quantity of 1.5.


- You can define one quantity for each production item that is
          assigned to a menu item or modifier. As a result, when you assign a
          production item to a menu item that uses size pricing, you can only
          define one quantity for it.

If you need to define different quantities for different item
          sizes, you must set up the sizes as modifiers and then assign the
          production item to each option.


- You cannot assign production items to pre- or
          post-modifiers.


- Production items provide real-time information on the KDS.
          Production item totals are not included in reports or contribute to
          inventory tracking.



## Configure a production item

To configure a production item, you must have the following access
      permissions.

- 4. Restaurant Admin > 4.5 Edit Full
          Menu


- 6. Web Setup > 6.2 Kitchen / Dining Room
          Setup


- 7. Device Setup > 7.3 KDS and Order Screen
          Setup



Then, you complete this series of tasks.

1. [Create a production item](adminGuide-adminAssignPrepStationKDS#adminCreateProdItem) for
          each ingredient that you want to track on the KDS.


2. [Assign the production
          item](adminGuide-adminAssignPrepStationKDS#adminAssignProdItemQuantity) and its quantity to a menu item or modifier.


3. [Specify the production
          items](adminGuide-adminAssignPrepStationKDS#adminSpecifyProdItemDevice) that you want to see totaled on your KDS
          device.



Follow these procedures to complete the configuration of a
      production item.

**Procedure 10.5. To create a production item**

1. Identify an ingredient that you want your kitchen employees to
          track on KDS devices.


2. [Access Toast Web
          ](adminGuide-adminAccessToastAdminBackend).


3. Choose Kitchen > Kitchen stations > Production
          items to open the Production items
          page.


4. Select the + Add button and then enter
          the name of the production item.


5. Repeat this procedure to create another production
          item.

For example, you set up production items for chicken tenders
          and chicken wings.

![The Production Items page in Toast Web, with items set up for chicken tenders and chicken wings.](https://doc.toasttab.com/doc/media/kitchen-tw-add-production-item.png)


6. To change the sequence in which production items display, both
          on this page and along the bottom of the KDS ticket screen, select
          Order. An Order column
          appears in the table so that you can enter a sequence number next to
          each production item.

For example, if you want the Chicken Tenders total to appear
          before the Chicken Wings total on your KDS, enter 1 next to Chicken
          Tenders and then select Done.


7. Save and publish your changes.



After you create one or more production items, you can assign them
      to menu items and modifiers.

**Procedure 10.6. To assign production item quantities to a menu item or
        modifier**

1. Identify a menu item or modifier that uses one of your
          production items and the quantity that it uses.


2. [Access Toast Web ](adminGuide-adminAccessToastAdminBackend)
          and then choose Menus > Bulk management > Advanced
          properties.


3. (Multi-location restaurants only) Choose the locations you
          want to view from the You are viewing dropdown
          menu.


4. Select the name of the menu item.

- To add a production item to this menu item, scroll down to
              the Preparation section of the page.


- To add the production item to a modifier, scroll down to
              the Modifiers section of the page, select
              the name of the modifier group, select the name of the modifier,
              and then select Edit Item. You can then
              scroll down to the Preparation section of
              the page.




5. If you are editing a menu item, select its name to see its
          classic details page. If you are editing a modifier option, select
          its name, then select Edit Item to see the
          classic details page for the modifier's [item
          reference](adminGuide-adminPricingModifierOptions#adminUnderstandingAModifierOptionsItemReference).


6. Scroll down to the Preparation section of
          the page.


7. In the Production Items field, select the
          plus (+) button and then use the dropdown list to select the
          production item.


8. Enter the quantity of the ingredient your kitchen uses to
          prepare this menu item or modifier.

For example, you update the "Small Wings" modifier to identify
          the number of chicken wings in a small order of wings, and the
          "Small Tenders" modifier to identify the number of chicken tenders
          in a small order of tenders.

![The Production Items field with a count of 3 chicken wings identified.](https://doc.toasttab.com/doc/media/kitchen-tw-add-production-item-count-for-item.png)


9. Repeat this procedure to assign another production item and
          its quantity to a menu item or modifier.


10. Save and publish your changes.



After you assign one or more production items to menu items or
      modifiers, you can set up your KDS devices to report the totals for
      specific production items.

**Procedure 10.7. To specify the production items to report on a KDS
        device**

1. Identify the prep stations and expediter seats that need to
          see the real-time totals for production items.


2. On a Toast POS device, select the Toast logo or left arrow in
          the top corner until the Toast POS home screen appears.


3. In the Setup section, select
          Device Setup and go to the Kitchen
          Setup section.


4. Select Production Items, and then select
          each production item that you want to display.


5. Select Continue, and then select the
          Toast logo or left arrow to return to the Toast POS home
          screen.


6. To verify that production item totals appear as expected, in
          the Mode section select Kitchen
          Display System.


7. Repeat this procedure to configure another KDS device to
          report production items.



