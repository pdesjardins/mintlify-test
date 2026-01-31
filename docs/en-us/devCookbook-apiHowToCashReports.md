---
title: "Building a cash transactions report"
id: apiHowToCashReports
type: section
documentId: devCookbook
parentSectionFile: devCookbook-cookbookAnalyticsOmitChunkFromSearchIndex.md
parentSectionTitle: "Reports"
previousSectionFile: devCookbook-apiIntegrationChecklistAccounting.md
previousSectionTitle: "Building a sales report"
nextSectionFile: devCookbook-apiHowToReporting.md
nextSectionTitle: "Building a data warehouse integration"
excerpt: "Use the instructions below to build cash transaction reports using information from the Toast platform. This information helps when validating cash drawer values, spotting large cash transactions,..."
procedures: 0
codeExamples: 0
---

### Building a cash transactions report

Use the instructions below to build cash transaction reports using information from the Toast platform. This information helps when validating cash drawer values, spotting large cash transactions, reviewing payout activity, and more.

The integration allows you to provide customers with detailed information about cash transactions, providing restaurants with useful information to understand their daily cash flow.

#### Required scopes

To follow these instructions, you must have the following [scopes](apiScopes.html):

- `cashmgmt:read`


- `config:read`


- `labor.employees:read`


- `restaurants:read`



#### Setup and planning

##### Complete initial integration setup

Review and implement the instructions in [How to build a Toast integration](devPortalCookbookHowToOmitChunkFromSearchIndex.html#apiIntegrationChecklistGeneral).

##### Decide what information your reports will provide

Before you begin development, decide what reports you will build.

This guide describes how to report on the following cash transaction information:

- Addition and removal of miscellaneous cash from cash drawer


- Addition and removal of cash tips from cash drawer


- "No sale" transactions


- Cash payments for goods and services


- Delivery driver reimbursement


- Closeouts


- Deposits


- Expected value in cash drawer


- Anomalous cash transactions



#### Retrieving restaurant information

##### Set up recurring retrieval of configuration and employee information

To display additional information associated with cash transactions, query the following configuration API endpoints at least once per day:

- `/cashDrawers`


- `/noSaleReasons`


- `/payoutReasons`



In addition, query the `/employees`[endpoint](apiEmployeeInformationOmitChunkFromSearchIndex.html#api-get-all-employees) of the labor API at least once per day to retrieve information about the employees associated with cash transactions.

##### Set up recurring retrieval of cash transactions

To report on cash transactions, you need to retrieve cash entries and deposits once per day.

- For cash entries, use the `businessDate` parameter of the `/entries`[endpoint](apiGettingCashManagementInformationOmitChunkFromSearchIndex.html#apiUsingCashManagementApi) of the cash management API.

Toast support recommends that you retrieve cash entries for the previous business day every day.


- For deposits, use the `businessDate` parameter of the `/deposits`[endpoint](apiGetCashDeposits.html) of the cash management API.

Toast support recommends retrieving deposits for the previous business day every day.



##### Consider historical backfill

When a restaurant first connects to your integration, they may expect to see some historical information already displayed in your system.

Define how many days of historical cash transactions you retrieve when a restaurant first connects to your integration.

Toast support recommends that you retrieve twelve weeks of historical cash transactions when a restaurant first connects to your integration.

##### Determine closeout hour

The `closeoutHour` value in the `General`object returned by the [restaurants API](apiRestaurantInformation.html) contains the restaurant's closeout hour.

The default closeout hour is 4:00 a.m. local time unless a Toast employee changes this setting. The `businessDate` value on cash transactions changes after the `closeoutHour`.

Consider [daylight savings time](api_dates_and_timestamps.html#apiDaylightSavingsTime) when interacting with the closeout hour.

#### Building report functionality

##### Associate cash drawer information with cash entries

To display the cash drawer associated with the cash entry, identify the `cashDrawer` value of the `CashEntry`object returned by the `/entries` endpoint of the cash management API.

Then display the `name` of the associated `CashDrawer` object returned by the `/cashDrawers`endpoint of the configuration API.

##### Addition and removal of miscellaneous cash from cash drawer

To report on the addition and removal of miscellaneous cash from the cash drawer, your reports should display cash entries whose `type` values are `CASH_IN` and `CASH_OUT`. Cash entries with `type` of `CASH_IN` or `CASH_OUT` indicate that employees added cash to a cash drawer or removed cash from a cash drawer outside of a transaction.

- Cash entries with a `type` of `CASH_IN`represent employees adding cash into a cash drawer.


- Cash entries with a `type` of `CASH_OUT`represent employees removing cash from a cash drawer.



To display the name of the employee who *initiated* the addition or removal of cash from the cash drawer, match the GUID of the `employee`1 value on the `CashEntry` object with that of the corresponding employee from the `/employees` endpoint of the labor API and display the employee name.

To display the name of the employee who *approved* the addition or removal of cash from the cash drawer, match the GUID of the `employee`2 value on the `CashEntry` object with that of the corresponding employee from the `/employees` endpoint of the labor API and display the employee name.

When a restaurant employee undoes a `CASH_IN` entry, there is a corresponding `CASH_OUT` entry. In that `CASH_OUT` entry, the `undoes` value contains the GUID of the original `CASH_IN` transaction. Similarly, when a restaurant employee undoes a `CASH_OUT` entry, there is a corresponding `CASH_IN` entry. In that `CASH_IN`entry, the `undoes` value contains the GUID of the original `CASH_OUT` transaction. If the `undoes` value on a cash entry contains information, your reports should match this cash entry with the original entry it undoes. The `CASH_IN` and corresponding `CASH_OUT` entries may occur on different business days.

##### Addition and removal of cash tips from cash drawer

To report on the addition and removal of miscellaneous cash from the cash drawer, your reports should display cash entries whose `type` values are `CASH_COLLECTED` and `TIP_OUT`.

- Cash entries whose `type` is `CASH_COLLECTED` represent employees adding cash tips into a cash drawer. This does not include cash transactions that are paid into a cash drawer at the time that the guest pays for a check.


- Cash entries whose `type` is `TIP_OUT`represent employees removing cash from a cash drawer to pay non-cash tips or gratuities to restaurant employees. For example, a tip out entry might pay tips that were entered in credit card payments.



To display the name of the employee who *performed* the shift review that created the cash entry, match the GUID of the `employee`1 value on the `CashEntry` object with that of the corresponding employee from the `/employees` endpoint of the labor API and display the employee name.

To display the name of the employee who is the *subject of* the shift review that created the cash entry, match the GUID of the `employee2` value on the `CashEntry`object with that of the corresponding employee from the `/employees` endpoint of the labor API and display the employee name.

When a restaurant employee undoes a `CASH_COLLECTED`entry, there is a corresponding `TIP_OUT` entry. In that `TIP_OUT` entry, the `undoes` value contains the GUID of the original `CASH_COLLECTED` transaction. Similarly, when a restaurant employee undoes a `TIP_OUT` entry, there is a corresponding `CASH_COLLECTED` entry. In that `CASH_COLLECTED` entry, the `undoes` value contains the GUID of the original `TIP_OUT` transaction. If the `undoes` value on a cash entry contains information, your reports should match this cash entry with the original entry it undoes. The `CASH_COLLECTED` and corresponding `TIP_OUT`entries may occur on different business days.

##### "No sale" transactions

To report on the addition and removal of miscellaneous cash from the cash drawer, your reports should display cash entries whose `type` value is `NO_SALE`.

A restaurant employee opens a cash drawer and does not make a change to the cash balance. For example, a restaurant employee might perform a "no sale" transaction to make change for a guest. The restaurant employee can select a pre-configured reason to explain the nature of the no sale transaction.

To display the reason the employee performed the "no sale" transaction, display the `name` of the `NoSaleReason` object associated with the `noSaleReason` value on the cash entry. The `/noSaleReasons` endpoint of the configuration API returns no-sale reasons.

To display the name of the employee who initiated the cash transaction, match the GUID of the `employee`1 value on the `CashEntry` object with that of the corresponding employee from the `/employees` endpoint of the labor API and display the employee name.

##### Cash payments for goods and services

To report on cash payments for goods and services, your reports should display cash entries whose `type` values are `PAY_OUT` and `UNDO_PAY_OUT`.

Cash entries whose `type` is `PAY_OUT`represent employees removing cash from a cash drawer to pay for goods or services. For example, an employee might pay cash for a window washing service.

To display the reason the employee performed the payout transaction, display the `name` of the `PayoutReason` object associated with the `payoutReason` value on the cash entry. The `/payoutReasons` endpoint of the configuration API returns payout reasons.

To display the name of the employee who *initiated* the payout transaction, match the GUID of the `employee`1 value on the `CashEntry` object with that of the corresponding employee from the `/employees`endpoint of the labor API and display the employee name.

To display the name of the employee who *approved* the payout transaction, match the GUID of the `employee`2 value on the `CashEntry` object with that of the corresponding employee from the `/employees`endpoint of the labor API and display the employee name.

When a restaurant employee undoes a `PAY_OUT` entry, there is a corresponding `UNDO_PAY_OUT` entry. In that `UNDO_PAY_OUT` transaction, the `undoes` value contains the GUID of the original `PAY_OUT` transaction. If the `undoes` value on a cash entry contains information, your reports should match this cash entry with the original entry it undoes. The `PAY_OUT` and corresponding `UNDO_PAY_OUT`entries may occur on different business days.

##### Delivery driver reimbursement

To report on cash reimbursement of delivery drivers, your reports should display cash entries whose `type` value is `DRIVER_REIMBURSEMENT`.

Cash entries whose `type` is `DRIVER_REIMBURSEMENT` represent employees removing cash from a cash drawer to pay a delivery driver for delivery driving expenses.

To display the name of the employee who *performed* the shift review that created the driver reimbursement transaction, match the GUID of the `employee`1 value on the `CashEntry` object with that of the corresponding employee from the `/employees` endpoint of the labor API and display the employee name.

To display the name of the employee who is the *subject of* the shift review that created the driver reimbursement transaction, match the GUID of the `employee`2 value on the `CashEntry` object with that of the corresponding employee from the `/employees` endpoint of the labor API and display the employee name.

##### Closeouts

To report on when employees close a cash drawer, your reports should display cash entries whose `type` value is `CLOSE_OUT_EXACT`, `CLOSE_OUT_OVERAGE`, and `CLOSE_OUT_SHORTAGE`.

- If the cash drawer's close out balance is equal to the expected balance, the `type` of the cash entry is `CLOSE_OUT_EXACT`.


- If the cash drawer's close out balance is greater than the expected balance, the `type` of the cash entry is `CLOSE_OUT_OVERAGE`.


- If the cash drawer's close out balance is less than the expected balance, the `type` of the cash entry is `CLOSE_OUT_SHORTAGE`.



To display the name of the employee who initiated the cash transaction, match the GUID of the `employee`1 value on the `CashEntry` object with that of the corresponding employee from the `/employees` endpoint of the labor API and display the employee name.

##### Deposits

To report on cash deposits from the previous business day, display the deposits you retrieved from the `/deposits` endpoint of the cash management API. The `amount` value indicates the amount of cash deposited in the cash drawer.

To display the name of the employee who deposited the cash, match the GUID of the `employee` value on the `Deposit`object with that of the corresponding employee from the `/employees` endpoint of the labor API and display the employee name.

##### Expected cash balance in cash drawer

Follow [these instructions](apiCalculatingExpectedCashDeposits.html) to report on the expected cash balance in a cash drawer at the end of a business day.

##### Anomalous cash transactions

Consider flagging cash transactions that restaurants may consider noteworthy.

For example, your service may allow restaurants to configure a dollar threshold that they consider to be a high-dollar cash transaction. Consider highlighting cash transactions whose value is greater than this threshold.

You can use the `Schedules` object in the [restaurants API](apiRestaurantInformation.html) to determine a restaurant's hours. Consider highlighting cash transactions that occur after hours.

