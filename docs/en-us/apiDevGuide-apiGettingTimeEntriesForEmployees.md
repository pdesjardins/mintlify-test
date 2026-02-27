---
title: "Getting time entries for employees"
id: apiGettingTimeEntriesForEmployees
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingEmployeeInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting employee information"
previousSectionFile: apiDevGuide-api_get_all_employees.md
previousSectionTitle: "Getting all employees of a restaurant"
nextSectionFile: apiDevGuide-apiGettingShiftAssignmentsForEmployees.md
nextSectionTitle: "Getting shift assignments for employees"
externalReferences: [https://central.toasttab.com/s/article/Enforcing-Scheduling-Time-Clock-Rules-with-Integration-Partners-1492745815961]
excerpt: "To get the time entry records for the..."
keywords: ["/labor/v1/timeEntries", "outDate", "nonCashSales"]
procedures: 0
codeExamples: 0
---

To get the time entry records for the employees at your restaurant, send a `GET` request to the `/labor/v1/timeEntries` resource of the labor API. Time entries record information about the shifts that employees complete. The response contains an array of time entry objects that contain information about the time entries.

If an employee has not clocked out of the work shift, the `outDate` value for the time entry is `null`. The time entry period is not yet complete. Time entry values can change as the server takes new orders and payments during an active work shift.

When the employee clocks out, the `outDate` value is set to the date and time that the employee closed the work shift. The time entry is then complete. At this point, the monetary values in the time entry are static and are not updated by other activities in the restaurant. For example, if an employee has $100 of non-cash sales in their time entry when they clock out, and then an order of $10 non-cash sales is later transferred to the employee, the `nonCashSales` value of the time entry is still $100, not $110. The same applies to tips.

## Example request for employee time entries

The following example **curl** command sends a `GET` request to the `/labor/v1/timeEntries` endpoint.

**Example 7.3. Example request to GET the time entries for restaurant employees**


```
curl -v -X GET \
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
"https://`[toast-api-hostname]`/labor/v1/timeEntries?startDate=
2018-11-14T01:00:00.000-0000&endDate=2018-11-16T01:00:00.000-0000
&includeMissedBreaks=true"
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e15283A590EF-007A-48DE-8B8A-FE6BF2FE2ADA" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Specify the GUID of the restaurant that you want to <code className="font-mono text-sm">GET</code> time entries for. This must be an individual restaurant, not the GUID for a restaurant group.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e15783A590EF-007A-48DE-8B8A-FE6BF2FE2ADA" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">Specify the start and end dates of the time period you want to <code className="font-mono text-sm">GET</code> time entries for. You can select a period of up to 30 days.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e15983A590EF-007A-48DE-8B8A-FE6BF2FE2ADA" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">timeEntries</code> endpoint accepts the <code className="font-mono text-sm">includeMissedBreaks</code> query parameter. If you set the value of <code className="font-mono text-sm">includeMissedBreaks</code> to <code className="font-mono text-sm">true</code>, the <code className="font-mono text-sm">timeEntries</code> endpoint returns <code className="font-mono text-sm">TimeEntryBreak</code> objects for scheduled break periods even if an employee did not take them. The <code className="font-mono text-sm">includeMissedBreaks</code> parameter is optional. If you do not include the parameter, the endpoint returns only breaks that were taken, not breaks that were missed.</p></div></td>
    </tr>
  
## Example response

The following example shows a time entry for an employee.

**Example 7.4. Example response containing an employee time entry**


```
[
  {
    "guid": "26ac616b-b0d2-4d4e-b89b-62291be33d80",
    "entityType": null,
    "externalId": null,
    "nonCashSales": 0,
    "outDate": "2018-11-15T19:17:34.653+0000",
    "overtimeHours": 0,
    "breaks": [
      {
        "breakType": {
          "guid": "8ed442b0-ca52-416d-8976-f941184eba15",
          "entityType": "BreakType"
        },
        "paid": true,
        "inDate": "2018-11-15T14:19:27.043+0000",
        "outDate": "2018-11-15T14:30:35.490+0000",
        "missed": false,
        "auditResponse": true
      },
      {
        "breakType": {
          "guid": "8ed442b0-ca52-416d-8976-f941184eba15",
          "entityType": "BreakType"
        },
        "paid": true,
        "inDate": "2018-11-15T18:13:46.894+0000",
        "outDate": null,
        "missed": true,
        "auditResponse": true
      }
    ],
    "employeeReference": {
      "guid": "a0c9070e-fffd-4e97-b3ea-fc356fbf9224",
      "entityType": "RestaurantUser",
      "externalId": null
    },
    "shiftReference": "56387b8e-78df-47a4-9395-e5e1cb3f04d1",
    "nonCashGratuityServiceCharges": 0,
    "inDate": "2018-11-15T14:14:46.894+0000",
    "regularHours": 5.046599722222222,
    "jobReference": {
      "guid": "8b623183-7d6f-4f7c-babb-e74fe722ad30",
      "entityType": "RestaurantJob",
      "externalId": null
    },
    "tipsWithheld": 0,
    "businessDate": "20181115",
    "cashGratuityServiceCharges": 12.95,
    "createdDate": "2018-11-15T14:14:47.503+0000",
    "deleted": false,
    "deletedDate": null,
    "cashSales": 139.02,
    "hourlyWage": 7.5,
    "nonCashTips": 0,
    "modifiedDate": "2018-11-15T19:17:35.801+0000",
    "declaredCashTips": 30
  }
]
```



    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e21739786C5B-846E-4DDA-823C-AF858E53331A" className="">(1)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">GET</code> request returns an array of time entry objects. Each object contains information about an employee's shift.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e21939786C5B-846E-4DDA-823C-AF858E53331A" className="">(2)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">nonCashSales</code> value shows the total non-cash sales in the orders opened by the employee during the time entry period. The value includes tax amounts, but does not include tip or gratuity amounts.</p> <p className="text-base leading-relaxed">For example, <code className="font-mono text-sm">nonCashSales</code> includes credit card payments, gift card payments, and payments using options that you configure in the Other Payment Options screen of Toast Web.</p> <p className="text-base leading-relaxed">If the <code className="font-mono text-sm">outDate</code> value for the time entry is <code className="font-mono text-sm">null</code>, then the time entry period is not complete, and the sales totals are <code className="font-mono text-sm">0</code>. If the <code className="font-mono text-sm">outDate</code> value for the time entry is set, the sales totals are final and will not change. If you make changes to an order after the time entry is complete, the sales totals for the time entry do not change.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e22139786C5B-846E-4DDA-823C-AF858E53331A" className="">(3)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The time entry object contains information about the shift worked. For example, this <code className="font-mono text-sm">outDate</code> value specifies the date and time that the employee clocked out (the value is <code className="font-mono text-sm">null</code> if the employee has not clocked out).</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e22339786C5B-846E-4DDA-823C-AF858E53331A" className="">(4)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">breaks</code> array contains break type objects that contain information about breaks taken by the employee:</p><ul className="list-disc space-y-2 pl-7 text-base leading-relaxed"><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">breakType</code> is the Toast platform GUID of the type of employee break period. You configure types of employee break periods for your restaurant.</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">inDate</code> specifies when the employee started the break and <code className="font-mono text-sm">outDate</code> is when the employee ended the break. The datetime values are in UTC (Universal Time Coordinated).</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">paid</code> is a Boolean value that indicates whether the employee was paid for the break. If the value is <code className="font-mono text-sm">true</code>, the employee was paid for the break. If the value is <code className="font-mono text-sm">false</code>, the employee was not paid for the break.</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">missed</code> is a Boolean value that indicates whether the employee took the break. If the value is <code className="font-mono text-sm">true</code>, the employee did not take the break. If the value is <code className="font-mono text-sm">false</code>, the employee did take the break.</p></li><li className=""><p className="text-base leading-relaxed"><code className="font-mono text-sm">auditResponse</code> is a Boolean value that indicates whether the employee was asked to take the break. If the value is <code className="font-mono text-sm">true</code>, the employee was asked to take the break. If the value is <code className="font-mono text-sm">false</code>, the employee was not asked to take the break. If the value is <code className="font-mono text-sm">null</code>, either the break type is not configured to use break acknowledgement, or the employee did not respond to the break acknowledgement prompt on the Toast POS device.</p> <p className="text-base leading-relaxed">For information on configuring missed breaks and break acknowledgements, see <a href="adminGuide-portalEmployeeBreaksOverview" className="">Tracking missed breaks and acknowledging breaks</a> in the <em className="">Toast Platform Guide</em> .</p></li></ul></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e22539786C5B-846E-4DDA-823C-AF858E53331A" className="">(5)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">employeeReference</code> value specifies the employee who worked the shift.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#shiftReference" className="">(6)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The GUID of the <code className="font-mono text-sm">Shift</code> object associated with this time entry. The <code className="font-mono text-sm">shiftReference</code> value on a <code className="font-mono text-sm">TimeEntry</code> object is only populated if the restaurant uses Toast's <a href="https://central.toasttab.com/s/article/Enforcing-Scheduling-Time-Clock-Rules-with-Integration-Partners-1492745815961" className="">clock-in enforcement feature</a>, and the employee clocked into their shift within the restaurant's allowed window. Otherwise, the <code className="font-mono text-sm">shiftReference</code> value is null.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e22839786C5B-846E-4DDA-823C-AF858E53331A" className="">(7)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">nonCashGratuityServiceCharges</code> value is the amount of gratuity service charges paid to the employee in non-cash tender (such as credit cards).</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e23039786C5B-846E-4DDA-823C-AF858E53331A" className="">(8)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">jobReference</code> value specifies the job that the employee performed.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e23239786C5B-846E-4DDA-823C-AF858E53331A" className="">(9)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">tipsWithheld</code> value specifies the amount withheld from the employee's credit card tips.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e23439786C5B-846E-4DDA-823C-AF858E53331A" className="">(10)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">cashGratuityServiceCharges</code> value is the amount of gratuity service charges paid in cash to the employee.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e23639786C5B-846E-4DDA-823C-AF858E53331A" className="">(11)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">cashSales</code> value shows the total cash sales in the orders opened by the employee during the time entry period. The cash sales amount includes tax amounts, but does not include tip or gratuity amounts.</p> <p className="text-base leading-relaxed">If the <code className="font-mono text-sm">outDate</code> value for the time entry is <code className="font-mono text-sm">null</code> (the time entry period is not complete), the sales totals are <code className="font-mono text-sm">0</code>. If the <code className="font-mono text-sm">outDate</code> value for the time entry is set, the sales totals are final and will not change. If you make changes to an order after the time entry is complete, the sales totals for the time entry do not change.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e23839786C5B-846E-4DDA-823C-AF858E53331A" className="">(12)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">nonCashTips</code> value lists the total amount of tips paid to the employee in non-cash tender.</p></div></td>
    </tr>
    <tr className="">
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed"><a href="#co-d1e24139786C5B-846E-4DDA-823C-AF858E53331A" className="">(13)</a></p></div></td>
      <td className="px-4 py-4"><div className="space-y-4"><p className="text-base leading-relaxed">The <code className="font-mono text-sm">declaredCashTips</code> value is the amount of tips paid to the employee in cash.</p></div></td>
    </tr>
  
