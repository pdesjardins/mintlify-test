---
title: "Data export field reference"
id: adminDataExportFieldReference
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformDataExportFilesOmitChunkFromSearchIndex.md
parentSectionTitle: "Data export files"
previousSectionFile: adminGuide-adminDataExportSecurity.md
previousSectionTitle: "Security"
nextSectionFile: adminGuide-devPortalPlatformGuideGuestsOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 13. Guests"
excerpt: "This section explains the data included in Toast data export reports."
procedures: 0
codeExamples: 0
---

This section explains the data included in Toast data export reports.

### Accounting data export

The accounting data export includes the revenue amounts for each general ledger (GL) code that you have configured for your restaurant during one business day. The file name of the accounting data export is `AccountingReport.xls`.

The following table shows details on what the accounting data export contains.

| Field | Description | Data Type | 
| --- | --- | --- |
| From | Start Date | Date (MM/DD/YYYY HH:MM:SS) | 
| To | End Date | Date (MM/DD/YYYY HH:MM:SS) | 
| Location | Restaurant Location | String | 
| GL Account | Assigned general ledger (GL) code | Integer | 
| Description | Text Description | String | 
| Amount | Currency amount | Number (two digits) Formatted USD | 

### All items data export

The all items data export includes information about all of the items in the menu for your restaurant. The file name of the all items data export is `AllItemsReport.csv`.

The following table shows details on what the all items data export contains.

| Field | Description | Data Type | 
| --- | --- | --- |
| Master ID | Item Master ID | Long | 
| Item ID | Item ID | Long | 
| Parent ID | Parent Item ID | Integer | 
| Menu Name | Menu Name | String | 
| Menu Group | Menu Group Name | String | 
| Subgroup | Menu Subgroup Name | String | 
| Menu Item | Menu Item Name | String | 
| Avg Price | Average Net Price of item | Number (5 decimals) | 
| Item Qty (incl voids) | Item Quantity including voids | Number (5 decimals) | 
| % of Ttl Qty (incl voids) | Percent of Total Quantity including voids | Number (5 decimals) | 
| Gross Amount (incl voids) | Gross amount of Item sold including voids | Number (2 digits) | 
| % of Ttl Amt (incl voids) | Percent of Total Gross Amount including voids | Number (5 decimals) | 
| Item Qty | Item Quantity | Number (5 decimals) | 
| Gross Amount | Gross Amount excluding voids | Number (5 decimals) | 
| Void Qty | Void quantity of Item | Number (5 decimals) | 
| Void Amount | Void Amount Value of Item | Currency (2 digits) | 
| Discount Amount | Discount Value of Item | Currency (2 digits) | 
| Net Amount | Net Amount of Item (Gross less discount) | Currency (2 digits) | 
| # Orders | Number of Orders Item appears upon | Integer | 
| % of Ttl # Orders | Orders as a percent of Menu Group total orders | Number (5 decimals) | 
| % Qty (Group) | Items as a percent of Menu Group total items | Number (5 decimals) | 
| % Qty (Menu) | Items as a percent of Menu total items | Number (5 decimals) | 
| % Qty (All) | Items as a percent of All total items | Number (5 decimals) | 
| % Net Amt (Group) | Net amount as a percent of Total Menu Group Net Amount | Number (5 decimals) | 
| % Net Amt (Menu) | Net amount as a percent of Total Menu Net Amount | Number (5 decimals) | 
| % Net Amt (All) | Net amount as a percent of Total Net Amount | Number (5 decimals) | 

### Cash management data export

The cash management data export includes information about cash payments made at your restaurant. The file name of the cash management data export is `CashEntries.csv`.

The following table shows details on what the cash management data export contains.

| Field | Description | Data Type | 
| --- | --- | --- |
| Location | Restaurant Location | String | 
| Entry Id | Entry ID | String | 
| Created Date | Date | Date (MM/DD/YYYY HH:MM:SS) | 
| Action | Specific Cash Action | String | 
| Amount | Amount | Number (2 digits) | 
| Cash Drawer | Assigned Cash Drawer Name | String | 
| Payout Reason | Reason | String | 
| Comment | Comment | String | 
| Employee | Employee Name who created entry | String | 
| Employee 2 | Employee Name who received Amount | String | 
| Payout Reason | A description of the reason for the cash payment | String | 

### Check details data export

The check details data export includes information about about the checks in the orders placed at your restaurant. The file name of the checks data export is `CheckDetails.csv`.

The following table shows details on what the check details data export contains.

| Field | Description | Data Type | 
| --- | --- | --- |
| Location Code | This field is not used. | This field is not used. | 
| Opened Date | The date on which the check was created. | Date (MM/DD/YY) | 
| Opened Time | The time of day that the check was created, in twelve hour format. | Time (hh:mm a) | 
| Item Description | A comma-separated list of the text descriptions of each item in the check. | String | 
| Server | The name of the server who created the check. | String | 
| Tax | The currency amount of tax payments applied to the check. | Currency (two decimal places) | 
| Tender | The method of payment for the check. | String | 
| Check Id | The unique identifier for the check. | String | 
| Check # | The numeric identifier for the check. | Integer | 
| Total | The total price of the check, in US dollars. | Currency (two decimal places) | 
| Customer Family | This field is not used. | This field is not used. | 
| Table Size | The number of customers whose orders are part of the check. | Integer | 
| Discount | The currency amount that the price of the check was reduced because of discounts. | Currency (two decimal places) | 
| Reason of Discount | A description of the discount that was applied to the check. | String | 
| Link | The URL of the check image. | String | 
| Customer Id | The unique identifier of the customer associated with the check. | String | 
| Customer | The name of the customer associated with the check. | String | 
| Customer Phone | The telephone number of the customer associated with the check. | String | 
| Customer Email | The email address of the customer associated with the check. | String | 

### Item modifier selection data export

The item modifier data export includes information about the modifiers applied to items ordered at your restaurant. The file name of the item modifier selection data export is `ModifiersSelectionDetails.csv`.

The following table shows details on what the item modifier data export contains.

| Field | Description | Data Type | 
| --- | --- | --- |
| Location | Restaurant Location | String | 
| Order Id | Order ID | Long | 
| Order # | Order Number | Integer | 
| Sent Date | Timestamp for Item Send Time | Date (MM/DD/YYYY HH:MM:SS) | 
| Order Date | Timestamp for Order Open Time | Date (MM/DD/YYYY HH:MM:SS) | 
| Check Id | Check ID | Long | 
| Server | Name of Server who created order | String | 
| Table | Number of Table | Integer | 
| Dining Area | Name of Dining Area | String | 
| Service | Daypart | String | 
| Dining Option | Dining Options (defined by restaurant) | String | 
| Item Selection Id | Item Selection ID | Long | 
| Modifier Id | Modifier ID | Long | 
| Master Id | Item Master ID | Long | 
| Modifier SKU | Modifier SKU | String | 
| Modifier | Modifier Name | String | 
| Option Group ID | Modifier Option Group ID | Long | 
| Option Group Name | Modifier Option Group Name | String | 
| Parent Menu Selection Item ID | Parent Item Selection ID | Long | 
| Parent Menu Selection | Parent Item Selection Name | String | 
| Sales Cateogry | Sales Category Name | String | 
| Gross Price | Gross Price not including taxes | Number (2 decimals) | 
| Discnt | Discount | Number (2 decimals) | 
| Net Price | Net Price (Gross Price less Discount) | Number (2 decimals) | 
| Qty | Quantity | Number (4 decimals) | 
| Void? | True or False | Boolean | 
| Void Reason ID | Void Reason ID | Long | 
| Void Reason | Reason for void | String | 

### Item selection data export

The item selection data export includes information about the items ordered at your restaurant. The file name of the item selection data export is `ItemSelectionDetails.csv`.

The following table shows details on what the item selection data export contains.

| Field | Description | Data Type | 
| --- | --- | --- |
| Location | Restaurant Location | String | 
| Order Id | Order ID | Long | 
| Order # | Order Number | Integer | 
| Sent Date | Timestamp for Item Send Time | Date (MM/DD/YYYY HH:MM:SS) | 
| Order Date | Timestamp for Order Open Time | Date (MM/DD/YYYY HH:MM:SS) | 
| Check Id | Check ID | Long | 
| Server | Name of the server who created order | String | 
| Table | Number of Table | Integer | 
| Dining Area | Name of Dining Area | String | 
| Service | Daypart | String | 
| Dining Option | Dining Options (defined by restaurant) | String | 
| Item Selection Id | Item Selection ID | Long | 
| Item Id | Item ID | Long | 
| Master Id | Item Master ID | Long | 
| SKU | SKU | String | 
| Menu Item | Item Name | String | 
| Menu Subgroup(s) | Item Subgroup Name | String | 
| Menu Group | Item Group Name | String | 
| Menu | Menu Name | String | 
| Sales Category | Sales Category Name | String | 
| Gross Price | Gross Sale Price of Item | Number (2 decimals) | 
| Discnt | Discount | Number (2 decimals) | 
| Net Price | Net Price (Gross - Discount) | Number (2 decimals) | 
| Qty | Quantity | Number (4 decimals) | 
| Tax | Taxes | Number (5 decimals) | 
| Void? | True or False | Boolean | 
| Deferred | Indicates whether the item has been purchased but not delivered. For example, a gift card is a deferred item. | Boolean | 
| Tax Exempt | Indicates whether tax payments are required for the check. | Boolean | 
| Tax Inclusion Option | Indicates whether tax payments are included in the check amount. | String | 
| Dining Option Tax | A description of tax payments applied because of the dining option for the check. | String | 
| Tab Name | A name assigned to the check. | String | 

### Kitchen details data export

The kitchen details data export includes information about the kitchen tickets at your restaurant. The file name of the kitchen data export is `KitchenTimings.csv`.

The following table shows details on what the kitchen details data export contains.

| Field | Description | Data Type | 
| --- | --- | --- |
| Location | The location name. | String | 
| ID | The unique identifier for the check. | String | 
| Server | The name of the employee who created the check. | String | 
| Check # | The numeric identifier for the check. | Integer | 
| Table | The number of the table, if available. | Integer | 
| Check Opened | The time of day that the check was opened, in twelve-hour format. For example: `10/22/19 4:22
          PM`. | Date (MM/DD/YY h:mm AM|PM) | 
| Station | The prep station that received the ticket. In the Toast POS system, a prep station represents the location of a kitchen printer or KDS device that receives orders for fulfillment. | String | 
| Expediter Level | The [Two-Level Fulfillment](adminUsingExpo.html#adminConfigureExpediter)setting for the expediter: `1` for single level or `2` for two levels. | Integer | 
| Fired Date | The time of day that the ticket was fired, in twelve-hour format. | Date (MM/DD/YY h:mm AM|PM) | 
| Fulfilled Date | The time of day that the ticket was fulfilled, in twelve-hour format. | Date (MM/DD/YY h:mm AM|PM) | 
| Fulfillment Time | The amount of time it took for the ticket to be fulfilled. The duration is calculated by subtracting the Fired Date from the Fulfilled Date. For example: `2 weeks, 1 day, 22
          hours, 1 minute and 6 seconds`. | String | 
| Fulfilled By | The name of the employee who fulfilled the ticket. | String | 

### Labor data export

The labor data export includes information about the shifts worked by employees at your restaurant. The file name of the labor data export is `TimeEntries.csv`.

The following table shows details on what the labor data export contains.

| Field | Description | Data Type | 
| --- | --- | --- |
| Location | Restaurant location. You can set the location name for a restaurant in Toast Web. | String | 
| Location Code | Restaurant location code. You can set the location code for a restaurant in Toast Web. | String | 
| Id | Labor Event ID. | Long | 
| GUID | The unique identifier for this labor event, assigned by the Toast POS. | String | 
| Employee Id | Employee ID (Toast). This field is for Toast internal use only. | Integer | 
| Employee GUID | The unique identifier for the employee, assigned by the Toast POS. | String | 
| Employee External Id | Employee ID (Restaurant). | String | 
| Employee | Employee Name. | String | 
| Job Id | Job or position ID (Toast). This field is for Toast internal use only. | Long | 
| Job GUID | The unique identifier for the job, assigned by the Toast POS. | String | 
| Job Code | Job or position code (specified by restaurant). | Integer | 
| Job Title | Job title name (specified by restaurant). For example, `Cook` or `Server`. | String | 
| In Date | A timestamp indicating when an employee clocked in. For example: `9/20/17 10:44 AM` | Date (M/D/YY HH:mm AM|PM) | 
| Out Date | A timestamp indicating when an employee clocked out. For example: `9/20/17 10:15 PM` | Date (M/D/YY HH:mm AM|PM) | 
| Total Hours | Hours calculated. | Number (2 digits) | 
| Unpaid Break Time | Unpaid break time calculated | Number (2 digits) | 
| Paid Break Time | Paid break time calculated | Number (2 digits) | 
| Payable Hours | Hours calculated (`Total Hours` less `Unpaid Break Time`). | Number (2 digits) | 
| Cash Tips Declared | Total tips paid with cash. | Number (2 digits) | 
| Non Cash Tips | Total tips not paid with cash. For example, tips paid with a credit card or other payment methods. | Number (2 digits) | 
| Total Gratuity | Total gratuities from checks. | Number (2 digits) | 
| Total Tips | Total tips calculated (`Cash Tips Declared`plus `Non Cash Tips`). | Number (2 digits) | 
| Tips Withheld | The amount withheld from an employee's credit card tips and gratuities during the time entry. | Number (2 digits) | 
| Wage | Wage per hour. | Number (2 digits) | 
| Regular Hours | Number of non-overtime hours. | Number (2 digits) | 
| Overtime Hours | Number of overtime hours. | Number (2 digits) | 
| Regular Pay | The amount that an employee is paid for non-overtime hours in the time entry. | Number (2 digits) | 
| Overtime Pay | The amount that an employee is paid for overtime hours in the time entry. | Number (2 digits) | 
| Total Pay | The amount paid to an employee for non-overtime and overtime hours. | Number (2 digits) | 

### Menu data export

The menu data export includes two types of information:

- Information about each menu item at your restaurant.


- Information about the premodifiers and postmodifiers created at your restaurant.



The file name of the menu data export is `MenuExport_<em>[export file
  identifier]</em>.json`. The menu data export is in JavaScript Object Notation (JSON) format. For information about downloading data export files, see [Downloading data export files](downloading_data_export_files.html).



> **Note**
> 
> The JSON format of the menu data export is significantly different than the spreadsheet formats of other Toast POS data exports. JSON is optimized for use by software and the menu data export is intended to assist in integration with Toast POS API clients.


#### Menus

This section describes information about each menu entity at your restaurant.

##### Menu

The following table shows the information about each menu at your restaurant from from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| entityType | The type of the menu component described by this JSON object. The value for a menu object is `Menu`. | String | 
| name | A descriptive identifier for the menu. For example, `Food` or `Drinks`. | String | 
| guid | The unique identifier for the menu, assigned by the Toast POS. | String | 
| description | A written description of the menu. | String | 
| groups | A JSON array of [MenuGroup](adminDataExportFieldReference.html#menuExportMenugroup) objects. | JSON array | 
| idString | This field is for Toast internal use only. | String | 
| orderableOnline | Indicates whether the menu is available for online ordering. Valid values are `true` and `false`. This field is a Boolean version of the orderableOnlineStatus field. | Boolean | 
| orderableOnlineStatus | Indicates whether the menu is available for online ordering. Valid values are `YES` and `NO`. This field is a string version of the orderableOnline field. | String | 
| visibility | Indicates where the menu is displayed and who can see it. Values are:- `ALL` - The menu is visible to everyone. For example, the menu is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.
- `POS_ONLY` - The menu is visible only on Toast POS devices (including kiosks).
- `NONE` - The menu is hidden from everyone.

 | String | 
| startTime | The time of day when a time-based menu becomes available. The value is in milliseconds (for example, `41400000`) since the start of the restaurant's day (the day starts at `0`). When converted to 24-hour clock time, the result should be the same as the startTimeHHmm field. | Int | 
| endTime | The time of day when a time-based menu stops being available. The value is in milliseconds (for example, `57600000`) since the start of the restaurant's day (the day starts at `0`). When converted to 24-hour clock time, the result should be the same as the endTimeHHmm field. | Int | 
| startTimeHHmm | The time of day when a time-based menu becomes available. The time is in 24-hour HHmm format (for example, `15:45`). This value is a conversion of the startTime field to a more readable format (the day starts at `00:00`). | String | 
| endTimeHHmm | The time of day when a time-based menu stops being available. The time is in 24-hour HHmm format (for example, `19:35`). This value is a conversion of the endTime field to a more readable format (the day starts at `00:00`). | String | 
| startTimeLocalStandardTime | The time of day when a time-based menu becomes available. The value is in milliseconds since the start of the restaurant's day (the day starts at `0`). The value adds the restaurant timezone's offset (for example, -5 hours in a `23400000` value). Note that Daylight Saving Time (DST) is ignored. When converted to 24-hour clock time, the result should be the same as the startTimeHHmm field. | Int | 
| endTimeLocalStandardTime | The time of day when a time-based menu stops being available. The value is in milliseconds since the start of the restaurant's day (the day starts at `0`). The value adds the restaurant timezone's offset (for example, -5 hours in a `36900000` value). Note that Daylight Saving Time (DST) is ignored. When converted to 24-hour clock time, the result should be the same as the startTimeLocalStandardTime field. | Int | 
| startTimeHHmmLocalStandardTime | The time of day when a time-based menu becomes available. The time is in 24-hour HHmm format (for example, `15:45`). This value is a conversion of the startTimeLocalStandardTime field to a more readable format (the day starts at `00:00`). | String | 
| endTimeHHmmLocalStandardTime | The time of day when a time-based menu stops being available. The time is in 24-hour HHmm format (for example, `19:35`). This value is a conversion of the endTimeLocalStandardTime field to a more readable format (the day starts at `00:00`). | String | 
| availableAllTimes | Indicates whether the menu is available at all times of the day. If the value is `false`, then the startTime* fields and the endTime* fields list when this time-based menu is available. | Boolean | 
| availableAllDays | Indicates whether the menu is available each day of the week. | Boolean | 
| daysAvailableString | A JSON array of strings that lists the days of the week when the menu is available. The days are listed in an abbreviated format, such as `Sun` or `Thurs`.In this example, the menu is available on all days except for Sunday and Saturday:```
"daysAvailableString": [
   "Mon",
   "Tues",
   "Wed",
   "Thurs",
   "Fri"
]
```

 | JSON array | 
| daysAvailableBits | This field is a numeric version of the daysAvailableString field and is for Toast internal use only. | Int | 
| imageLink | A URL to an image located on Amazon S3. For example:https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg | String | 

##### MenuGroup

The following table shows the information about each menu group at your restaurant from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| entityType | The type of the menu component described by this JSON object. The value for a menu object is `MenuGroup`. | String | 
| name | A descriptive identifier for the menu group. For example, `Appetizers` or `Entrees`. | String | 
| guid | The unique identifier for the menu group, assigned by the Toast POS. | String | 
| description | A written description of the menu group. | String | 
| subgroups | An array of other `MenuGroup` objects. For example, `Red Wine` is the menu group and it has the subgroups `By the Glass` and `By the
              Bottle`. | JSON array | 
| items | An array of [MenuItem](adminDataExportFieldReference.html#menuExportMenuitem) objects. | JSON array | 
| idString | This field is for Toast internal use only. | String | 
| imageLink | A URL to an image located on Amazon S3. For example:https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg | String | 
| orderableOnline | Indicates whether the menu group is available for online ordering. | Boolean | 
| visibility | Indicates where the menu group is displayed and who can see it. Values are:- `ALL` - The menu group is visible to everyone. For example, the menu group is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.
- `POS_ONLY` - The menu group is visible only on Toast POS devices (including kiosks).
- `NONE` - The menu group is hidden from everyone.

 | String | 

##### MenuItem

The following table shows the information about each menu item at your restaurant from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| entityType | The type of the menu component described by this JSON object. The value for a menu item object is `MenuItem`. | String | 
| name | A descriptive identifier for the menu item. For example, `Caesar Salad` or `Lemonade`. | String | 
| guid | The unique identifier for the menu item, assigned by the Toast POS. | String | 
| description | A written description of the menu item. | String | 
| sku | The stock keeping unit (SKU) identifier for the item. | String | 
| plu | The price lookup (PLU) code for the item. | String | 
| maxSelections | This value only applies to items in a [MenuOptionGroup](adminDataExportFieldReference.html#menuExportMenuoptiongroup)object. | Integer | 
| price | The amount of money that the item costs, expressed in U.S. dollars. All currency in Toast is treated the same and uses the dollar symbol $. There is no conversion between currency. | Currency | 
| prices | An array of menu-specific prices for the item. If an item is included in more than one menu, it can have different prices on each menu. For example, if you have a Lunch menu and a Dinner menu, a menu item can belong to both menus and have one price for the Lunch menu and a higher price for the Dinner menu. | JSON array | 
| isDefault | Whether or not the item is selected unless a customer chooses to decline it. | Boolean | 
| optionGroups | An array of [MenuOptionGroup](adminDataExportFieldReference.html#menuExportMenuoptiongroup) objects. | JSON array | 
| idString | This field is for Toast internal use only. | String | 
| itemGroupGuid | The unique identifier of the menu group to which this menu item belongs. | String | 
| calories | The caloric value for this menu item. The value can be any positive or negative integer, or zero. | Integer | 
| imageLink | A URL to an image located on Amazon S3. For example:https://s3.amazonaws.com/toasttab/restaurants/restaurant-59760/menu/items/5/item-4989_149066.jpg | String | 
| orderableOnline | Indicates whether the menu item is available for online ordering. | Boolean | 
| visibility | Indicates where the menu item is displayed and who can see it. Values are:- `ALL` - The menu item is visible to everyone. For example, the menu item is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.
- `POS_ONLY` - The menu item is visible only on Toast POS devices (including kiosks).
- `NONE` - The menu item is hidden from everyone.

 | String | 

##### MenuOptionGroup

The following table shows the information about each menu option group, or modifier group, at your restaurant from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| entityType | The type of the menu component described by this JSON object. The value for a menu option group object is `MenuOptionGroup`. | String | 
| name | A descriptive identifier for the menu option group. For example, `Substitutions` or `Extras`. | String | 
| guid | The unique identifier for the menu option group, assigned by the Toast POS. | String | 
| minSelections | The minimum number of options that a customer can choose from the menu option group. If a server must make a selection from the menu option group, the value is `1`. For example, a menu item might require that a customer choose an option from a menu option group that specifies the level of doneness. | Integer | 
| maxSelections | The maximum number of options that a customer can choose from the menu option group. If a customer can choose an unlimited number of options from a menu option group, the value is `null`.As an example of a menu option group with a maximum greater than one, assume this configuration:```
Group: Cheese
Items: ( Cheddar, American, Swiss )
maxSelections: 2
minSelections: 1
```

This means:- You can select AT MOST two different cheeses from this group to apply on the item (the `maxSelections` value).
- You must select AT LEAST one cheese from this group to apply on the item (the `minSelections`value).

 | Integer or null | 
| pricingMode | Indicates how the options in the menu option group affect the price of the menu items they are applied to. Values are:- `ADJUSTS_PRICE` - Choosing an option from the menu option group affects the price of the menu item it applies to. The amount of the adjustment depends on the price of the option applied.
- `FIXED_PRICE` - Choosing an item from the menu option group affects the price of the item it applies to. The amount of the adjustment is set at the menu option group level and applies to all options in the group. Note that this does not necessarily mean that all options in the group have an identical price. It means that all options in the group are treated the same way with respect to pricing. For example, if the menu option group uses sequence pricing, and the first two options are free while the third is $1, the specific modifier that costs $1 is arbitrary. Fixed refers to the fact that the pricing is fixed at the modifier group level, not that the price of each option in the group is constant.
- `INCLUDED` - Choosing an option from the menu option group does not affect the price of the menu item it applies to (because the price of the option is included in the price of the menu item it applies to).

 | String | 
| pricingStrategy | Indicates the way prices are set for the options in this menu option group. Values are:- `NONE` - Indicates that no pricing strategy is defined for this menu option group. `pricingStrategy` is set to `NONE`if the [pricingMode](adminDataExportFieldReference.html#adminDataExportPricingModeModifierGroup)is set to `ADJUSTS_PRICE` (prices are set on individual items in the menu option group, not on the menu option group itself, so there is no pricing strategy for the menu option group as a whole) or `INCLUDED`(no additional cost is charged for the options in the menu option group).
- `BASE_PRICE` - The pricing strategy for the menu option group is a constant price that does not change based on other conditions (such as size, sequence of ordering, and so on). For example, all of the options in the menu option group cost $1 at all times.
- `SEQUENCE_PRICE` - The pricing strategy for the menu option group is Sequence Price. With sequence pricing, the order in which options are specified determines the cost of each option, for example, the first option costs $1.00, the second costs $1.50, and the third costs $1.75.
- `UNSUPPORTED_STRATEGY` - The pricing strategy for the menu option group is one that, while it is supported internally in the Toast POS system, it is not yet supported for use via API. Currently, two pricing strategies are unsupported by the API, Size Price and Size/Sequence Price.

 | String | 
| pricingStrategyRules | An [object](adminDataExportFieldReference.html#menuExportPricingStrategyRules) that contains the pricing rules for the chosen [pricingStrategy](adminDataExportFieldReference.html#adminDataExportPricingStrategyModOptionGroup). If the pricing strategy is `NONE` or `UNSUPPORTED_STRATEGY`, this object is set to `NONE`. | JSON object | 
| defaultOptionsChargePrice | Indicates whether the prices associated with the menu option group's default options are added to the cost of the menu items they modify. Values are:- `NO` - The option price is ignored. No change is made to the cost of the menu item.
- `YES` - The option price is added to the cost of the menu item.

 | String | 
| defaultOptionsSubstitutionPricing | Indicates whether substitution pricing is enabled for the menu options group. Values are:- `NO` - Substitution pricing is not enabled. Removing a default option from a menu item has no impact on the price of the menu item.
- `YES` - Substitution pricing is enabled. Substitution pricing allows a guest to remove one or more default options from a menu item and apply the value of those options toward the purchase of one or more different options. For example, a guest orders a salad that comes with chicken by default but asks to substitute salmon for the chicken. The price of the chicken option is $7. The price of the salmon option is $9. In this case, the Toast POS system calculates the difference and charges the substitution price of $2 for the salmon (not the regular price of $9).

There are two scenarios that can occur with substitution pricing:- If the substitution options cost the same as or less than the default options, then no price adjustments occur. The menu item costs the same as it does with the default options.
- If the substitution options cost more than the default options, then the Toast POS system calculates the difference in price and reprices the substitution options accordingly. For example, if you remove a default option that costs $10 and replace it with two options that cost $8 and $7, then the cost of the replacement options is $5 ($8 + $7 - $10 = $5).

 | String | 
| items | An array of the objects that represent the options in the menu option group. | JSON array | 
| idString | This field is for Toast internal use only. | String | 
| visibility | Indicates where the menu option group is displayed and who can see it. Values are:- `ALL` - The menu option group is visible to everyone. For example, the menu option group is seen by restaurant employees using a Toast POS device and by restaurant guests using the online ordering page.
- `POS_ONLY` - The menu option group is visible only on Toast POS devices (including kiosks).
- `NONE` - The menu option group is hidden from everyone.

 | String | 

##### PricingStrategyRules

The following table shows the information about the pricing strategy for the modifier groups at your restaurant from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| basePrice | Used when the [pricingStrategy](adminDataExportFieldReference.html#adminDataExportPricingStrategyModOptionGroup)is set to `BASE_PRICE`. Defines a constant price for all of the options in the menu options group. For example:```
"optionGroups": [ 
\{
  "guid": "7aeae7d5-8891-4fa1-bcbd-647ad1f16c66",
  "name": "Toppings",
  ...
  "pricingStrategy":"BASE_PRICE",
  "pricingStategyRules": \{
    "basePrice": 1.00
    \}
  ...
\}
```

 | Number | 
| numberOfLevels | Used when the [pricingStrategy](adminDataExportFieldReference.html#adminDataExportPricingStrategyModOptionGroup)is set to `SEQUENCE_PRICE`. Defines the number of levels for the sequence price. For example, if you have three levels, you can set a price for the first option added to the order, the second option added to the order, and all options added from the third option on. Used in conjunction with the [sequencePrices](adminDataExportFieldReference.html#adminDataExportSequencePrices)array. | Number | 
| sequencePrices | Sets the price for each level defined in the [numberOfLevels](adminDataExportFieldReference.html#adminDataExportNumberOfLevels)value. For example:```
"optionGroups": [ 
\{
  "guid": "7aeae7d5-8891-4fa1-bcbd-647ad1f16c66",
  "name": "Toppings",
  ...
  "pricingStrategy": "SEQUENCE_PRICE",
  "pricingStrategyRules": \{
    "numberOfLevels": 3,
    "sequencePrices": [
      0.50,
      0.75,
      1.00,
    ]
  \}
  ...
\}
```

 | JSON array | 

#### Premodifiers and postmodifiers

This section describes:

- `premodifierGroup` objects. Each premodifier group contains a group of `premodifier` objects.


- `premodifier` objects. Each premodifier can be a premodifier or postmodifier item.



##### premodifierGroups

The following table shows the information about the premodifier groups at your restaurant from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| name | A descriptive identifier for a `premodifierGroup` object. | String | 
| guid | The unique identifier for the premodifier group, assigned by the Toast POS. | String | 
| isDefault | Whether or not the item is selected unless a customer chooses to decline it. | Boolean | 
| premodifiers | An array of [premodifiers](adminDataExportFieldReference.html#menuExportPremodifier) objects. | JSON array | 

##### premodifiers

The following table shows the information about the premodifiers or postmodifiers at your restaurant from the menu data export.

| Field | Description | Data Type | 
| --- | --- | --- |
| name | A descriptive identifier for a specific premodifier or postmodifier in a `premodifiers` object. For example, `ADD` or `ON
              SIDE`. | String | 
| guid | The unique identifier for the premodifier or postmodifier, assigned by the Toast POS. | String | 
| basePrice | If `scalePrice` is `false`, this amount is added to the price. Note that the amount can be 0.00 (so that the price remains the same) and it can also be a negative value (which will reduce the price). | Currency | 
| scalePrice | Determines how the price is scaled. Values are:- `true` - multiplies the price by the `scaleFactor` value.
- `false` - does not multiply the price but instead adds the `basePrice` value to the item.

 | Boolean | 
| scaleFactor | If `scalePrice` is `true`, the item price is multiplied by this factor. | Number | 
| displayMode | Determines the modifier type. Values are:- `PREFIX` - specifies a premodifier. This means the name of this premodifier is displayed as a prefix before the name of the modifier. For example, if the modifier is named `Bacon` and the premodifer is named `ADD`, the full display will be `ADD Bacon`.
- `SUFFIX` - specifies a postmodifier. This means the name of this premodifier is displayed as a suffix after the name of the modifier. For example, if the modifier is named `Bacon` and the postmodifer is named `ON SIDE`, the full display will be `Bacon ON SIDE`.

 | String | 

### Orders data export

The orders report includes information about the orders placed at your restaurant. The file name of the orders data export is `OrderDetails.csv`.

The following table shows details on what the orders data export contains.

| Field | Description | Data Type | 
| --- | --- | --- |
| Location | Restaurant Location | String | 
| Order Id | Order ID | Long | 
| Order # | Order Number | Integer | 
| Checks | Check number(s) | List of Strings | 
| Opened | Timestamp for Order Open Time | Date (MM/DD/YYYY HH:MM:SS) | 
| # of Guests | Number of Guests | Integer | 
| Tab Names | Guest Name for Tab | String | 
| Server | Name of Server who created order | String | 
| Table | Number of Table | Integer | 
| Revenue Center | Name of Revenue Center | String | 
| Dining Area | Name of Dining Area | String | 
| Service | Day part | String | 
| Dining Options | Dining Options (defined by restaurant) | String | 
| Discount Amount | Discount Value | Number (2 decimals) | 
| Amount | Amount Value | Number (2 decimals) | 
| Tax | Taxes Value | Number (4 decimals) | 
| Tip | Tip Value | Number (2 decimals) | 
| Gratuity | Gratuity Value | Number (2 decimals) | 
| Total | Total Value | Number (2 decimals) | 
| Voided | True or False | Boolean | 
| Paid | Timestamp for Paid Time | Date (MM/DD/YYYY HH:MM:SS) | 
| Closed | Timestamp for Closed Time | Date (MM/DD/YYYY HH:MM:SS) | 
| Duration (Opened to Paid) | Time Duration from Open Timestamp to Paid Timestamp | Time (HH:MM:SS) | 
| Order Source | "Source of Order (In store, Online)" | String | 

### Payments data export

The payments data export includes information about the payments applied to checks at your restaurant. The file name of the payments data export is `PaymentDetails.csv`.

The following table shows details on what the payment data export contains.

| Field | Description | Data Type | 
| --- | --- | --- |
| Location | Restaurant Location | String | 
| Payment Id | Payment ID | Long | 
| Order Id | Order ID | Long | 
| Order # | Order Number | Integer | 
| Paid Date | Timestamp for Order Paid Time | Date (MM/DD/YYYY HH:MM:SS) | 
| Order Date | Timestamp for Order Open Time | Date (MM/DD/YYYY HH:MM:SS) | 
| Check Id | Check ID | Long | 
| Check # | Check number | Integer | 
| Tab Name | Number of Table | Integer | 
| Server | Name of Server who created order | String | 
| Table | Number of Table | String | 
| Dining Area | Name of Dining Area | String | 
| Service | Day Part | String | 
| Dining Option | Dining Options (defined by restaurant) | String | 
| House Acct # | House Account number payment applied to | Integer | 
| Amount | Amount Value | Number (2 decimals) | 
| Tip | Tip Value | Number (2 decimals) | 
| Gratuity | Gratuity Value | Number (2 decimals) | 
| Total | Total Value | Number (2 decimals) | 
| Swiped Card Amount | Swiped Card Amount | Number (2 decimals) | 
| Keyed Card Amount | Keyed Card Amount | Number (2 decimals) | 
| Amount Tendered | Cash Amount Value | Number (2 decimals) | 
| Refunded | Status of Refund | String | 
| Refund Date | Timestamp of Refund Value | Date (MM/DD/YYYY HH:MM:SS) | 
| Refund Amount | Refund Value | Number (2 decimals) | 
| Refund Tip Amount | Refund Tip Amount | Number (2 decimals) | 
| Void User | Employee who voided the transaction | String | 
| Void Approver | Employee who approved the void transaction | String | 
| Void Date | Timestamp of the void transaction | String | 
| Status | CC Processing status | String | 
| Type | Payment type (Credit, Cash, Gift Card) | String | 
| Cash Drawer | Cash Drawer used for payment | String | 
| Card Type | Card Brand | String | 
| Other Type | Other type of payment | String | 
| Email | Email of customer for digital receipt | String | 
| Phone | Phone number of customer for digital receipt | String | 
| Last 4 Card Digits | Last 4 Card Digits of customer card | String | 
| Receipt | Receipt token for digital receipts | String | 
| V/MC/D Fees | CC processing fees for payment | Number (2 decimals) | 

