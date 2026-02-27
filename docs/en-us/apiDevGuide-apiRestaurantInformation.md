---
title: "Getting information about a specific restaurant"
id: apiRestaurantInformation
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingRestaurantInfoOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting restaurant info"
previousSectionFile: apiDevGuide-apiRestaurantsInGroup.md
previousSectionTitle: "Getting all restaurants in a management group"
nextSectionFile: apiDevGuide-apiRestaurantOnlineOrderingInfo.md
nextSectionTitle: "Online ordering configuration"
excerpt: "Send a GET request to the /restaurants/v1/restaurants/{restaurantGUID} endpoint of the restaurants API to obtain configuration information for a specific restaurant. The endpoint returns a..."
keywords: ["getting", "information", "about", "specific", "restaurant", "/restaurants/v1/restaurants/{restaurantGUID}", "RestaurantInfo", "General", "West End Grille", "locationName"]
procedures: 0
codeExamples: 2
---

Send a `GET` request to the `/restaurants/v1/restaurants/&#123;restaurantGUID&#125;` endpoint of the restaurants API to obtain configuration information for a specific restaurant. The endpoint returns a `RestaurantInfo` object that contains the following objects and their information:

- `General` object: general information about the restaurant:

- `name` is the restaurant's guest-facing name. For example: `West End Grille`.


- `locationName` is a name used externally to differentiate multiple locations. For example, `Davis Square` might be the location of one of the restaurants in a restaurant group in a city.


- `locationCode` is a code used internally to differentiate multiple locations. It is typically a three or four letter code.


- `description` is a description of the restaurant. This description appears on Toast's website.


- `timeZone` is the name of the restaurant's time zone in the IANA (Internet Assigned Numbers Authority) time zone database.


- `closeoutHour` is the business day cutoff, which is the hour of the day that ends the current business day and starts the next. The value is 0-12 (midnight to noon) and is in the restaurant's time zone. For example, a value of `4` means that 4:00 AM is the close of the current business day. Note that this value is different from the `closeTime` value for a day schedule.


- `managementGroupGuid` is the GUID of the restaurant management group.


- `archived` indicates whether the restaurant has been made inactive on the Toast platform. An example reason that a restaurant is archived is that it was created in error.



Note that the `name`, `timeZone`, and `closeoutHour` values are always populated, but the other values may be null.


- `URLs` object: web addresses for the restaurant:

- `website` is the restaurant's primary (independently-hosted) website.


- `facebook` is the restaurant's Facebook page.To


- `twitter` is the restaurant's Twitter feed.


- `orderOnline` is the restaurant's online ordering page, where guests can place takeout or delivery orders.


- `purchaseGiftCard` is the restaurant's website where guests can purchase gift cards. This value is populated only if the location has Toast gift cards (not a gift card integration).


- `checkGiftCard` is the restaurant's website where guests can find balances and other information about gift cards. This value is populated only if the location has Toast gift cards (not a gift card integration).




- `Location` object: information about the physical location of the restaurant:

- `address1` is the first line of the restaurant's street address.


- `address2` is the second line of the restaurant's street address.


- `city` is the restaurant's city or town.


- `stateCode` is the two-letter abbreviation of the restaurant's state, such as `CA` for California.


- `zipCode` is the restaurant's ZIP or postal code.


- `country` is the two-letter abbreviation of the restaurant's country, such as `US` for United States.


- `phone` is the restaurant's 10-digit phone number.


- `latitude` is the restaurant's north/south geographical coordinate in decimal degrees.


- `longitude` is the restaurant's east/west geographical coordinate in decimal degrees.




- `Schedules` object: information about the restaurant services (such as lunch and dinner) and the schedules for those services over a one-week period. For details on the `Schedules` object, see [Restaurant configuration settings that affect order wait time](apiDevGuide-calculatingOrderWaitTime#apiRestaurantTimeConfigurationSettings).


- `Delivery` object: information about the Toast delivery service provided by the restaurant:

- `enabled` indicates whether the restaurant provides a Toast delivery service.


- `minimum` is minimum order price that qualifies for delivery.


- `area` is the geographic area in which the restaurant provides delivery service. The delivery area is represented by an encoded set of latitude and longitude coordinates that describe a polygon area on a map. The coordinates are encoded using the Google maps encoded polyline algorithm format.




- `OnlineOrdering`object: information about the restaurant's online ordering service, including payment options for online orders. For details on the `OnlineOrdering` object, see [Online ordering configuration](apiDevGuide-apiRestaurantOnlineOrderingInfo).


- `PrepTimes` object: information about the scheduled availability of dining options that are provided by the restaurant. For details on the `PrepTimes` object, see [Restaurant configuration settings that affect order wait time](apiDevGuide-calculatingOrderWaitTime#apiRestaurantTimeConfigurationSettings).



The following example **curl** command sends a `GET` request to the `/restaurants/v1/restaurants/&#123;restaurantGUID&#125;`endpoint.

**Example 6.3. Get configuration of a specific restaurant**


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
dWq4Yzwo007AMgxjH9d241Y-g" \
-H "Toast-Restaurant-External-ID: 76cb1b05-cb1e-4adf-863a-b2a94a5ecdcf" \
https://`[toast-api-hostname]`/restaurants/v1/restaurants/76cb1b05-cb1e-4adf-863a-b2a94a5ecdcf
```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e619B3F37BA5-CBF8-4BF9-B6F3-68E222AD450D" className="">(1)</a></div></td>
      <td className=""><div className="">Use the <code className="">Toast-Restaurant-External-ID</code> request parameter to specify the GUID of the restaurant from which to retrieve configuration information.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e624B3F37BA5-CBF8-4BF9-B6F3-68E222AD450D" className="">(2)</a></div></td>
      <td className=""><div className="">Use the same restaurant GUID in the <code className="">/restaurants/v1/restaurants/&#123;restaurantGUID&#125;</code> endpoint.</div></td>
    </tr>
  
The following example shows the JSON response data for a GET request to the `/restaurants/v1/restaurants/&#123;restaurantGUID&#125;`endpoint.

**Example 6.4. Get restaurant configuration return data**


```
{
  "guid": "76cb1b05-cb1e-4adf-863a-b2a94a5ecdcf",
  "general": {
    "archived": false,
    "name": "Trattoria Roma",
    "locationName": Fenway,
    "locationCode": "",
    "description": "Italian food in a casual atmosphere",
    "timeZone": "America/New_York",
    "closeoutHour": 6,
    "managementGroupGuid": "ae6c32fe-f4d2-4dcc-aa82-f30edac96296"
  },
  "urls": {
    "website": "https://www.example.com",
    "facebook": "",
    "twitter": "https://twitter.com/",
    "orderOnline": "https://www.toasttab.com/trattoria-roma/onlineorders",
    "purchaseGiftCard": "https://www.toasttab.com/trattoria-roma/giftcards",
    "checkGiftCard": "https://www.toasttab.com/trattoria-roma/findcard"
  },
  "location": {
    "address1": "401 Park Drive",
    "address2": "",
    "city": "Boston",
    "stateCode": "MA",
    "zipCode": "02215",
    "country": "US",
    "phone": "1112223333",
    "latitude": 42.344552,
    "longitude": -71.102756
  },
  "schedules": {
    "daySchedules": {
      "1495000000000023": {
        "scheduleName": "Weekdays",
        "services": [
          {
            "name": "Lunch",
            "hours": {
              "startTime": "12:00:00.000",
              "endTime": "15:59:00.000"
            },
            "overnight": false
          },
          {
            "name": "Dinner",
            "hours": {
              "startTime": "16:00:00.000",
              "endTime": "22:00:00.000"
            },
            "overnight": false
          }
        ],
        "openTime": "12:00:00.000",
        "closeTime": "22:00:00.000"
      },
      "1495000000000024": {
        "scheduleName": "Weekends",
        "services": [
          {
            "name": "Lunch",
            "hours": {
              "startTime": "12:00:00.000",
              "endTime": "15:59:00.000"
            },
            "overnight": false
          },
          {
            "name": "Dinner",
            "hours": {
              "startTime": "16:00:00.000",
              "endTime": "22:00:00.000"
            },
            "overnight": false
          }
        ],
        "openTime": "12:00:00.000",
        "closeTime": "22:00:00.000"
      }
    },
    "weekSchedule": {
      "monday": "1495000000000023",
      "tuesday": "1495000000000023",
      "wednesday": "1495000000000023",
      "thursday": "1495000000000023",
      "friday": "1495000000000023",
      "saturday": "1495000000000024",
      "sunday": "1495000000000024"
    }
  },
  "delivery": {
    "enabled": true,
    "minimum": null,
    "area": ""
  },
  "onlineOrdering": {
    "enabled": true,
    "scheduling": false,
    "specialRequests": true,
    "specialRequestsMessage": "No substitutes",
    "paymentOptions": {
      "delivery": {
        "cash": true,
        "ccSameDay": true,
        "ccFuture": false
      },
      "takeout": {
        "cash": true,
        "ccSameDay": true,
        "ccFuture": false,
        "ccInStore": true
      },
      "ccTip": true
    }
  },
  "prepTimes": {
    "deliveryPrepTime": 60,
    "deliveryTimeAfterOpen": 0,
    "deliveryTimeBeforeClose": 0,
    "takeoutPrepTime": 30,
    "takeoutTimeAfterOpen": 0,
    "takeoutTimeBeforeClose": 0,
    "takeoutThrottlingTime": 0,
    "deliveryThrottlingTime": 0
  }
}
```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e566EA079BAD-EBC7-4074-A78B-E75704C9760F" className="">(1)</a></div></td>
      <td className=""><div className="">The GUID of the restaurant from which configuration information is retrieved.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e568EA079BAD-EBC7-4074-A78B-E75704C9760F" className="">(2)</a></div></td>
      <td className=""><div className=""><a href="apiDevGuide-apiRestaurantInformation#restInfoGeneral" className="">General information</a> about the restaurant. The name of this sample restaurant is <code className="">Trattoria Roma</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e570EA079BAD-EBC7-4074-A78B-E75704C9760F" className="">(3)</a></div></td>
      <td className=""><div className="">The <a href="apiDevGuide-apiRestaurantInformation#restInfoURLs" className="">web addresses</a> for the restaurant.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e572EA079BAD-EBC7-4074-A78B-E75704C9760F" className="">(4)</a></div></td>
      <td className=""><div className="">The <a href="apiDevGuide-apiRestaurantInformation#restInfoLocation" className="">physical location</a> of the restaurant.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e574EA079BAD-EBC7-4074-A78B-E75704C9760F" className="">(5)</a></div></td>
      <td className=""><div className="">The <a href="apiDevGuide-apiRestaurantInformation#restInfoSchedules" className="">schedules and services</a> provided by the restaurant. This sample restaurant has two day schedules, named <code className="">Weekdays</code> and <code className="">Weekends</code>. Each day schedule has an <code className="">openTime</code> value that designates when the first service of the day begins and a <code className="">closeTime</code> value for when the last service of the day ends.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e577EA079BAD-EBC7-4074-A78B-E75704C9760F" className="">(6)</a></div></td>
      <td className=""><div className="">The <a href="apiDevGuide-apiRestaurantInformation#restInfoDelivery" className="">delivery service</a> of the restaurant. In this sample restaurant, a delivery service is available.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e579EA079BAD-EBC7-4074-A78B-E75704C9760F" className="">(7)</a></div></td>
      <td className=""><div className="">The <a href="apiDevGuide-apiRestaurantInformation#restInfoOnlineOrdering" className="">online ordering service</a> provided by the restaurant. In this sample restaurant, a delivery service is available, orders are fulfilled as soon as possible, and both cash and credit card payments are accepted for takeout and delivery orders.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#apiRestaurantEnabled" className="">(8)</a></div></td>
      <td className=""><div className="">The <code className="">enabled</code> value in the <code className="">OnlineOrdering</code> object will always be <code className="">true</code> after the restaurant does their initial setup for Toast Online Ordering.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e581EA079BAD-EBC7-4074-A78B-E75704C9760F" className="">(9)</a></div></td>
      <td className=""><div className="">The <a href="apiDevGuide-apiRestaurantInformation#restInfoPrepTimes" className="">scheduled availability of the dining options</a> provided by the restaurant.</div></td>
    </tr>
  
