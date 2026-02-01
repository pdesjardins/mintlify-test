---
title: "Text messaging"
id: platformKitchenTextMessaging
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenConfigurationOmitChunkFromSearchIndex.md
parentSectionTitle: "Kitchen configuration"
previousSectionFile: adminGuide-platformKitchenConfiguringTickets.md
previousSectionTitle: "Configuring tickets"
nextSectionFile: adminGuide-adminItemRoutingOmitChunkFromSearchIndex.md
nextSectionTitle: "Item and order routing"
externalReferences: [https://central.toasttab.com/s/article/Send-Text-Message-when-Order-is-Fulfilled-1492800294544]
excerpt: "This section provides procedures and information about sending text messages when an order is fulfilled."
keywords: [text,messaging]
procedures: 0
codeExamples: 0
---

### Text messaging

This section provides procedures and information about sending text messages when an order is fulfilled.

#### Sending text messages on expediter fulfillment

If your kitchen includes a KDS for one or two expediters, you can configure the Toast POS to automatically send SMS text messages when the expediters mark the order fulfilled. For example, to encourage timely pickup, a quick service restaurant might decide to send text messages to guests who place online orders.

Text messages are sent for orders that meet these criteria.

- The order must be entered on a Toast POS device in Table Service or Quick Order mode, on a Toast kiosk, or via the Toast Online Ordering website.


- Recipients for the text messages must be [configured](platformKitchenTextMessaging.html#adminConfigureTextMessage) in the Toast Web.


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

To configure text messaging, you must have the 6. Web Setup \> 6.2 Kitchen / Dining Room Setup access permission. Then, follow these steps.

1. [Access Toast Web ](adminAccessToastAdminBackend.html).


2. Choose Kitchen \> Printers, tickets, & KDS devices \> Kitchen and ticket setup to open the Kitchen page. Scroll down to theOrder Ready Text Messaging section.


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



