---
title: "Restaurant availability webhook"
id: apiRxAvailabilityWebhook
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalWebhooksReferenceOmitChunkFromSearchIndex.md
parentSectionTitle: "Webhooks reference"
previousSectionFile: apiDevGuide-apiPartnersWebhook.md
previousSectionTitle: "Partners webhook"
nextSectionFile: apiDevGuide-apiRxOnlineOrderingScheduleWebhook.md
nextSectionTitle: "Restaurant online ordering schedule webhook"
externalReferences: [https://central.toasttab.com/s/article/Troubleshooting-your-Autofire-Device, https://central.toasttab.com/s/article/How-do-I-ensure-scheduled-orders-and-online-orders-fire-automatically-to-the-kitchen-1492811100407, https://central.toasttab.com/s/article/Getting-Started-Online-Ordering#approvalmode, https://central.toasttab.com/s/article/How-do-I-ensure-scheduled-orders-and-online-orders-fire-automatically-to-the-kitchen-1492811100407#Enabling_Order_Auto-Firing_In_Toasts_Back-end]
excerpt: "The restaurant_availability webhook allows you to receive real-time information about a restaurant's ability to accept online orders. The restaurant_availability webhook sends a message when:"
keywords: ["restaurant_availability", "restaurant_availability_toggle", "eventCategory", "eventType"]
procedures: 0
codeExamples: 0
---

The `restaurant_availability` webhook allows you to receive real-time information about a restaurant's ability to accept online orders. The `restaurant_availability` webhook sends a message when:

- The Toast Autofire™ device has stopped approving online orders.


- A third-party online ordering channel (for example, Uber Eats™, DoorDash™, or Grubhub™) was turned on or off, or snoozed (paused). A channel may be paused for 20 or 40 minutes, or until the start of the restaurant's online ordering hours for the next day.



Restaurant availability webhook messages follow the [standard message data schema](apiDevGuide-apiMessageDataSchema). The `restaurant_availability` webhook has two event categories:

- `restaurant_availability`


- `restaurant_availability_toggle`



When you receive a webhook event for the `restaurant_availability` event category, the `eventCategory` value is set to `restaurant_availability` and the `eventType` is set to one of the following:

- [availability_online](apiDevGuide-apiRxAvailabilityWebhook#apiRxAvailabilityOnline)


- [availability_offline](apiDevGuide-apiRxAvailabilityWebhook#apiRxAvailabilityOffline)



When you receive a webhook event for the `restaurant_availability_toggle` event category, the `eventCategory` value is set to `restaurant_availability_toggle` and the `eventType`is set to one of the following:

- [toggle_availability_online](apiDevGuide-apiRxAvailabilityWebhook#apiRxAvailabilityOnlineToggle)


- [toggle_availability_offline](apiDevGuide-apiRxAvailabilityWebhook#apiRxAvailabilityOfflineToggle)





> **Note**
> 
> Multiple webhook messages can be sent from Toast depending on the scenario.


For more information about webhooks, see [Webhook basics](apiDevGuide-apiWebhookBasics) and [Message data schema](apiDevGuide-apiMessageDataSchema).

## Restaurant availability status overview

A restaurant’s availability status is one of the following:

- `ONLINE`:

- The restaurant’s autofire device is online and approving orders.


- The restaurant has stopped snoozing ordering from a third-party online ordering channel. The restaurant is accepting online orders from the channel.


- The restaurant has turned on a third-party ordering channel and is accepting online orders from the channel.




- `OFFLINE`: 

- The restaurant’s autofire device is offline and has stopped approving orders.


- The restaurant has started snoozing ordering from a third-party online ordering channel. The restaurant is not accepting online orders from the channel.


- The restaurant has turned off a third-party ordering channel and is not accepting online orders from the channel.



When a restaurant is `OFFLINE`, you can still place online orders via the orders API. You will receive a 200 response and the restaurant will see the order when they come back `ONLINE`. Toast support recommends waiting to place orders until the restaurant's status is `ONLINE`.





> **Note**
> 
> Placing orders while the restaurant is offline can cause orders to not fire to the kitchen and may result in the restaurant becoming overwhelmed with missed orders once back online. This can contribute to a poor guest ordering experience.


## Autofire device stopped approving online orders

The webhook service checks for updates when:

- An `ONLINE` restaurant is `OFFLINE`. Gone `OFFLINE` means the restaurant’s orders are pending. No order has been approved and autofired for fulfillment in the last five minutes. This indicates that there may be a network issue or other technical problems at the restaurant. For more information, see [Troubleshoot Your Autofire Device](https://central.toasttab.com/s/article/Troubleshooting-your-Autofire-Device).


- An `OFFLINE` restaurant is now `ONLINE`. Coming back `ONLINE` means the restaurant has approved and autofired at least one order in the last five minutes.



The `restaurant_availability` webhook sends updates when a restaurant's autofire device has stopped auto-approving orders for five minutes. The restaurant availability service runs every minute to check if at least one order has been abandoned, meaning it has not approved and autofired an order within a five minute period. For example, if your guest placed an order at 9:02 AM, and your restaurant stopped auto-approving orders at 9:02 AM, the service runs at 9:03 AM but does not fire a webhook event because only one minute has passed since the order was created and not approved. When the service runs at 9:07 AM and the order was still not been approved, the webhook event fires. For more information about autofiring orders, see [Setting up Order Auto-Firing](https://central.toasttab.com/s/article/How-do-I-ensure-scheduled-orders-and-online-orders-fire-automatically-to-the-kitchen-1492811100407).



> **Note**
> 
> If you do not receive any `restaurant_availability`webhook events, the restaurant should be considered `ONLINE`. This assumes you are respecting the restaurant’s available operating hours for both ASAP and scheduled orders placed for future fulfillment.


Restaurants using Toast Online Ordering with [Manual Approval or Approval Rules](https://central.toasttab.com/s/article/Getting-Started-Online-Ordering#approvalmode) configured do not trigger webhook events with the AVAILABILITY_OFFLINE `reasonKey`. Only restaurants that choose to “Send orders directly to the kitchen” are included in the `ONLINE` and `OFFLINE` webhook alerts for this scenario. Restaurants can configure their approval options in Toast Web. These settings do not apply to online ordering integration channels. Orders sent via the orders API are immediately autofired to the kitchen. For more information, see [Orders API limitations](apiDevGuide-portalOrdersApiOverview#ordersAPILimitations).



> **Note**
> 
> This limitation does not apply to the scenario when a restaurant turns a third-party online ordering channel on or off.


### availability_online

The restaurant is online and can accept orders. Attributes in the `availability_online` event’s payload include:


<table>
  <thead>
    <tr>
      <th>Value</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>restaurantGuid</code></td>
      <td>A unique Toast POS identifier for the restaurant. <br/> data type: string <br/> format: uuid</td>
    </tr>
    <tr>
      <td><code>status</code></td>
      <td><code>ONLINE</code> <br/> data type: string</td>
    </tr>
    <tr>
      <td><code>reasonKey</code></td>
      <td><code>AVAILABILITY_ONLINE </code> <br/> The machine-readable reason why the restaurant is available to accept online orders.  <br/> data type: string</td>
    </tr>
    <tr>
      <td><code>reason</code></td>
      <td><code>Restaurant is approving online orders</code> <br/> The human-readable reason why the restaurant is available to accept orders.  <br/> data type: string </td>
    </tr>
  </tbody>
</table>

**Example 9.8. Payload for an availability_online event when a restaurant is online and approving orders**


```
{
  "timestamp": "2021-08-23T16:40:00.063Z",
  "eventCategory": "restaurant_availability",
  "eventType": "availability_online",
  "guid": "bf12cb0a-173a-4e66-bd3c-8121d4a5287f",
  "details": {
    "restaurantGuid": "27d35c6a-7068-49f7-bee0-25e654e1227a",
    "status": "ONLINE",
    "reasonKey": "AVAILABILITY_ONLINE",
    "reason": "Restaurant is approving online orders"
  }
}
```

  
### availability_offline

The restaurant is offline and should not receive orders. Attributes in the `availability_offline` event’s payload include:


<table>
  <thead>
    <tr>
      <th>Value</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>restaurantGuid</code></td>
      <td>A unique Toast POS identifier for the restaurant. <br/> data type: string <br/> format: uuid</td>
    </tr>
    <tr>
      <td><code>status</code></td>
      <td><code>OFFLINE</code> <br/> data type: string </td>
    </tr>
    <tr>
      <td><code>reasonKey</code></td>
      <td><code>AVAILABILITY_OFFLINE</code> <br/> The machine-readable reason why the restaurant is unavailable to accept online orders.  <br/> data type: string</td>
    </tr>
    <tr>
      <td><code>reason</code></td>
      <td><code>Restaurant cannot accept online orders</code> <br/> The human-readable reason why the restaurant is unavailable to accept online orders.  <br/> data type: string </td>
    </tr>
  </tbody>
</table>

**Example 9.9. Payload for an availability_offline event when a restaurant is offline and not approving orders**


```
{
  "timestamp": "2021-08-23T16:40:00.063Z",
  "eventCategory": "restaurant_availability",
  "eventType": "availability_offline",
  "guid": "bf12cb0a-173a-4e66-bd3c-8121d4a5287f",
  "details": {
    "restaurantGuid": "27d35c6a-7068-49f7-bee0-25e654e1227a",
    "status": "OFFLINE",
    "reasonKey": "AVAILABILITY_OFFLINE",
    "reason": "Restaurant cannot accept online orders"
  }
}
```

  
## Third-party online ordering channel has been manually turned on or off

A third-party online ordering channel is any online ordering channel such as Uber Eats, DoorDash, or Grubhub. Restaurants can turn a third-party online ordering channel on or off in Toast Web. The default setting for an online ordering channel is `ONLINE`. For more information about turning on or off a third-party online ordering channel, see [Managing orders from third-party online ordering channels](adminGuide-platformManagingThirdPartyOnlineOrderingChannels).



> **Note**
> 
> A webhook message is sent every time an online ordering channel is turned on or off.


- If a restaurant’s status is `ONLINE`, this means that the restaurant has manually turned on online ordering for that ordering channel. An `ONLINE` status means the restaurant is available for guests to place orders.


- If a restaurant’s status is `OFFLINE`, this means that the restaurant has manually turned off online ordering for that ordering channel. An `OFFLINE` status means the restaurant is unavailable for guests to place orders.





> **Note**
> 
> If the restaurant has manually turned on ordering from third-party online ordering channels on Toast Web, but the restaurant's availability status is showing still `OFFLINE`, check if the autofire device is online and operational. For more information, see [Troubleshoot Your Autofire Device](https://central.toasttab.com/s/article/Troubleshooting-your-Autofire-Device).


### toggle_availability_online

The restaurant has turned on online ordering for that ordering channel. Attributes in the `toggle_availability_online`event’s payload include:


<table>
  <thead>
    <tr>
      <th>Value</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>restaurantGuid</code></td>
      <td>A unique Toast POS identifier for the restaurant. <br/> data type: string <br/> format: uuid</td>
    </tr>
    <tr>
      <td><code>status</code></td>
      <td><code>ONLINE</code> <br/> data type: string</td>
    </tr>
    <tr>
      <td><code>reasonKey</code></td>
      <td><code>TOGGLE_ENABLED</code> <br/> The machine-readable reason why the restaurant is available to accept online orders. <br/> data type: string</td>
    </tr>
    <tr>
      <td><code>reason</code></td>
      <td><code>User enabled integration</code> <br/> The human-readable reason why the restaurant is available to accept orders.  <br/> data type: string </td>
    </tr>
  </tbody>
</table>

**Example 9.10. Payload for a toggle_availability_online event when a restaurant is online and has turned on online ordering**


```
{
  "timestamp": "2021-08-23T16:40:00.063Z",
  "eventCategory": "restaurant_availability_toggle",
  "eventType": "toggle_availability_online",
  "guid": "bf12cb0a-173a-4e66-bd3c-8121d4a5287f",
  "details": {
    "restaurantGuid": "27d35c6a-7068-49f7-bee0-25e654e1227a",
    "status": "ONLINE",
    "reasonKey": "TOGGLE_ENABLED",
    "reason": "User enabled integration"
  }
}
```

  
### toggle_availability_offline

The restaurant has turned off online ordering for that ordering channel. Attributes in the `toggle_availability_offline`event’s payload include:


<table>
  <thead>
    <tr>
      <th>Value</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>restaurantGuid</code></td>
      <td>A unique Toast POS identifier for the restaurant. <br/> data type: string <br/> format: uuid</td>
    </tr>
    <tr>
      <td><code>status</code></td>
      <td><code>OFFLINE</code> <br/> data type: string</td>
    </tr>
    <tr>
      <td><code>reasonKey</code></td>
      <td><code>TOGGLE_DISABLED</code> <br/> The machine-readable reason why the restaurant is unavailable to accept online orders. <br/> data type: string</td>
    </tr>
    <tr>
      <td><code>reason</code></td>
      <td><code>User disabled integration</code> <br/> The human-readable reason why the restaurant is unavailable to accept orders.  <br/> data type: string </td>
    </tr>
  </tbody>
</table>

**Example 9.11. Payload for a toggle_availability_offline event when a restaurant is offline and has turned off online ordering**


```
{
  "timestamp": "2021-08-23T16:40:00.063Z",
  "eventCategory": "restaurant_availability_toggle",
  "eventType": "toggle_availability_offline",
  "guid": "bf12cb0a-173a-4e66-bd3c-8121d4a5287f",
  "details": {
    "restaurantGuid": "27d35c6a-7068-49f7-bee0-25e654e1227a",
    "status": "OFFLINE",
    "reasonKey": "TOGGLE_DISABLED",
    "reason": "User disabled integration"
  }
}
```

  
## Restaurant availability webhook statuses

For a restaurant to be available to accept online orders, the online ordering channel toggle and the autofire device must be on (indicating the restaurant's health as being online). Any combination where the online ordering channel toggle and the autofire device are not both on results in the restaurant being offline and unable to accept online orders. The table below outlines the combination of online ordering toggle availability with the autofire device status and the resulting restaurant status.


<table>
  <thead>
    <tr>
      <th>Online ordering channel toggle availability</th>
      <th>Autofire device status</th>
      <th>Restaurant availability status</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>toggle_availability_online </code> <br/> The online ordering channel toggle is on. </td>
      <td><code>availability_online </code> <br/> Restaurant health is online.</td>
      <td>The restaurant is online and available to accept online orders. </td>
    </tr>
    <tr>
      <td><code>toggle_availability_online </code> <br/> The online ordering channel toggle is on. </td>
      <td><code>availability_offline</code> <br/> Restaurant health is offline.</td>
      <td>The restaurant is offline and not available to accept online orders. </td>
    </tr>
    <tr>
      <td><code>toggle_availability_offline </code> <br/> The online ordering channel toggle is off. </td>
      <td><code>availability_online</code> <br/> Restaurant health is online.</td>
      <td>The restaurant is offline and not available to accept online orders. </td>
    </tr>
    <tr>
      <td><code>toggle_availability_offline </code> <br/> The online ordering channel toggle is off. </td>
      <td><code>availability_offline</code> <br/> Restaurant health is offline.</td>
      <td>The restaurant is offline and not available to accept online orders. </td>
    </tr>
  </tbody>
</table>

## Testing the restaurant availability webhook

### Setup and testing

Before testing, you need an Android tablet or emulator and the most recent Toast APK version in a Sandbox environment. Set up your tablet or emulator as an autofire device. For more information, see [Setting Up an Auto-fire Device](https://central.toasttab.com/s/article/How-do-I-ensure-scheduled-orders-and-online-orders-fire-automatically-to-the-kitchen-1492811100407). Submit a test API order using the Toast orders API to ensure the autofire device is configured correctly.

The following procedures describe how to trigger `OFFLINE` and `ONLINE` webhook events.



> **Note**
> 
> Restaurants must choose to the “Send orders directly to the kitchen” approval rule to receive the `ONLINE` and `OFFLINE` webhook events. For more information, see [Get Started With Online Ordering](https://central.toasttab.com/s/article/Getting-Started-Online-Ordering#approvalmode).


**Procedure 9.1. To trigger an `OFFLINE` webhook event**

1. Ensure that your Toast POS device is online and you have configured an autofire device.


2. Submit a test order using the orders API. For more information, see [Orders API overview](apiDevGuide-portalOrdersApiOverview).


3. Disable the autofire device. For more information on how to disable your autofire device, see [Set up Order Auto-firing](https://central.toasttab.com/s/article/How-do-I-ensure-scheduled-orders-and-online-orders-fire-automatically-to-the-kitchen-1492811100407#Enabling_Order_Auto-Firing_In_Toasts_Back-end).


4. Submit another test order. After five minutes, you receive an `OFFLINE` webhook event.



**Procedure 9.2. To trigger an `ONLINE` webhook event**

1. Enable the autofire device.


2. Submit another test order using the orders API. After one minute, you receive an `ONLINE` webhook event.



