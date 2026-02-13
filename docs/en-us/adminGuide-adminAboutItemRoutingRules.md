---
title: "Using item routing rules"
id: adminAboutItemRoutingRules
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminItemRoutingOmitChunkFromSearchIndex.md
parentSectionTitle: "Item and order routing"
previousSectionFile: adminGuide-platformKDSRoutingUsingAssemblyLines.md
previousSectionTitle: "Routing using assembly lines"
nextSectionFile: adminGuide-adminMonitoringTicketsOtherPrepStations.md
nextSectionTitle: "Monitoring items at other prep stations"
externalReferences: [https://central.toasttab.com/s/article/Creating-Service-Areas-and-Table-Setup-1493049150430]
excerpt: "An item routing rule defines a condition for an order that, if met, requires a change to the order fulfillment workflow. The conditions are the dining option of the order, or the service area."
keywords: ["item", "routing", "rules"]
procedures: 0
codeExamples: 0
---

An item routing rule defines a condition for an order that, if met,
    requires a change to the order fulfillment workflow. The conditions are
    the [*dining option*](adminGuide-adminGlossary.html#glossDiningOption) of
    the order, or the [*service
    area*](adminGuide-adminGlossary.html#glossServiceArea).



> **Note**
> 
> To create item routing rules, you must have the 6. Web
      Setup > 6.2 Kitchen / Dining Room Setup permission.


After specifying the condition for your rule, you then define how
    you want the workflow to change.

- Specify a single prep station to reroute items
        *from*. This is the prep station that you want to
        reroute items from when a condition is met. Set up a separate rule for
        each "from" prep station that needs a workflow change. For example,
        you select a prep station that is currently getting tickets for
        takeout orders.


- Specify one or more prep stations to reroute items
        *to*. This is the new prep station or stations that
        you want the item to be sent to once the condition is met. You can
        specify more than one prep station, including the one that currently
        fulfills the orders.



As soon as you publish the item routing rule, the Toast platform
    applies the rule to all items in an order that meet the specified dining
    option or service area condition.



> **Note**
> 
> If you use the Dining Option[additional modifier
      group](adminGuide-adminUiOptionsReference#configAdditionalModifierGroups) to identify a different dining option for an item in an
      order, that item is routed to the same prep stations as the other items
      in the order.


## Rerouting based on dining option

The dining option that guests select for their meals can have a
      significant effect on which, and how many, prep stations are involved in
      fulfilling the order. With the Toast platform, you can set up item
      routing rules that change the way items are routed for fulfillment based
      on the dining option specified. This means sending the item to an
      additional prep station or a completely different prep station,
      depending on the dining option.

For more information about how you configure dining options, see
      [Dining Options](adminGuide-adminKitchenDiningRoomReference#configDiningOptions).

You can also use KDS devices to display tickets only for specified
      dining options. For more information, see [Filtering tickets on a KDS device](adminGuide-adminKdsTicketDisplayOptions).

### Routing tickets to an additional prep station

One way to change item routing based on dining option is to add
        an additional prep station for items to be assigned to. For example,
        this occurs when a particular dining option requires an extra step or
        process.

For example, you add an employee to package takeout orders and
        set up a *Packer* prep station in the kitchen
        alongside the original *Hot*,
        *Cold*, and *Dessert* prep
        stations. You then add item routing rules that send takeout orders to
        the *Packer* prep station in addition to the
        *Hot*, *Cold*, and
        *Dessert* prep stations.

![A workflow diagram of dine-in orders going from Front of House to three prep stations: Cold, Hot, and Dessert, and takeout orders going to those prep stations and then to a Packer prep station.](https://doc.toasttab.com/doc/media/item_routing_ex1.png)

This requires three different item routing rules for each prep
        station when the dining option for an order is takeout:

- Rerouting items sent to the *Hot* prep
              station to be sent to the *Hot* and
              *Packer* prep stations.


- Rerouting items sent to the *Cold* prep
              station to be sent to the *Cold* and
              *Packer* prep stations.


- Rerouting items sent to the *Dessert*
              prep station to be sent to the *Dessert* and
              *Packer* prep stations.



You do not need to add item routing rules for dine-in orders,
        because that dining option does not require additional or different
        prep stations.

### Routing tickets to a different prep station

Another way to change item routing based on dining option is to
        change which prep station receives orders. For example, you have a
        quick service restaurant. Guests can place orders in person and
        receive them immediately at the counter or over the phone and then
        pick them up at a scheduled time.

To accommodate both dining options as efficiently as possible,
        your kitchen has two identical prep stations, one to fulfill in-person
        (dine-in) orders and the other for phone (takeout) orders. The item
        routing rule sends takeout orders to the Takeout prep station. The
        default behavior is to send items to the Dine-in prep station.

![A workflow diagram of in-person orders going through a no print prep station line and ending in a Toast POS device acting as a quick order, cash drawer, and receipt printer, and of phone in orders starting at the Toast POS device and being sent to a kitchen printer for a separate takeout prep station.](https://doc.toasttab.com/doc/media/item_routing_ex2.png)

For in-person orders, the line cook interacts with the guest to
        fulfill the order. Therefore, tickets do not need to be printed for
        the Dine-in prep station. For phone orders, because the guest is not
        there to work with the line cook, the order is printed at the Takeout
        prep station.

## Rerouting based on service area

You can also choose to change how items are routed based on the
      service area. Item routing rules can be set to change the prep stations
      items are routed to when sent from a specified service area. This means
      sending an item to an additional or completely different prep station,
      depending on what you need for each service area.

For more information about how to configure service areas, see
      this [Toast
      Central article](https://central.toasttab.com/s/article/Creating-Service-Areas-and-Table-Setup-1493049150430).

You can also use KDS devices to display tickets only for specified
      service areas. For more information, see [Filtering tickets on a KDS device](adminGuide-adminKdsTicketDisplayOptions).

### Routing tickets to an additional prep station

One way to change item routing based on service area is to add
        an additional prep station for items to be assigned to. For example,
        this occurs when a particular service area requires an extra step or
        process.

For example, you have a full service restaurant that has a
        separate room for private events. This room uses the service area
        Events. When items are made for this service area, items typically
        shared for a table should be plated individually. You add an item
        routing rule that sends these shared items to a
        *Plating* prep station in addition to the original
        *Hot*, *Cold*, and
        *Dessert* prep stations.

![A workflow diagram of other service area orders going from Front of House to three prep stations: Cold, Hot, and Dessert, and the Events service area orders going to those prep stations and then to a Plating prep station.](https://doc.toasttab.com/doc/media/kitchen-service-area-item-routing-ex1.png)

This requires three different item routing rules for each prep
        station when the service area is Events:

- Rerouting items sent to the *Hot* prep
            station to be sent to the *Hot* and
            *Plating* prep stations.


- Rerouting items sent to the *Cold* prep
            station to be sent to the *Cold* and
            *Plating* prep stations.


- Rerouting items sent to the *Dessert*
            prep station to be sent to the *Dessert* and
            *Plating* prep stations.



You do not need to add item routing rules for other service
        areas, because those service areas do not require additional or
        different prep stations.

### Routing tickets to a different prep station

Another way to change item routing based on service area is to
        change which prep station receives orders.

For example, you have a full service restaurant that includes a
        Bar service area on another floor. You want drinks entered at the Bar
        to be prepared by the Bar prep station, while drinks at other service
        areas to be prepared at the Drinks prep station in the kitchen. The
        item routing rule sends items originally sent to the Drinks prep
        station to the Bar prep station when the service area is Bar. The
        default behavior for all other service areas is to send items to the
        Drinks prep station.

![A workflow diagram of a drink order going to the "Drinks" prep station for most service areas, but the "Bar" prep station when ordered from the "Bar" service area.](https://doc.toasttab.com/doc/media/kitchen-service-area-item-routing-ex2.png)

For all other service area orders, the items should be prepared
        at the Drinks prep station, therefore items do not need to be routed
        to a different prep station.

## Adding item routing rules

Before creating item routing rules, make sure that you configure
      any prep stations, dining options, or service areas you need, and assign
      prep stations to your menu entities. Take into consideration the
      following:

- How many prep stations you will need to reroute from. You
            can only choose a single prep station to reroute from in an item
            routing rule.


- How many dining options or service areas you need to create
            item routing rules for.



The number of prep stations you need to reroute from
      for each dining option or service area determines how many item routing
      rules you need.

Once you determine which prep stations you want to reroute and
      where you want them to reroute to and for which dining options or
      service areas, you can add your item routing rules.

**Procedure 10.16. To create item routing rules**

1. [Access Toast
          Web](adminGuide-adminAccessToastAdminBackend).


2. Choose Kitchen > Kitchen stations > Item
          routing. 


3. Select the + Add button. A row is added
          to the interactive table.


4. Enter an identifying name for the rule.


5. Set the Category for the rule. This is
          either:

- Dining Option


- Service Area




6. From the Condition list, select the
          [dining option](adminGuide-adminKitchenDiningRoomReference#configDiningOptions) or service
          area that your rule applies to.


7. From the Reroute From list, select the
          prep station that you want to reroute items from.



> **Note**
> 
> You can only select one prep station from this list.



8. From the Reroute To list, select the prep
          station or stations that should recieve the tickets when the
          condition is met.

For example, you can choose a different prep station, or
          additional prep stations. If you want to add additional prep
          stations, remember to include the original prep station you selected
          in the previous step.


9. Save and publish your changes.



The Toast platform immediately begins routing tickets to the new
      or additional prep stations when the condition is met.

