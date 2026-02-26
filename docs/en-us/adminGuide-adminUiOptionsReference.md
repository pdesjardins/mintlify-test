---
title: "UI options settings"
id: adminUiOptionsReference
type: section
documentId: adminGuide
parentSectionFile: adminGuide-devPortalPlatformGuideUiOptionsReferenceOmitChunkFromSearchIndex.md
parentSectionTitle: "UI options"
previousSectionFile: adminGuide-devPortalPlatformGuideUiOptionsReferenceOmitChunkFromSearchIndex.md
previousSectionTitle: "UI options"
nextSectionFile: adminGuide-adminGlossary.md
nextSectionTitle: "Glossary"
externalReferences: [https://central.toasttab.com/s/article/Basic-Digital-Receipt-Configuration, https://central.toasttab.com/s/article/Close-Out-Day-Z-Report-Auto-Capture#Z_report, https://central.toasttab.com/s/article/Closed-Drawer-Report-1492723816056, https://central.toasttab.com/s/article/Enabling-Strict-Mode-1492810276171]
excerpt: "The settings on this page customize how employees interact with Toast POS devices."
procedures: 0
codeExamples: 0
---

The settings on this page customize how employees interact with Toast POS devices.

To review and change settings on the Front of house &gt; Order screen setup &gt; UI options page, you must have the Web Setup &gt; 6.6 Restaurant Operations Setup[access permission](adminGuide-adminPermissions#adminRestaurantAdminAccessPermissions).

When applying these settings to multiple locations, you can select locations for each setting option. Use the Select locations to manage dropdown menu at the top of the page to choose locations to apply the UI options to. Use the dropdown menu under the Select locations option to open the Select locations dialog. You can select the locations you want to apply the setting option to by using the Locations or Groups tab.

For settings where you can select more than one option or uses a custom field, you create a set of options that can then be applied to locations. Add a new entry, modify the entry in the dialog that appears, and then select locations.

## Login screen

The following table provides information about the settings of the Login screen section on the Front of house &gt; Order screen setup &gt; UI options page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>The settings described in this table affect the set of buttons that are available on the Toast POS devices used by employees, and the way that orders appear on order screens and on printed and KDS device kitchen tickets.</td>
    </tr>
    <tr>
      <td>Mask passcode</td>
      <td>This setting allows you to apply passcode masking.<ul><li>On <br/> This option is enabled by default to activate passcode masking on all Toast POS devices. Asterisks (*) appear instead of the typed digits when employees enter their passcodes.</li><li>Off <br/> This option disables passcode masking.</li></ul> <br/> You can also allow employees to access Toast POS devices that have a magnetic card reader by swiping a card with a magnetic stripe. On Toast POS devices, you associate a card with an employee passcode by selecting Manager Activities > Register Swipe Card.</td>
    </tr>
    <tr>
      <td>Additional text</td>
      <td>This setting accepts a text string. The text appears along the bottom of the sign in screen of your Toast POS devices. It appears above the Toast POS version number and in the same size font. <blockquote><strong>Note</strong> If using multi-location restaurants, you can only set one text string for each restaurant.</blockquote> </td>
    </tr>
  </tbody>
</table>

## Order screen

The following table provides information about the settings of the Order screen section on the Front of house &gt; Order screen setup &gt; UI options page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>The settings described in this table affect the set of buttons that are available on the Toast POS devices used by employees, and the way that orders appear on order screens and on printed and KDS device kitchen tickets.</td>
    </tr>
    <tr>
      <td>Additional Modifier Groups</td>
      <td>This setting lists modifier groups that you can include on the order screen for every menu item. The modifier options that employees select from these modifier groups appear on kitchen tickets to help coordinate serving, packaging, plating, and preparing items to each guest's specifications. <br/> To include a button for an additional modifier group, select the Enabled checkbox. <br/> In the example, all of the additional modifier groups are enabled. A button appears for each enabled modifier group on the right, or bottom, of the order screen after the menu-related modifier groups for the item being ordered.![A Table Service order screen for an order of chicken wings with modifier buttons for Seat Number, Dining Option, Course, Split, and Special Request after the menu-related size and sauce modifier buttons.](https://doc.toasttab.com/doc/media/order_in_progress_addl_modifiers.png) <br/> If an ordered item does not have any associated menu-related modifier groups, employees select the ordered item to access buttons for additional modifier groups. <br/> You can also change the sequence in which the additional modifier buttons appear on order screens. To move a button to a different location, click and drag the reorder icon next to the name of the additional modifier group.<ul><li>Seat number (Table Service Only) <blockquote><strong>Note</strong> To use this option, you must also set <a href="adminGuide-adminUiOptionsReference#configPartySize">Party size</a> to Always ask before creating a new order.</blockquote>  <br/> This option adds the Seat Number modifier group for orders taken in Table Service mode. For parties with more than one guest, when an employee selects Seat Number, buttons for Share, 1, 2, and so on appear. <br/> If you enable this option, you can require employees to specify seat numbers by selecting the Required checkbox. You can also use the seat number to sort items on kitchen tickets: on the Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup page, set <a href="adminGuide-adminKitchenDiningRoomReference#configItemSortingPriority">Item Sorting Priority</a> to By seat number.</li><li>Seat number (Quick Order Only) <blockquote><strong>Note</strong> To use this option, you must also set <a href="adminGuide-adminUiOptionsReference#configPartySize">Party size</a> to Always ask before creating a new order.</blockquote>  <br/> This option adds the Seat Number modifier group for orders taken in Quick Order mode. For parties with more than one guest, when an employee selects Seat Number, buttons for Share, 1, 2, and so on appear. <br/> If you enable this option, you can require employees to specify seat numbers by selecting the Required checkbox. You can also use the seat number to sort items on kitchen tickets: on the Kitchen > Printers, tickets, & KDS devices > Kitchen and ticket setup page, set <a href="adminGuide-adminKitchenDiningRoomReference#configItemSortingPriority">Item Sorting Priority</a> to By seat number.</li><li>Dining option <br/> This option adds the Dining Option modifier group. When an employee selects Dining Option, buttons for Dine In, Take Out, Delivery, and so on appear. You define the <a href="adminGuide-adminKitchenDiningRoomReference#configDiningOptions">dining options</a> that your restaurant uses on the Kitchen > Dining options > Dining options page. <blockquote><strong>Note</strong> This modifier appears on the right (or bottom) of the order screen and identifies how to package an item for service. The Dining button that is available on the left (or top) of the order screen applies to the order as a whole. For example, guests at a table order for themselves, and ask for a wrapped sandwich to be ready when they finish their meal. The dining option selected for the table is Dine In and the dining option for the sandwich is Take Out. On a KDS device, the ticket for the sandwich appears as follows.</blockquote> ![A kitchen ticket with Dine In printed in large font at the top, a course of Dessert in the center, and 1 sandwich with Take Out, in brackets and italics, underneath.](https://doc.toasttab.com/doc/media/dine_in_vs_take_out.png) <br/> If you define rules to <a href="adminGuide-adminAboutItemRoutingRules#adminReroutingOrdersBasedOnDiningOption">reroute orders based on the dining option</a> specified, this additional modifier only affects the appearance of the item on the ticket. It does not affect how the Toast platform routes the order.</li><li>Course <br/> This option adds the Course modifier group. When an employee selects Course, buttons for your courses (Apps, Main, Dessert, and so on) appear. <br/> You add <a href="adminGuide-adminKitchenDiningRoomReference#configCourses">courses</a> on the Kitchen > Pacing > Courses page, and enable <a href="adminGuide-adminKitchenDiningRoomReference#configCoursePacing">course pacing</a> on the Kitchen > Pacing > Meal pacing page.</li><li>Split <br/> This option adds the Split modifier group. When an employee selects Split, buttons for For 2, For 3, For 4, and so on appear. <blockquote><strong>Note</strong> The button for this modifier appears on the right (or bottom) of the order screen to identify how to plate an item for service. The Split button that is available on the left (or top) of the order screen applies to the order as a whole, and allows employees to divide a check for payment by multiple guests.</blockquote> ![An order screen showing both of the Split buttons.](https://doc.toasttab.com/doc/media/split_check_vs_split_modifiers.png)</li><li>Special request <br/> This option is enabled by default to add the Special Request modifier group. When an employee selects Special Request, the New Request dialog prompts for the name and optional additional cost of the requested modification.</li></ul></td>
    </tr>
    <tr>
      <td>Special request price entry</td>
      <td> <blockquote><strong>Note</strong> This setting is managed on the Front of House page</blockquote> When enabled, a price can be specified for each Special Request additional modifier.</td>
    </tr>
    <tr>
      <td>Show Send, Stay, and Hold buttons</td>
      <td>This setting only applies if <a href="adminGuide-adminUiOptionsReference#configOrdersSendOnlyAfterPaid">Orders send only after check is paid</a> is set to Off. <br/> This setting lists buttons that you can use on order screens. To include a button for one of these actions, select the checkbox next to the action name.<ul><li>Send <br/> This option allows employees to send ordered items to the kitchen, and begin an order for another guest, without collecting payment for the first order.</li><li>Stay <br/> This option allows employees to send a partial order to the kitchen, and continue to enter additional items to the same order for the same group of guests. For example, employees can use this option to send the drink order for a large party and then immediately begin taking orders for additional items.</li><li>Hold <br/> This option allows employees to save all ordered items without sending them to the kitchen or collecting payment. To return to a held order, employees select All checks on the top right and select the Open tab.</li></ul> <blockquote><strong>Note</strong> The orientation of the Toast POS device affects how much space is available to display buttons. If all of these buttons are enabled but they do not all appear in Quick Order mode, try rotating the device 90°.</blockquote> </td>
    </tr>
    <tr>
      <td>Valid SSIDs</td>
      <td>This setting identifies the valid service set identifier (SSID) name of your wireless local area network (WLAN). When you use this setting to set one or more SSIDs, Toast POS devices will only connect to the internet using the specified network(s). <br/> To add an SSID, select Add SSID and enter the name of the network in the entry field that appears. <blockquote><strong>Note</strong> The SSID that you enter must match the network name exactly, including capitalization and punctuation.</blockquote> </td>
    </tr>
    <tr>
      <td>Orders send only after check is paid</td>
      <td>This setting determines whether payment is required before orders are sent to the kitchen for fulfillment.<ul><li>On <br/> This option only shows the Pay $ button. Employees must receive payment to send tickets to the kitchen. Applies to all order screens. <blockquote><strong>Note</strong> When employees specify a <a href="adminGuide-adminKitchenDiningRoomReference#configDiningOptions">dining option</a> that has takeout or delivery as a dining behavior the following functions are expected:  The Stay and Send buttons appear on all order modes. The Hold button appears on the Table Service screen. The Pay ($) button functions as a Send button and sends a ticket to the kitchen even if the order has not been paid. To prevent unpaid checks from firing to the kitchen, employees should use the Stay button instead of Pay ($).</blockquote>  <br/> For example, the employees in a quick service restaurant use hand-held devices to take orders from guests as they walk in. Selecting On streamlines the typical in-person ordering and payment process. When a guest calls in a takeout order, however, the employee can send the order to the kitchen and take payment by credit card (by selecting Pay $), or send the order to the kitchen (by selecting Send, which appears for the takeout dining option) and receive cash payment when the guest arrives.</li><li>Off <br/> This option provides the Send, Stay, and Hold buttons on the Table Service and Delivery screens for all orders, regardless of the selected dining option. It also provides access to the <a href="adminGuide-adminUiOptionsReference#configShowSendHoldStay">Show Send, Stay, and Hold buttons</a> setting for Quick Order mode.</li></ul></td>
    </tr>
    <tr>
      <td>Prompt for tab name? (Quick Order only)</td>
      <td>This setting determines whether a tab name (or credit card swipe) is required for dine-in orders when employees use quick order mode to send an order to the kitchen. The tab name appears at the top of the kitchen ticket under the order number.<ul><li>On <br/> This option prompts employees for a tab name or card swipe when they select Pay $ for a dine-in order. If Send, Stay, or Hold are enabled by the <a href="adminGuide-adminUiOptionsReference#configShowSendHoldStay">Show Send, Stay, and Hold buttons</a> option, or Fast Cash is enabled by <a href="adminGuide-adminUiOptionsReference#configFastCashButton">Show fast cash button?</a>, selecting them for a dine-in order also prompts for the tab name. <br/> After you select this option, Device Setup includes an Override Blank Tab Name Prompt setting. You configure this setting to Off on devices that <em>should</em>  prompt for a tab name, or to On on devices that you do not want to prompt for a tab name.</li><li>Off <br/> This option does not prompt employees for a tab name or card swipe.</li></ul> <br/> For more information about the effects of these options, see <a href="adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefContent">KDS ticket contents</a>.</td>
    </tr>
    <tr>
      <td>Prompt for dining option? (Quick Order only)</td>
      <td>For restaurants and devices that do not have a default dining option, this setting determines whether a dining option must be specified when employees send an order to the kitchen using quick order mode. The dining option appears at the top of the kitchen ticket. <blockquote><strong>Note</strong> This setting requires that none of the <a href="adminGuide-adminKitchenDiningRoomReference#configDiningOptions">dining options</a> defined on the Kitchen > Dining options > Dining options is identified as the default.</blockquote> <ul><li>On <br/> Select this option to prompt employees for the dining option when they select Pay $ in Quick Order mode. If Send, Stay, or Hold are enabled by the <a href="adminGuide-adminUiOptionsReference#configShowSendHoldStay">Show Send, Stay, and Hold buttons</a> setting, or Fast Cash is enabled by <a href="adminGuide-adminUiOptionsReference#configFastCashButton">Show fast cash button?</a>, selecting them also prompts for the dining option. <blockquote><strong>Note</strong> For this option to take effect, verify that there is no default dining option specified by either the Kitchen > Dining options > Dining options page for your restaurant or Setup > Device Setup > Device Default Dining Option for a specific Toast POS device.</blockquote> </li><li>Off <br/> Select this option if the kitchen does not need this information on kitchen tickets, or if you have a default dining option defined on the Kitchen > Dining options > Dining options page or on your Toast POS devices.</li></ul> <br/> For more information about the effects of these options, see <a href="adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefContent">KDS ticket contents</a>.</td>
    </tr>
    <tr>
      <td>Show item sent time</td>
      <td>This setting determines whether the time that the order was sent to the kitchen appears below the item list on the order screen.<ul><li>On <br/> Select this option to include a <code>Sent HH:MM</code> message below the item list on order screens. The sent time appears for every ordering mode: Table Service, Quick Order, and Delivery. Including this information with orders gives employees and managers additional insight into the fulfillment time frame, and, as a result, the guest experience.</li><li>Off <br/> Select this option if you do not need this information on order screens.</li></ul></td>
    </tr>
    <tr>
      <td>Modifier display mode</td>
      <td>This setting controls how modifiers appear under menu items on order screens and printed and KDS device kitchen tickets. <br/> Illustrations of the order and kitchen tickets for each setting are provided. The example order is for a sandwich item with the following modifiers entered in sequence: required modifiers for meat (chicken) and side (green salad, which has an extra charge and requires the dressing modifier, balsamic), and optional modifiers of bacon (extra charge), lettuce, and tomato. <a href="adminGuide-adminUiOptionsReference#configHideModifierPrices">Add modifier charges to item price</a> is set to On and <a href="adminGuide-adminUiOptionsReference#configModifierGroupSorting">Modifier group sorting</a> is set to Display in order modifiers are listed in their modifier group.<ul><li>Vertical: list one modifier per line <br/> Select this option to show each modifier on a separate line, in either the sequence the employee selects them or in the sequence the modifier groups and modifiers are defined for the menu item, as defined by the Sort Order, <a href="adminGuide-adminUiOptionsReference#configModifierOrderingPriority">Modifier ordering priority</a>, and <a href="adminGuide-adminUiOptionsReference#configModifierGroupSorting">Modifier group sorting</a> settings. In kitchens that use KDS devices and set <a href="adminGuide-adminKitchenDiningRoomReference#configFulfillItems">Fulfill Items</a> to Enable individual item fulfillment, kitchen employees can individually mark modifiers in the list as fulfilled.![An order screen using vertical to display the example order](https://doc.toasttab.com/doc/media/vertical_order.png)![A KDS device using vertical to display the example order.](https://doc.toasttab.com/doc/media/vertical_kds.png) <blockquote><strong>Note</strong> To use Sort Order to sort how modifiers are ordered on printed and KDS kitchen tickets, you must use either the Vertical or Horizontal options. Using Sort Order to sort modifiers on kitchen tickets is in limited release.</blockquote> </li><li>Horizontal: list all modifiers on one line, comma separated <br/> Select this option to show each modifier in a comma-separated list, in either the sequence the employee selects them or in the sequence the modifier groups and modifiers are defined for the menu item, as defined by the Sort Order, <a href="adminGuide-adminUiOptionsReference#configModifierOrderingPriority">Modifier ordering priority</a>, and <a href="adminGuide-adminUiOptionsReference#configModifierGroupSorting">Modifier group sorting</a> settings.![An order screen using horizontal to display the example order.](https://doc.toasttab.com/doc/media/horizontal_order.png)![A KDS device using horizontal to display the example order.](https://doc.toasttab.com/doc/media/horizontal_kds.png) <blockquote><strong>Note</strong> To use Sort Order to sort how modifiers are ordered on printed and KDS kitchen tickets, you must use either the Vertical or Horizontal options. Using Sort Order to sort modifiers on kitchen tickets is in limited release.</blockquote> </li><li>Legacy <br/> Select this option to show each modifier on a separate line, with required modifier options first, followed by optional modifiers sorted from lowest price (free) to highest. Multiple modifier options with the same price appear in the sequence the employee selects them. In kitchens that use KDS devices and set <a href="adminGuide-adminKitchenDiningRoomReference#configFulfillItems">Fulfill Items</a> to Enable individual item fulfillment, kitchen employees can individually mark modifiers in the list as fulfilled.![An order screen using legacy to display the example order.](https://doc.toasttab.com/doc/media/legacy_order.png)![A KDS device using legacy to display the example order.](https://doc.toasttab.com/doc/media/legacy_kds.png) <blockquote><strong>Note</strong> The Legacy and Legacy - Flatten options override the <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode">Modifier display mode</a>, <a href="adminGuide-adminUiOptionsReference#configModifierGroupSorting">Modifier group sorting</a>, and <a href="adminGuide-adminUiOptionsReference#configModifierOrderingPriority">Modifier ordering priority</a> settings.</blockquote> </li><li>Legacy - Flatten <br/> Select this option to show modifiers in a comma-separated list, in the sequence the employee selects them.![An order screen using legacy - flatten to display the example order.](https://doc.toasttab.com/doc/media/legacy_flatten_order.png)![A KDS device using legacy - flatten to display the example order.](https://doc.toasttab.com/doc/media/legacy_flatten_kds.png) <blockquote><strong>Note</strong> The Legacy and Legacy - Flatten options override the <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode">Modifier display mode</a>, <a href="adminGuide-adminUiOptionsReference#configModifierGroupSorting">Modifier group sorting</a>, and <a href="adminGuide-adminUiOptionsReference#configModifierOrderingPriority">Modifier ordering priority</a> settings.</blockquote> </li></ul> <br/> For more information about the effects of these options, see <a href="adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefLayout">KDS ticket layout</a>.</td>
    </tr>
    <tr>
      <td>Show default modifiers?</td>
      <td>This setting determines how default modifiers in a modifier group appear on order screens and printed and KDS device kitchen tickets. <br/> Illustrations of the order and kitchen tickets for each setting are provided. The example order is for a sandwich item that has default modifiers of lettuce, onion, and tomato. The guest in this example asks for lettuce and tomato but no onion. <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode">Modifier display mode</a> is set to Vertical: list one modifier per line.<ul><li>On <br/> Select this option if you want all selected modifier options to appear below the ordered item. If a modifier is selected it appears, if it is not selected it does not appear.![An order screen that shows all selected modifiers.](https://doc.toasttab.com/doc/media/show_default_yes_order.png)![A KDS device that shows all selected modifiers.](https://doc.toasttab.com/doc/media/show_default_yes_kds.png)</li><li>Off <br/> Select this option if you only want default modifier options to appear below the ordered item when they are specifically de-selected. A default modifier option that is de-selected appears with <code>NO</code> before the name.![An order screen that only shows default modifiers if they are not .](https://doc.toasttab.com/doc/media/show_default_no_order.png)![A KDS device using horizontal to display the example order.](https://doc.toasttab.com/doc/media/show_default_no_kds.png)</li></ul></td>
    </tr>
    <tr>
      <td>Consolidate menu items</td>
      <td>This setting determines whether each item in an order appears on a separate line, or if identical items (with identical modifiers if any) in an order are summed and shown on one line with the total count. <blockquote><strong>Note</strong> If you enable the Seat Number<a href="adminGuide-adminUiOptionsReference#configAdditionalModifierGroups">additional modifier group</a>, items always appear on separate lines, even if a seat number is not explicitly specified by the employee.</blockquote>  <br/> Illustrations of the order and kitchen tickets for each setting are provided. The example order is for two identical chicken wings with Buffalo sauce. <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode">Modifier display mode</a> is set to Vertical: list one modifier per line.<ul><li>On <br/> Select this option to show identical items and modifiers once with the total number ordered on order screens and printed or KDS device kitchen tickets. Applies only when the Seat Number<a href="adminGuide-adminUiOptionsReference#configAdditionalModifierGroups">additional modifier group</a> is not enabled.![An order screen using Consolidate menu items set to On to display the example order.](https://doc.toasttab.com/doc/media/combine_items_yes_order.png)![A KDS device using Consolidate menu items set to On to display the example order.](https://doc.toasttab.com/doc/media/combine_items_yes_kds.png)</li><li>Off <br/> Select this option to show each item separately, with a count of 1, on order screens and printed or KDS device kitchen tickets.![An order screen using Consolidate menu items set to Off to display the example order.](https://doc.toasttab.com/doc/media/combine_items_no_order.png)![A KDS device using Consolidate menu items set to Off to display the example order.](https://doc.toasttab.com/doc/media/combine_items_no_kds.png)</li></ul> <br/> For more information about the effects of these options, see <a href="adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefLayout">KDS ticket layout</a>.</td>
    </tr>
    <tr>
      <td>Consolidate discounts</td>
      <td>This setting determines whether an item-level fixed currency discount is applied to each item in a consolidated group of identical items in an order.<ul><li>On <br/> Select this option to apply an item-level fixed currency discount to each item in a consolidated group of identical items. Note that consolidated groups of identical items are created when the Consolidate menu items setting is enabled.</li><li>Off <br/> Select this option if you do not want an item-level fixed currency discount to be applied to all items in a consolidated group of identical items, but instead want the discount to be applied to the total of all items.</li></ul></td>
    </tr>
    <tr>
      <td>Consolidate modifiers</td>
      <td>This setting determines whether each modifier option for a menu item appears on a separate line or if identical modifier options are combined and shown on one line with the total count. <br/> The configuration of the Consolidate modifiers setting affects the way that modifier options appear on:<ul><li>Toast POS order screens</li><li>Printed kitchen tickets, KDS device tickets, and the KDS all day display view</li><li>Guest facing displays</li><li>Guest receipts</li></ul> <br/> You can select:<ul><li>On <br/> Select this option to show identical modifier options once with the total number ordered.![An example of an order that shows identical modifier options grouped together with a prefix sum.](https://doc.toasttab.com/doc/media/con-mods-yes.png)</li><li>Off <br/> Select this option to show each modifier option separately.![An example of an order that shows modifier options listed separately, even if they are identical.](https://doc.toasttab.com/doc/media/con-mods-no.png)</li></ul></td>
    </tr>
    <tr>
      <td>Add modifier charges to item price</td>
      <td>This setting determines whether the prices defined for modifier options are summed with the menu item price for one total, or appear separately from menu item prices. <blockquote><strong>Note</strong> This setting affects only order screens. You define how modifier prices appear on guest receipts on the Payments > Checks & receipt setup > Guest receipt setup page.</blockquote> <ul><li>On <br/> Select this option if you only want the total price of the menu item and all modifier options to appear on the order screen.</li><li>Off <br/> Select this option if you want modifier option prices to appear separately from menu item prices. <br/> If <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode">Modifier display mode</a> is set to Legacy or Vertical: list one modifier per line the price of each modifier option appears on its own line; if set to Legacy - Flatten or Horizontal: list all modifiers on one line, comma separated the system sums the modifier option prices and displays the total below the menu item price.</li></ul></td>
    </tr>
    <tr>
      <td>Modifier group sorting</td>
      <td>For restaurants with <a href="adminGuide-adminUiOptionsReference#configModifierDisplayMode">Modifier display mode</a> set to Vertical: list one modifier per line or Horizontal: list all modifiers on one line, comma separated, this setting controls the sequence in which modifier options appear on order screens and printed and KDS device kitchen tickets.<ul><li>Display in order modifiers were added <br/> Select this option to list the modifier options in the sequence the employee selects them.</li><li>Display in order modifiers are listed in their modifier group <br/> Select this option to list modifier options sequenced by how the modifier groups are sequenced for the menu item, and, for multi-select modifier groups, by how the modifier options are sequenced in the modifier group.</li></ul> <br/> For example, you serve different kinds of barbecue sauce with your chicken wings, defined as options in the modifier group as mild, medium, hot, and insane. When guests order more than one of the sauces with their wings, they can either be listed in the order that the employee adds them (hot, mild, insane), or always in the same sequence relative to each other (mild, hot, insane). <blockquote><strong>Note</strong> If you configured the Sort Order setting for modifiers, that overrides this setting. Using Sort Order to sort modifiers on kitchen tickets is in limited release.</blockquote>  <br/> For more information about the effects of these options, see <a href="adminGuide-adminKdsConfigQuickRef#adminKdsQuickRefLayout">KDS ticket layout</a>.</td>
    </tr>
    <tr>
      <td>Modifier ordering priority</td>
      <td>This setting determines the sequence in which modifier group buttons appear on order screens and how modifiers are organized on printed and KDS kitchen tickets. This option applies to modifier groups defined in the menu. If you enable any of the <a href="adminGuide-adminUiOptionsReference#configAdditionalModifierGroups">additional modifier groups</a>, they appear after the menu modifier groups.<ul><li>On <br/> Select this option if you want modifier group buttons to appear in the sequence defined by their Display Ordering Priority values. To review and update these values for all of your modifier groups use Menus > Bulk management > Advanced properties. <blockquote><strong>Note</strong> For KDS devices using dynamic view and printed kitchen tickets, this setting is treated as if On is always selected.</blockquote> </li><li>Off <br/> Select this option if you want buttons for any required modifier groups to appear on the order screen before optional modifier groups.</li></ul> <blockquote><strong>Note</strong> If you configured the Sort Order setting for modifiers, that overrides this setting. Using Sort Order to sort modifiers on kitchen tickets is in limited release.</blockquote> </td>
    </tr>
    <tr>
      <td>Show fast cash button? (Quick Order only)</td>
      <td>This setting determines whether employees using Quick Order mode can use a single button to accept payments in cash for the exact amount of the check.<ul><li>On <br/> Select this option to include the Fast Cash button on the Quick Order screen, next to the Pay button. The Fast Cash button appears while an order is in progress, and has the effect of immediately closing a check when exact change is received.</li><li>Off <br/> Select this option to not include the Fast Cash button on the Quick Order screen.</li></ul></td>
    </tr>
    <tr>
      <td>Close order screen after printing receipt</td>
      <td>This setting determines whether the order screen remains open to the same order after employees tap Print to print a guest receipt.<ul><li>On <br/> Select this option to refresh the order screen after employees tap Print. The screen that appears next depends on the <a href="adminGuide-adminUiOptionsReference#configAutoSwitchUser">Auto switch user</a> setting:<ul><li>Off: A new order screen appears. The same employee can take the next order.</li><li>On: The passcode screen. A different employee can sign in.</li></ul></li><li>Off <br/> Select this option to keep the order screen open for the same order (similar to Stay) after employees tap Print.</li></ul></td>
    </tr>
    <tr>
      <td>Auto switch user</td>
      <td>This setting determines how frequently employees need to sign in to Toast POS devices. Applies to all order screens: Quick Order, Table Service, and Delivery. <blockquote><strong>Note</strong> Regardless of how you configure this setting, if you define a Screen Timeout period on a device the system signs the current user out of that device whenever the specified time period elapses without activity. For information about configuring individual devices, see <a href="adminGuide-adminConfigureDevice">Accessing the Toast POS Device Setup screen</a>.</blockquote> <ul><li>On <br/> Select this option to automatically sign the current user out and return to the passcode screen each time employees send an order to the kitchen, hold an order, or complete a payment transaction. If <a href="adminGuide-adminUiOptionsReference#configCloseAfterPrinting">Close After Printing</a> is Yes, the passcode screen also appears when employees print guest receipts.</li><li>Off <br/> Select this option if you do not want employees to sign in after every order.</li></ul></td>
    </tr>
    <tr>
      <td>Edit other employees' checks confirmation</td>
      <td>This setting determines whether employees who have the <a href="adminGuide-adminPermissions#adminAddlPosAccessPermissions">Edit Other Employees' Orders</a> access permission must respond to a confirmation prompt when they edit another employee's check.<ul><li>Prompt user when editing another server's check <br/> Select this option to present a confirmation dialog with the name of the employee who opened the check when lead employees change a check that is in progress.</li><li>Don't prompt <br/> Select this option to streamline the work of lead employees who frequently need to add items to checks opened by other employees.</li></ul></td>
    </tr>
    <tr>
      <td>Enable promo code search</td>
      <td>This setting determines whether order screens include the Promo Code option on the overflow menu (the ⋮ icon).<ul><li>On <br/> Select this option to allow employees to look up promo codes for guests.</li><li>Off <br/> Select this option to require guests to present the promo code to receive a discount.</li></ul></td>
    </tr>
    <tr>
      <td>Enable manual entry when using scale</td>
      <td>This setting determines whether employees, when using a device that is connected to a scale, can enter item weights manually.<ul><li>On <br/> Select this option to allow employees to override the weight provided by the scale.</li><li>Off <br/> Select this option to only use the weight provided by the scale.</li></ul></td>
    </tr>
    <tr>
      <td>Menu item search</td>
      <td> <blockquote><strong>Note</strong> This setting is managed on the Front of House page under the Search bar for POS menu setting.</blockquote> When enabled, employees can search for menu items by name using a search bar and the on-screen keyboard.</td>
    </tr>
  </tbody>
</table>

## POS Scheduling Settings

The following table provides information about the settings of the POS Scheduling Settings section on the Front of house &gt; Order screen setup &gt; UI options page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Max days in future to schedule orders</td>
      <td>This is the maximum number of days in the future an order can be scheduled. Includes online or catering orders.</td>
    </tr>
    <tr>
      <td>Enable Next Day mode on POS</td>
      <td><ul><li>On</li><li>Off</li></ul></td>
    </tr>
    <tr>
      <td>Time to send previous day's orders to kitchen (Next Day mode)</td>
      <td>This is the time when orders that are scheduled for fulfillment the next day are sent to the kitchen. The time is formatted as a 24-hour value, ranging from 4:00 to 23:59. For example, 3:30 PM is formatted as 15:30.</td>
    </tr>
  </tbody>
</table>

## Service Areas Screen

The following table provides information about the settings of the Service Areas Screen section on the Front of house &gt; Order screen setup &gt; UI options page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Party size</td>
      <td><ul><li>Always ask before creating a new order</li><li>Never ask</li></ul></td>
    </tr>
  </tbody>
</table>

## Tipping

The following table provides information about the settings of the Tipping section on the Front of house &gt; Order screen setup &gt; UI options page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Tip / Tax</td>
      <td>This setting determines the sequence in which the Toast platform calculates suggested <a href="adminGuide-adminGlossary.html#glossTip"><em>tip</em> </a> amounts and fixed percent <a href="adminGuide-adminGlossary.html#glossServiceCharge"><em>service charges</em> </a>.<ul><li>Calculate tip before tax <br/> Select this option to calculate suggested tip or service charge amounts first, and then calculate taxes.</li><li>Calculate tip after tax <br/> Select this option to calculate charges for taxes first, and then calculate suggested tip or service charge amounts.</li></ul> <br/> Examples of how the Toast platform calculates suggested tips and service charges follow. <br/> <strong>Suggested tip</strong> : For items totalling $50, a tax rate of 7.5%, and suggested tip percentages of 15%, 18%, and 20%, the system:<ul><li>Calculates tip before tax: Calculates suggested tip amounts of $7.50, $9.00, and $10. Then uses the $50 item total to calculate the taxes, <code>$50 * .075 = $4.50</code>, for a total check amount of $54.50.</li><li>Calculates tip after tax: Calculates the taxes, <code>$50 * .075 = $4.50</code>, for a total check amount of $54.50. Then uses the $54.50 total to calculate suggested tip amounts of $8.06, $9.68, and $10.75.</li></ul> <br/> Note that the total on the check, which is paid to the restaurant, is the same in both cases. The actual tip amount paid directly to the employee is at the guest's discretion. <br/> <strong>Service charge</strong> : For items totalling $1000, a tax rate of 6.25%, and a service charge of 20% (taxed at the same rate), the system either:<ul><li>Calculates tip before tax: Calculates the service charge as <code>$1000 * .20 = $200</code>, for a new subtotal of $1200. Then uses the new subtotal to calculate the tax, <code>$1200 * .0625 = $75</code>, for a total check amount of <code>$1200 + $75 = $1275</code>.</li><li>Calculates tip after tax: Calculates the taxes, <code>$1000 * .0625 = $62.50</code>, for a new subtotal of $1062.50. Then uses the new subtotal to calculate the service charge, <code>$1062.50 * .20 = $212.50</code>. Because this service charge is taxable, the system also calculates the tax on the service charge, <code>$212.50 * .0625 = $13.28</code>. Then adds the service charge and its tax to the subtotal, for a total check amount of <code>$1062.50 + $212.50 + $13.28 = $1288.28</code>.</li></ul> <br/> Note that service charges, unlike tips, are included in the check total and collected by the restaurant. As a result, the setting that you choose for this option can affect the total check amount. <br/> Appropriate variations on these computations apply to service charges that have different tax rates or that are not taxed. <br/> For more information about service charges, see <a href="adminGuide-adminServiceChargeOverview">Service charge overview</a>.</td>
    </tr>
    <tr>
      <td>Tip & signature flow</td>
      <td><ul><li>Combined tip & signature screen <br/> Tip selection and guest signature are on a single screen. This option supports the default tip selection. <blockquote><strong>Note</strong> The default tip selection can be <a href="adminGuide-adminUiOptionsReference#configTipOptionsDefaultPercentage">Default percentage</a>, <a href="adminGuide-adminUiOptionsReference#configTipOptionsDefaultAmount">Default amount</a>, or both depending on your <a href="adminGuide-adminUiOptionsReference#configChooseTipOptions">Tip options</a> setting.</blockquote> </li><li>Legacy tip screen along with the legacy signature screen <br/> Tip selection and guest signature are on separate screens. This option does not support default tip selection.</li></ul></td>
    </tr>
    <tr>
      <td>Tip options</td>
      <td><ul><li>Show tip options in percentages only</li><li>Show tip options in amounts only</li><li>Show tip options in amounts and percentages <br/> For check totals below a specified value, suggested tips appear as dollar amounts. For check totals above the specified value, suggested tips appear as percentages of the total. You use the <a href="adminGuide-adminUiOptionsReference#confTipOptionTransactionAmount">Tip option transaction amount</a> to specify the value.</li></ul></td>
    </tr>
    <tr>
      <td>Tip option transaction amount</td>
      <td>This setting appears if <a href="adminGuide-adminUiOptionsReference#configChooseTipOptions">Tip options</a> is set to Show tip options in amounts and percentages. <br/> This setting determines the total check value used to determine whether the suggested tips are dollar amounts or percentages.</td>
    </tr>
    <tr>
      <td>Tip amounts</td>
      <td>This setting appears if <a href="adminGuide-adminUiOptionsReference#configChooseTipOptions">Tip options</a> is set to either Show tip options in amounts only or Show tip options in amounts and percentages. <br/> You can enter up to three dollar amounts. Each value defines a dollar amount to automatically add as a tip. For example, 1.00, 1.50, 2.00. <blockquote><strong>Note</strong> This field can be reconfigured to accept up to four dollar amounts: choose Payments > Payment methods > Payment options, and set the Tip & signature flow option to Legacy tip screen along with the legacy signature screen.</blockquote> </td>
    </tr>
    <tr>
      <td>Default amount</td>
      <td>This setting appears if <a href="adminGuide-adminUiOptionsReference#configChooseTipOptions">Tip options</a> is set to Show tip options in amounts only. <br/> This setting determines what tipping option is preselected on the guest-facing display.<ul><li>One of the amounts set by <a href="adminGuide-adminUiOptionsReference#confCustomizeTipDollarAmounts">Tip amounts</a>. For example:<ul><li>$1.00</li><li>$1.50</li><li>$2.00</li></ul></li><li>No tip</li><li>None <br/> Select this option if you do not want any of the tip amounts or the No tip option to be preselected on the guest-facing display. The guest must select a suggested tip amount or No tip to proceed.</li></ul></td>
    </tr>
    <tr>
      <td>Tip percentages</td>
      <td>This setting appears if <a href="adminGuide-adminUiOptionsReference#configChooseTipOptions">Tip options</a> is set to either Show tip options in percentages only or Show tip options in amounts and percentages. <br/> You can enter up to three numbers. Each value defines a percentage of the check total to automatically add as a tip. For example, 15, 18, 20. <br/> To include these percentages on guest receipts, you must also enable the Display Tip Percentages on Customer Receipts setting on the Marketing > Receipt Setup page. <blockquote><strong>Note</strong> Previously, this field accepted up to four values. If you prefer this legacy feature, choose Payments > Payment methods > Payment options, and set the Tip & signature flow option to Legacy tip screen along with the legacy signature screen. As a result, this field accepts up to four tip percentage values, but an extra payment step will be presented to guests who pay on a Toast device. This <a href="https://central.toasttab.com/s/article/Basic-Digital-Receipt-Configuration">Toast Central article</a> provides additional information.</blockquote> </td>
    </tr>
    <tr>
      <td>Default percentage</td>
      <td>This setting appears if <a href="adminGuide-adminUiOptionsReference#configChooseTipOptions">Tip options</a> is set to either Show tip options in percentages only or Show tip options in amounts and percentages. <br/> This setting determines what tipping option is preselected on the guest-facing display.<ul><li>One of the amounts set by <a href="adminGuide-adminUiOptionsReference#confCustomizeTipPercentages">Tip percentages</a>. For example:<ul><li>25%</li><li>20%</li><li>18%</li></ul></li><li>No tip</li><li>None <br/> Select this option if you do not want any of the tip pergentages, or the No tip option, to be preselected on the guest-facing display. The guest must select a suggested tip percentage or No tip to proceed.</li></ul></td>
    </tr>
    <tr>
      <td>Require approval?</td>
      <td><ul><li>Yes <br/> Significant adjustments to tips require manager approval</li><li>No <br/> Significant adjustments to tips do not require manager approval</li></ul></td>
    </tr>
    <tr>
      <td>Minimum amount</td>
      <td>This setting appears only if <a href="adminGuide-adminUiOptionsReference#configTipOptionsRequireApproval">Requires approval?</a> is Yes.  <br/> This defines the minimum amount a tip must be to require manager approval.</td>
    </tr>
    <tr>
      <td>Minimum % of balance due</td>
      <td>This setting appears only if <a href="adminGuide-adminUiOptionsReference#configTipOptionsRequireApproval">Requires approval?</a> is Yes.  <br/> This defines the minimum percentage of the check a tip must equal to require manager approval.</td>
    </tr>
  </tbody>
</table>

## Shift review / closeout

The following table provides information about the Advanced shift review setup page settings. To navigate to the Advanced shift review setup page, select Employees &gt; Shift review &gt; Advanced shift review setup.



> **Note**
> 
> If configuring these settings for the first time, select Employees &gt; Shift review &gt; Shift review setup.



<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Require shift review</td>
      <td>This setting determines whether employees must close the checks for all of their orders and declare their cash tips before they clock out.<ul><li>Required <br/> This option requires employees to close all <a href="adminGuide-adminGlossary.html#glossOpenOrder"><em>open</em> </a> and <a href="adminGuide-adminGlossary.html#glossPaidOrder"><em>paid orders</em> </a>, which includes finalizing credit card transactions by adding any tip amounts and closing them.</li><li>Optional <br/> This option allows employees to clock out when their orders are either paid or closed. Shift review does not require entry of a cash tip amount. <blockquote><strong>Note</strong> If your restaurant uses the online ordering feature, select this option to pay and then automatically close all online credit card orders. Credit card receipts for guest signatures do not print; these receipts must be printed manually if needed.</blockquote> </li></ul></td>
    </tr>
    <tr>
      <td>Non-cash tips</td>
      <td><ul><li>Pay out non-cash tips at the end of the shift</li><li>Pay out non-cash tips through payroll</li></ul></td>
    </tr>
    <tr>
      <td>Gratuities (service charges)</td>
      <td><ul><li>Pay out gratuity at the end of the night</li><li>Pay out gratuity through payroll</li></ul></td>
    </tr>
    <tr>
      <td>Who is responsible for closed cash checks?</td>
      <td><ul><li>The person who owns the check</li><li>The person who closes the check</li></ul></td>
    </tr>
    <tr>
      <td>Declare cash tips</td>
      <td><ul><li>Tipped employees must declare cash tips</li><li>Tipped employees do not declare cash tips</li></ul></td>
    </tr>
    <tr>
      <td>Negative cash tips</td>
      <td>This setting appears only if Declare cash tips is Tipped employees must declare cash tips.<ul><li>Allow</li><li>Do not allow</li></ul> <br/> For more information about the effect of these options, see the <a href="adminGuide-adminPermissions#permissionNegativeDeclaredTips">Negative Declared Tips manager access permission</a>.</td>
    </tr>
    <tr>
      <td>Minimum tip percentage</td>
      <td>This setting appears only if <a href="adminGuide-adminUiOptionsReference#configDeclareCashTips">Declare cash tips</a> is Tipped employees must declare cash tips. <br/> The value of this setting defines the minimum amount, as a percentage of cash tips, that employees must report during shift review. <br/> For more information about the effect of this setting, see <a href="adminGuide-adminCashDrawerToastWebOperations#adminCashDrawerToastWebCloseDrawer">Closing cash drawer</a>.</td>
    </tr>
    <tr>
      <td>Require reconcile cash & tips</td>
      <td><ul><li>Employees must turn in any cash sales</li><li>Employees do not have to turn in cash sales</li></ul></td>
    </tr>
    <tr>
      <td>Lock employee to cash drawer</td>
      <td><ul><li>Required</li><li>Optional</li></ul></td>
    </tr>
  </tbody>
</table>

## Report configurations

### Shift review report configurations

The following list contains the sections you can include in the Shift review report. To navigate to the Shift review report page, select Employees &gt; POS report configurations &gt; Shift review report. For more information about these sections, see [Shift review report configurations](adminGuide-platformConfiguringShiftReview#platformShiftReviewReportConfigurations).

The Shift review report setting lists the sections that you can include in your shift review report.

- Employee Account


- Tips & Fees Earned


- My Guest Report


- Credit Tip Audit


- Tip Sharing


- Delivery


- Sales & Taxes Summary


- Cash/Credit Per Sales Category


- Revenue Centers


- Total Voids


- Total Removals


- Total Discounts


- Total Payments


- Credit Card Breakdown


- Other Breakdown


- Employee Signature


- Pay Outs



To include a section in the shift review report, select the checkbox next to the section name under the Show?column.

You also have the option to change the order of the sections. Click or tap and drag the reorder icon next to a section name and move it to a different location in the list.

### Z report configurations

The following list contains the sections you can choose to include in the Z Report. To navigate to the Z Report page, select Front of house &gt; Order screen setup &gt; UI options &gt; Report configurations and follow the link under the Z report configurations section. For more information about these sections, see this [Toast Central article](https://central.toasttab.com/s/article/Close-Out-Day-Z-Report-Auto-Capture#Z_report).

The Z Report setting lists sections that you can include in your [Z report](adminGuide-adminGlossary#glossZReport).

- Sales & Tax Summary


- Sales Categories


- Revenue Centers


- Payment Details


- Server Tip Outs


- Total Voids


- Total Removals


- Total Discounts


- Credit Card Breakdown


- Other Payments Breakdown


- Labor


- Employee Over/Short


- Employee Signature


- Pay Out Breakdown


- Deposit Summary


- Delivery



To include a section on the Z report, select the checkbox next to the section name under the Show?column.

You also have the option to change the sequence in which these sections appear. Click or tap and drag the reorder icon next to a section name and move it to a different location in the list.

### Closed drawer report configurations

The following table provides information about the settings of the Closed Drawer Report page. To navigate to the Closed Drawer Report page, select Payments &gt; Payment methods &gt; Cash overview &gt; POS report configurations &gt; Cash drawer report. For more information about the sections you can include in your closed drawer report, see [this Toast Central article](https://central.toasttab.com/s/article/Closed-Drawer-Report-1492723816056).


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Closed Drawer Report</td>
      <td><ul><li>Automatically print report after closing the drawer.</li><li>Only print the closed drawer report on demand.</li></ul></td>
    </tr>
    <tr>
      <td>Section Name</td>
      <td>This setting lists sections that you can include in your closed drawer report.<ul><li>Cash Summary</li><li>No Sale Audit</li><li>Cash Transaction Detail</li><li>Signatures</li></ul> <br/> To include a section in the closed drawer report, select the checkbox next to the section name under the Show? column. <br/> You also have the option to change the sequence in which these sections appear. Click or tap and drag the reorder icon next to a section name and move it to a different location in the list.</td>
    </tr>
  </tbody>
</table>

## Time clock

The following table provides information about the settings of the Time clock section on the Front of house &gt; Order screen setup &gt; UI options page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Print clock slips</td>
      <td><ul><li>On</li><li>Off</li></ul></td>
    </tr>
    <tr>
      <td>Enforce scheduling</td>
      <td>Only applies to API subscribers who integrate with a third-party clock-in enforcement partner.<ul><li>On</li><li>Off</li></ul></td>
    </tr>
    <tr>
      <td>Show time?</td>
      <td><ul><li>On</li><li>Off</li></ul></td>
    </tr>
    <tr>
      <td>Time entry rounding scheme</td>
      <td>This setting determines how the Toast platform applies rounding to the computation of employee hours. The payroll service that you use, such as Toast Payroll, can affect which option is more appropriate for your location.<ul><li>All time entries are added together, then rounded for total hours <br/> This option retains full precision for calculations of the length of time between employee clock in and clock out. All time periods are summed and then rounded to two decimal places. This is the default option. <blockquote><strong>Note</strong> Toast labor reports, including the Time Entries report, limit the precision shown for time periods to two decimal places. This limitation can result in differences between the length of time that the system uses to determine pay and the time periods shown on the report.</blockquote> </li><li>Each time entry is rounded, then added together for total hours <br/> This option rounds the length of time calculated between employee clock in and clock out to two decimal places. All time periods are then summed. Select this option if you use Toast Payroll, or are directed to do so by an integration partner offering a payroll service. <blockquote><strong>Note</strong> When you select this option and publish, the Toast platform recalculates all employee hours and pay from January 1, 2019 through publication.</blockquote> </li></ul></td>
    </tr>
  </tbody>
</table>

## Tax options

The following table provides information about the settings of the Tax options section on the Front of house &gt; Order screen setup &gt; UI options page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Receipt tax options > Layout</td>
      <td><ul><li>One line</li><li>Separate lines</li></ul></td>
    </tr>
    <tr>
      <td>Receipt tax options > Label</td>
      <td>This setting appears only if Receipt Tax options > Layout is One line. <br/> The label appears on printed guest receipts to identify the total amount charged as tax. This setting accepts a text string.</td>
    </tr>
    <tr>
      <td>Smart tax</td>
      <td><ul><li>On</li><li>Off</li></ul>For more information, see <a href="adminGuide-adminSmartTax">Smart tax</a>.</td>
    </tr>
  </tbody>
</table>

## Order management

The following table provides information about the settings of the Order management section on the Front of house &gt; Order screen setup &gt; UI options page.


<table>
  <thead>
    <tr>
      <th>Setting</th>
      <th>Options and description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Strict mode</td>
      <td><ul><li>On</li><li>Off</li></ul>For more information about Strict mode, see <a href="https://central.toasttab.com/s/article/Enabling-Strict-Mode-1492810276171">this Toast Central article</a>.</td>
    </tr>
  </tbody>
</table>

