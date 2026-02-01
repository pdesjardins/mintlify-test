---
title: "Getting a restaurant's online ordering availability"
id: apiGettingRxOnlineOrderingAvailability
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingRestaurantInfoOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting restaurant info"
previousSectionFile: apiDevGuide-apiGettingOnlineOrderingSchedules.md
previousSectionTitle: "Getting online ordering schedules"
nextSectionFile: apiDevGuide-apiEmployeeInformationOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 7. Employees"
excerpt: "Send a GET request to the /restaurant-availability/v1/availability endpoint of the restaurant availability API to retrieve a restaurant’s availability to accept online orders. The..."
keywords: [GET,restaurant_availability,restaurant_availability webhook,Toast-Restaurant-External-ID]
procedures: 0
codeExamples: 3
---

### Getting a restaurant's online ordering availability

Send a `GET` request to the `/restaurant-availability/v1/availability` endpoint of the restaurant availability API to retrieve a restaurant’s availability to accept online orders. The `restaurant_availability` webhook sends a message when the restaurant’s Toast Autofire™ device has stopped approving online orders.

This is the [fallback endpoint](apiWebhookUsageChecklist.html) for the `[`restaurant_availability`
      webhook](apiRxAvailabilityWebhook.html)`. Toast support recommends using both the API and the webhook.

Toast support recommends querying this API endpoint every ten minutes to ensure you have consistently accurate information about restaurants' availability to accept online orders. Failure to query the restaurant availability API endpoint could result in restaurants being offline for a longer period of time in the event of a missed webhook event.

For more information, see `[``](apiRxAvailabilityWebhook.html)[`restaurant_availability`
      webhook](apiRxAvailabilityWebhook.html)[``](apiRxAvailabilityWebhook.html)`.

**Example 6.9. Get a restaurant's online ordering availability**

In the following example, you send a `GET` request to the `/restaurant-availability/v1/availability` endpoint with the `Toast-Restaurant-External-ID` to retrieve a restaurant location's online ordering availability.

```
curl -X GET \
-H "Authorization: Bearer eyJzI1NiJ9hbGciOiJSU.eyJhd9yaXR5Ij
oiQ1JVTkNIVElNRSIsInJzR3VpZCI6IjE4YzQ5YWJlLWFlODItNGFlYy04ND
M1LWJhYTRjMjVlYTY2MiIsInNjb3BlIjpbImxWQiOlsidG9hc3QiXSwibmFt
aW5nQXV0aGhYm9yIiwib3JkZXJzIiwidXNlcm1nbXQiXSwiZXhwIjoxNDg0M
zg5ODUwLCJqdGkiOiJlMDYzZjJkMy1jNGYyLTRiZjItODJmNi01MTg1NWMzZ
DAxM2YiLCJjbGllbnRfaWQiOiJjcnVuY2h0aW1lIn0.X1_0y9Hzj5F9gdOw2
o6VSYTyZwooAJiFMDmNakbZrtiUdYwLzuLwLpCMQzX5pKYtOqDUz_cetGJL3
txKL1L-K2j1Enoq8An8hEM6e8J0KdAiwrYFO3W3CmWedaoz95K9ghNZVCs28
Td2Sp3Ix3fObxbrvanocx9_OT8S9uM8hdSXmBI_ykTWvOVgK4hO24V3DJy4b
9bz1FtgOvrClhELxCe8dJy7jiwAR60xczlCF5rna98RMLN6zY4ffjmljKFZ6
QV0KkVppWjEiJn7oFHiIylCX1sSg7sddrGatj0xJzts3GJ8u8_lryUNHaEvJ
dWq4Yzwo007AMgxjH9d241Y-g" \[(1)](apiDevGuide-apiGettingRxOnlineOrderingAvailability.html#d1e672109AB21-78E4-4FF7-8E28-AA98325F0F63-co)
-H "Toast-Restaurant-External-ID: 27d35c6a-7068-49f7-bee0-25e654e1227a"  \ [(2)](apiDevGuide-apiGettingRxOnlineOrderingAvailability.html#d1e692109AB21-78E4-4FF7-8E28-AA98325F0F63-co)
"https://[toast-api-hostname]/restaurant-availability/v1/availability
```



(1) Include an authentication token. For more information, see Authentication and restaurant access.

(2) Specify the location GUID of the restaurant whose online ordering availability you want to retrieve.

  
**Example 6.10. Ordering availability response for an online restaurant**

The following example shows an online restaurant location's ordering availability.

```
{
    "restaurantGuid": "00000000-05f4-55a4-0000-0000020f4be3",
    "status": "ONLINE",
    "reasonKey": "AVAILABILITY_ONLINE",
    "reason": "Restaurant is approving online orders"
  }
```

  
**Example 6.11. Ordering availability response for an offline restaurant**

The following example shows an offline restaurant location's ordering availability.

```
{
    "restaurantGuid": "00000000-05f4-55a4-0000-0000020f4be3",
    "status": "OFFLINE",
    "reasonKey": "AVAILABILITY_OFFLINE",
    "reason": "Restaurant cannot accept online orders"
  }
```

  
