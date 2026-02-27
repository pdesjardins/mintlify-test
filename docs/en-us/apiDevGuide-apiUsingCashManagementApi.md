---
title: "Getting cash entries"
id: apiUsingCashManagementApi
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingCashManagementInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting cash management information"
previousSectionFile: apiDevGuide-apiGettingCashManagementInformationOmitChunkFromSearchIndex.md
previousSectionTitle: "Getting cash management information"
nextSectionFile: apiDevGuide-apiGetCashDeposits.md
nextSectionTitle: "Getting cash deposit entries"
excerpt: "The entries endpoint of the cash management API returns information about the following types of cash entry:"
keywords: ["getting", "cash", "entries", "CASH_IN", "CASH_OUT", "CASH_COLLECTED", "TIP_OUT", "NO_SALE", "PAY_OUT", "UNDO_PAY_OUT"]
procedures: 0
codeExamples: 2
---

The `entries` endpoint of the cash management API returns information about the following types of cash entry:

- `CASH_IN` - A restaurant employee puts cash in a cash drawer. This type of entry represents miscellaneous cash operations that are not handled by standard Toast POS functionality. Note that when a restaurant employee undoes a `CASH_OUT`cash entry, the system posts a `CASH_IN` cash entry for the same amount.


- `CASH_COLLECTED` - At the end of a shift, a restaurant employee puts cash collected during that shift into a cash drawer. This does not include cash transactions that are paid into a cash drawer at the time that the guest pays for a check. Note that when a restaurant employee undoes a `TIP_OUT` cash entry, the system posts a `CASH_COLLECTED` cash entry for the same amount.


- `CASH_OUT` - A restaurant employee removes cash from a cash drawer. This type of entry represents miscellaneous cash operations that are not handled by standard Toast POS functionality. Note that when a restaurant employee undoes a `CASH_IN`cash entry, the system posts a `CASH_OUT` cash entry for the same amount.


- `NO_SALE` - A restaurant employee opens a cash drawer and does not make a change to the cash balance. For example, a restaurant employee might perform a no sale transaction to make change for a guest. The restaurant employee can select a pre-configured reason to explain the nature of the no sale transaction.


- `PAY_OUT` - A restaurant employee removes cash from a cash drawer to pay for goods or services. Pay out reasons are configured in Toast Web. For example, an employee might pay cash for a window washing service.


- `TIP_OUT` - A restaurant employee removes cash from a cash drawer to pay non-cash tips or gratuities to restaurant employees. For example, a tip out entry might pay tips that were entered in credit card payments. Note that when a restaurant employee undoes a `CASH_COLLECTED` cash entry, the system posts a `TIP_OUT` cash entry for the same amount.


- `UNDO_PAY_OUT` - A restaurant employee puts cash in a cash drawer to undo a previous `PAY_OUT` cash entry


- `DRIVER_REIMBURSEMENT` - A restaurant employee removes cash from a cash drawer to pay a delivery driver for delivery driving expenses.


- `CLOSE_OUT_EXACT` - A restaurant employee closes a cash drawer and the close out balance is equal to the expected balance.


- `CLOSE_OUT_OVERAGE` - A restaurant employee closes a cash drawer and the close out balance is greater than the expected balance.


- `CLOSE_OUT_SHORTAGE` - A restaurant employee closes a cash drawer and the close out balance is less than the expected balance.



The following example **curl** command sends a `GET` request to the `entries`endpoint.

**Example 8.1. Get all cash entries made on a specific business date**


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
-H "Toast-Restaurant-External-ID: 4622e7a9-b4be-3fef-9220-b3dad273e0b4" \
https://`[toast-api-hostname]`/cashmgmt/v1/entries?businessDate=20190917
```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e195A5E2A1B1-DA0E-4054-99B6-F867706167E9" className="">(1)</a></div></td>
      <td className=""><div className="">Use the <code className="">Toast-Restaurant-External-ID</code> request parameter to specify the GUID of the restaurant from which to retrieve cash entries. The GUID must be for an individual restaurant, not the GUID for a restaurant group or management group.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e200A5E2A1B1-DA0E-4054-99B6-F867706167E9" className="">(2)</a></div></td>
      <td className=""><div className="">Use the <code className="">businessDate</code> request parameter to specify the date (in <code className="">yyyyMMdd</code> format) on which the cash entries were created.</div></td>
    </tr>
  
The following example shows a `CashEntry` object in the response data from the `entries` endpoint.

**Example 8.2. CashEntry object in entries endpoint response data**


```
[
  {
    "guid": "090f0e10-5469-4e86-a9d7-4c72eca366d7",
    "entityType": "CashEntry",
    "date": "2019-09-17T15:32:49.844+0000",
    "reason": "buy window cleaning supplies",
    "amount": -25,
    "payoutReason": {
      "guid": "9bad959b-250e-4b0d-9b13-a1a52026474c",
      "entityType": "PayoutReason"
    },
    "cashDrawer": {
      "guid": "30795302-5fc9-461c-b314-ac8ea6e55cd5",
      "entityType": "CashDrawer"
    },
    "undoes": null,
    "noSaleReason": null,
    "employee1": {
      "guid": "9659c962-7a8a-43ec-9343-47cafb68e83b",
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "type": "PAY_OUT",
    "employee2": null
  }
]
```



    <tr className="">
      <td className=""><div className=""><a href="#co-d1e24433B240E1-39A5-4C20-8325-985CCE09250C" className="">(1)</a></div></td>
      <td className=""><div className="">The GUID of this <code className="">CashEntry</code> object.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e24633B240E1-39A5-4C20-8325-985CCE09250C" className="">(2)</a></div></td>
      <td className=""><div className="">The date and time when the cash entry was made.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e24833B240E1-39A5-4C20-8325-985CCE09250C" className="">(3)</a></div></td>
      <td className=""><div className="">A descriptive comment entered by the restaurant employee when the cash entry was made. For undone cash entries, a hard-coded reason (such as <code className="">Undo Pay Out</code>) is provided by the system.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e25033B240E1-39A5-4C20-8325-985CCE09250C" className="">(4)</a></div></td>
      <td className=""><div className="">The US currency amount that the restaurant employee removed from (for negative amounts) or added to (for positive amounts) the cash drawer.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e25233B240E1-39A5-4C20-8325-985CCE09250C" className="">(5)</a></div></td>
      <td className=""><div className="">The GUID of the pre-configured pay out reason for this <code className="">PAY_OUT</code> cash entry. The value is <code className="">null</code> if the cash entry is any type other than <code className="">PAY_OUT</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e25533B240E1-39A5-4C20-8325-985CCE09250C" className="">(6)</a></div></td>
      <td className=""><div className="">The GUID of the cash drawer in which the cash entry was made.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e25733B240E1-39A5-4C20-8325-985CCE09250C" className="">(7)</a></div></td>
      <td className=""><div className="">The GUID of the cash entry that was undone. The value is <code className="">null</code> if this cash entry does not undo a previous cash entry.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e25933B240E1-39A5-4C20-8325-985CCE09250C" className="">(8)</a></div></td>
      <td className=""><div className="">The GUID of the pre-configured no sale reason for a <code className="">NO_SALE</code> cash entry. The value is <code className="">null</code> if the cash entry is any type other than <code className="">NO_SALE</code>.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e26133B240E1-39A5-4C20-8325-985CCE09250C" className="">(9)</a></div></td>
      <td className=""><div className="">The GUID or external identifier of the restaurant employee who made the cash entry.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e26333B240E1-39A5-4C20-8325-985CCE09250C" className="">(10)</a></div></td>
      <td className=""><div className="">The cash entry type for this transaction.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className=""><a href="#co-d1e26533B240E1-39A5-4C20-8325-985CCE09250C" className="">(11)</a></div></td>
      <td className=""><div className="">The GUID of the restaurant employee who approved this transaction. The value is <code className="">null</code> if approval was not needed.</div></td>
    </tr>
**Undone Cash Entries**

When restaurant employees undo cash entries, the `reason` and `type` values of the resulting undo cash entries are as follows:

- `CASH_IN` entries are undone by `CASH_OUT` entries that have a `reason`value of `Undo Cash In` and a `type` value of `CASH_OUT`.


- `CASH_OUT` entries are undone by `CASH_IN` entries that have a `reason` value of `Undo Cash Out` and a `type` value of `CASH_IN`.


- `CASH_COLLECTED` entries are undone by `TIP_OUT` entries that have a `reason` value of `Undo Cash Collected` and a `type` value of `TIP_OUT`.


- `TIP_OUT` entries are undone by `CASH_COLLECTED` entries that have a `reason` value of `Undo Tip Out` and a `type` value of `CASH_COLLECTED`.


- `PAY_OUT` entries are undone by `UNDO_PAY_OUT` entries that have a `reason`value of `Undo Pay Out` and a `type` value of `UNDO_PAY_OUT`.



Note that you should include undone tip out cash entries when you are calculating [expected cash deposits](apiDevGuide-apiCalculatingExpectedCashDeposits).

  
