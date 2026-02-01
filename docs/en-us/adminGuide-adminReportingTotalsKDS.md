---
title: "Reporting item or ingredient totals with the KDS"
id: adminReportingTotalsKDS
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminKitchenDisplaySystemOmitChunkFromSearchIndex.md
parentSectionTitle: "Using the kitchen display system"
previousSectionFile: adminGuide-platformKitchenUnderstandingItemFulfillmentKDS.md
previousSectionTitle: "Understanding item fulfillment"
nextSectionFile: adminGuide-adminRedisplayingTickets.md
nextSectionTitle: "Redisplaying tickets with recall and unfulfill"
externalReferences: [https://central.toasttab.com/s/article/KDS-All-Day-1493055871075, https://central.toasttab.com/s/article/Production-Item-Count]
excerpt: "Keeping track of how many items or ingredients should be in progress, across all fired items, is an important tactic for efficiency and waste reduction. Mentally tracking totals, however, can be..."
procedures: 0
codeExamples: 0
---

### Reporting item or ingredient totals with the KDS

Keeping track of how many items or ingredients should be in progress, across all fired items, is an important tactic for efficiency and waste reduction. Mentally tracking totals, however, can be difficult to do accurately in a fast-paced, high-volume kitchen. With Toast POS devices, you can use either, or both, of these features to report continuously updated totals for fired items or ingredients on the KDS device.

- All day view, which reports a total for each unique menu item, with or without totals for modifiers.


- Production items, which report totals for specific ingredients. You configure production items independently of menu items so that you can track ingredients that are used in multiple menu items and modifiers.



These features count only fired items, and do not report items that are in sent or scheduled status.

In addition, this [Toast Central article](https://central.toasttab.com/s/article/KDS-All-Day-1493055871075) provides an overview of all day view, and this [Toast Central article](https://central.toasttab.com/s/article/Production-Item-Count) provides an overview of production items.

#### About all day view

When you [enable all day view](adminReportingTotalsKDS.html#adminEnableAllDayView) for your restaurant, a Show All Day View option appears in the KDS device title bar. Employees can use this feature to see totals for identical menu items, with or without information about modifiers, by temporarily switching from the ticket screen to all day view. All day view gives your kitchen employees a way to verify how many of each item they need to be working on at any given time.

An example of the KDS device for a sports bar that specializes in chicken wings and chicken tenders served with different kinds of sauces follows.

![A KDS device showing 13 tickets for wings, tenders, and sandwiches. The Show All Day View option in the title bar is circled.](https://doc.toasttab.com/doc/media/KDS_ticket_view_all_day_circled.png)

To see the current total for each unique menu item with a fired item, you tap Show All Day View. In the following illustration, all day view is configured to show the item names and totals only.

![A KDS device's all day view showing total counts for 10 different menu items, including different size wing and tender orders.](https://doc.toasttab.com/doc/media/KDS_all_day_items.png)

Kitchen employees might prefer this configuration of all day view if a server or packer is responsible for adding the selected sauces to each dish before service.

Another configuration option for all day view adds the course (if any) and the totals for modifiers under each menu item.

![A KDS device's all day view showing total counts for the same 10 menu items, with the course and the selected modifiers shown under each one.](https://doc.toasttab.com/doc/media/KDS_all_day_mods.png)

Kitchen employees might prefer this configuration of all day view if the wings and tenders need to be coated with the selected sauces at the prep station.

To return to the ticket view from all day view you tap Hide All Day View.

#### Update all day view

By default, all day view is enabled for all restaurants to display item names and totals. To update your configuration of all day view, you must have the Web Setup > Kitchen / Dining Room Setup access permission. Then, follow these steps.

1. [Access Toast Web ](adminAccessToastAdminBackend.html).


2. Choose Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup to open the Kitchen page.


3. In the Ticket Screens section, select one of these settings for All Day Display.

- To show a total across tickets for each menu item that currently appears on the KDS device, select Yes, enable All Day Display, grouped by item only.


- To show the course and a subtotal for each variation introduced by modifiers under each menu item total, select Yes, enable All Day Display, grouped by item and sub-grouped by modifiers.


- To remove the Show All Day Viewoption from the KDS device ticket view, select No, do not enable All Day Display.




4. Save and publish your changes.



