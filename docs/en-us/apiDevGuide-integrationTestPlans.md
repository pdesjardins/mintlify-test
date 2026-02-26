---
title: "Integration test plans"
id: integrationTestPlans
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalChecklistsAndTestPlansOmitChunkFromSearchIndex.md
parentSectionTitle: "Checklists and test plans"
previousSectionFile: apiDevGuide-checklistsforSpecificIntegrationFunctionality.md
previousSectionTitle: "Checklists for specific integration functionality"
nextSectionFile: apiDevGuide-apiOrdersOmitChunkFromSearchIndex.md
nextSectionTitle: "Chapter 2. Orders"
excerpt: "You can use these test plans to validate your integrations."
procedures: 0
codeExamples: 0
---

You can use these test plans to validate your integrations.

## Gift card integration test plan

You can use this test plan while you build your gift card integration. Your integration should be able to successfully complete all cases in this plan before it goes live.

You should also ensure that your integration successfully [authenticates](apiDevGuide-apiGiftCardIntegrationAuthentication)the JSON objects you receive.

You can [download a CSV version of this test plan](toast-api-integration-checklist-giftcard.csv).


<table>
  <thead>
    <tr>
      <th>Case number</th>
      <th>Card type</th>
      <th>Test case name</th>
      <th>Steps</th>
      <th>Expected results</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Non-Existent Card</td>
      <td>Add Value</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Gift Cards &gt; Add Value ($).<br/>Enter any value, and click Next.<br/>Swipe or enter a number not associated with a gift card at that restaurant.</td>
      <td>Gift card cannot be founderror message appears.</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Non-Existent Card</td>
      <td>Balance Inquiry</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Gift Cards &gt; Balance Inquiry.<br/>Swipe or enter a number not associated with a gift card at that restaurant.</td>
      <td>Gift card cannot be founderror message appears.</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Non-Existent Card</td>
      <td>Redeem</td>
      <td>From the Toast POS app &gt; New Order.<br/>Add items to your order.<br/>Click Pay.<br/>Click Gift Card.<br/>Swipe or enter a number not associated with a gift card at that restaurant.</td>
      <td>Gift card cannot be founderror message appears.</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Non-Existent Card</td>
      <td>Sell Card</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Gift Cards &gt; Sell Card.<br/>Enter any value, and click `Next`.<br/>Swipe or enter a number not associated with a gift card at the restaurant.</td>
      <td>Gift card cannot be founderror message appears.</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Inactive Card</td>
      <td>Add Value</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Gift Cards &gt; Add Value ($).<br/>Enter any value, and click Next.<br/>Swipe an inactive gift card.</td>
      <td>The gift card is inactiveerror message appears.</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Inactive Card</td>
      <td>Balance Inquiry</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Gift Cards &gt; Balance Inquiry.<br/>Swipe an inactive gift card.</td>
      <td>The gift card is inactiveerror message appears.</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Inactive Card</td>
      <td>Redeem</td>
      <td>From the Toast POS app &gt; New Order.<br/>Add items to your order.<br/>Click Pay.<br/>Click Gift Card.<br/>Swipe an inactive gift card.</td>
      <td>The gift card is inactiveerror message appears.</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Inactive Card</td>
      <td>Sell Card</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Gift Cards &gt; Sell Card.<br/>Enter any value, and click Next.<br/>Swipe inactive gift card.</td>
      <td>The gift card should display as an item selection on the check, for the amount for which you sold it.</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Inactive Card</td>
      <td>Sell Card</td>
      <td>Pay cash for the check you created in case 8, which contains the gift card.</td>
      <td>You should be able to sell and pay for the gift card successfully.</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Inactive Card</td>
      <td>Sell Card</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Gift Cards &gt; Balance Inquiry.<br/>Swipe the gift card.</td>
      <td>The gift card's balance should be the amount for which you sold it.</td>
    </tr>
    <tr>
      <td>11</td>
      <td>Inactive Card</td>
      <td>Reverse Sell Card</td>
      <td>Follow the steps from case 8.<br/>From the Toast POS app, navigate to the Closed Orders tab.<br/>Locate the check from your card sale.<br/>Click Update, then Pay, then Void. Confirm the void operation.<br/>In the overflow menu, click Void Order. Confirm the void operation.<br/>Create a new order.<br/>Click Gift Card.<br/>Click Balance Inquiry.<br/>Enter in the card number for the gift card you originally sold.<br/>Click Done.</td>
      <td>The gift card is inactiveerror message appears.</td>
    </tr>
    <tr>
      <td>12</td>
      <td>Active Card</td>
      <td>Balance Inquiry</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Gift Cards &gt; Balance Inquiry.<br/>Swipe active gift card.</td>
      <td>The balance should be the correct and expected balance on the card.</td>
    </tr>
    <tr>
      <td>13</td>
      <td>Active Card</td>
      <td>Redeem Full Order</td>
      <td>From the Toast POS app &gt; New Order.<br/>Add items to your order.<br/>Ensure that the total amount due is less than the amount on the gift card.<br/>Click Pay.<br/>Click Gift Card.<br/>Swipe an active gift card.</td>
      <td>The order should go to the Paid Checks tab on the POS, and it should have a gift card payment for the full order amount.</td>
    </tr>
    <tr>
      <td>14</td>
      <td>Active Card</td>
      <td>Redeem Full Order</td>
      <td>Run a balance inquiry on the card used in case 13.</td>
      <td>The balance should be decremented by the amount of the previous order.</td>
    </tr>
    <tr>
      <td>15</td>
      <td>Active Card</td>
      <td>Redeem Partial Order</td>
      <td>From the Toast POS app &gt; New Order.<br/>Add items to your order.<br/>Ensure the total amount due is more than the amount on the gift card.<br/>Click Pay.<br/>Click Gift Card.<br/>Swipe an active gift card.</td>
      <td>The Payments screen will open.<br/>Verify that there is a gift card payment for the full amount of the gift card in the payments list.<br/>Verify that there is a balance due.</td>
    </tr>
    <tr>
      <td>16</td>
      <td>Active Card</td>
      <td>Redeem Partial Order</td>
      <td>Complete the order from case 15 with a second payment.</td>
      <td>The order should appear on the Paid Checks tab.</td>
    </tr>
    <tr>
      <td>17</td>
      <td>Active Card</td>
      <td>Redeem Partial Order</td>
      <td>Run a balance inquiry on the card used in case 16.</td>
      <td>The card balance should be $0.</td>
    </tr>
    <tr>
      <td>18</td>
      <td>Active Card</td>
      <td>Reverse Redeem</td>
      <td>On the Paid Checks tab, locate one of the orders created and paid for in one of the previous two tests.<br/>Click Pay ($).<br/>Note the card number you use to pay for this order, and the amount of money for which you redeem it.<br/>Click each payment and press Remove / Void.<br/>In the overflow menu, clock Void Order.<br/>Create a new order.<br/>Run a balance inquiry on the gift card for which you voided the payment.</td>
      <td>The card balance should be incremented by the amount of the voided payment.</td>
    </tr>
    <tr>
      <td>19</td>
      <td>Active Card</td>
      <td>Tip Without Digital Receipts</td>
      <td>On the the Toast POS app home screen, navigate to the Setup section and click Device Setup.<br/>Turn off digital receipts.<br/>From the home screen, in the Mode section, click Payment Terminal.<br/>Create an order worth less than the value of an active gift card.<br/>Click Pay.<br/>Click Gift Card.<br/>On the Paid Checks tab, locate the previous check and click Pay ($).<br/>Enter in a tip that the gift card has enough money to cover.<br/>Click Update, and then Close.</td>
      <td>The check should be moved to the Closed Checks tab.</td>
    </tr>
    <tr>
      <td>20</td>
      <td>Active Card</td>
      <td>Tip Without Digital Receipts</td>
      <td>Run a balance inquiry on the card used in case 19.</td>
      <td>The balance on the card should be decremented by the amount of the check and tip.</td>
    </tr>
    <tr>
      <td>21</td>
      <td>Active Card</td>
      <td>Tip With Digital Receipts</td>
      <td>On the the Toast POS app home screen, navigate to the Setup section and click Device Setup.<br/>Turn Digital Receipts on.<br/>From the home screen, in the Mode section, click Payment Terminal.<br/>Create an order worth less than the value on an active gift card.<br/>Click Pay.<br/>Click Gift Card.<br/>When the tip dialog appears, select a tip amount less than the gift card balance. This dialog does not allow you to tip more than the balance on the card.<br/>Complete the order.</td>
      <td>The check should be moved to the Closed Checks tab.</td>
    </tr>
    <tr>
      <td>22</td>
      <td>Active Card</td>
      <td>Tip With Digital Receipts</td>
      <td>Get the balance of the card used in case 21.</td>
      <td>The balance on the card should be decremented by the amount of the check and tip.</td>
    </tr>
    <tr>
      <td>23</td>
      <td>Active Card</td>
      <td>Add Value</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Gift Cards &gt; Add Value ($).<br/>Enter any value, and click Next.<br/>Swipe an active gift card.</td>
      <td>Verify that Add Value ($) is added to the check for the correct amount.</td>
    </tr>
    <tr>
      <td>24</td>
      <td>Active Card</td>
      <td>Add Value</td>
      <td>Complete the order from case 23.</td>
      <td>The check should move to the Closed Checks tab.</td>
    </tr>
    <tr>
      <td>25</td>
      <td>Active Card</td>
      <td>Add Value</td>
      <td>Run a balance inquiry on the card used in cases 23-24.</td>
      <td>The card balance should be increased by the correct amount.</td>
    </tr>
    <tr>
      <td>26</td>
      <td>Active Card</td>
      <td>Reverse Add Value</td>
      <td>On the Closed Checks tab, find the order created in case 25.<br/>Click Pay ($).<br/>Void all payments.<br/>In the overflow menu, click Void Order.<br/>Confirm the void operation.<br/>Create a new order.<br/>Click Gift Card and then click Balance Inquiry.<br/>Swipe the card whose Add Value action was voided.</td>
      <td>The gift card balance should be decremented by the voided Add Value action.</td>
    </tr>
  </tbody>
</table>

## Loyalty integration test plan

You can use this test plan while you build your gift card integration. Your integration should be able to successfully complete all cases in this plan before it goes live.

You should also ensure that your integration successfully [authenticates](apiDevGuide-apiLoyaltyIntegrationAuthentication)the JSON objects that you receive.

You can [download a CSV version of this test plan](toast-api-integration-checklist-loyalty.csv).


<table>
  <thead>
    <tr>
      <th>Case number</th>
      <th>Category</th>
      <th>Test case</th>
      <th>Steps</th>
      <th>Expected results</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Account Lookup</td>
      <td>Card swipe</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Swipe a card associated with a loyalty account at that restaurant.</td>
      <td>The expected loyalty account should appear.</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Account Lookup</td>
      <td>Card swipe</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Swipe a card NOT associated with a loyalty account at that restaurant.</td>
      <td>The Invalid Account error message should appear.</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Account Lookup</td>
      <td>Card swipe</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Swipe a card that is NOT a loyalty account card.</td>
      <td>The Card swiped is not a rewards card error message should appear.</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Account Lookup</td>
      <td>Keying in number</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Key in a card number associated with a loyalty account at that restaurant.</td>
      <td>The expected loyalty account should appear.</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Account Lookup</td>
      <td>Scanning QR code</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer &gt; Scan.<br/>Scan a QR code associated with a loyalty account at that restaurant.</td>
      <td>The expected loyalty account should appear.</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Account Lookup</td>
      <td>Scanning QR code</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer &gt; Scan.<br/>Scan a QR code NOT associated with a loyalty account at that restaurant.</td>
      <td>The Invalid Account error message should appear.</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Account Lookup</td>
      <td>By email</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer &gt; Lookup.<br/>Key in an email address associated with a loyalty account at that restaurant.</td>
      <td>The expected loyalty account should appear.</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Account Lookup</td>
      <td>By phone number</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer &gt; Lookup.<br/>Key in a phone number associated with a loyalty account at that restaurant.</td>
      <td>The expected loyalty account should appear.</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Account Lookup</td>
      <td>By name</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer &gt; Lookup.<br/>Key in a name associated with a loyalty account at that restaurant.</td>
      <td>The expected loyalty account should appear.</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Account Inquiry</td>
      <td>Unavailable rewards</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Look up a loyalty account that has associated rewards.</td>
      <td>The expected rewards value should display, but because the awards are unavailable for redemption, you should not be able to apply them to a check.</td>
    </tr>
    <tr>
      <td>11</td>
      <td>Account Inquiry</td>
      <td>Available rewards</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Look up a loyalty account that has associated rewards.<br/>Add items that would trigger rewards to the check.<br/>Tap Rewards &gt; Look Up Customer.</td>
      <td>The expected rewards should be available redemption.<br/>A Redeem button should be present.</td>
    </tr>
    <tr>
      <td>12</td>
      <td>Account Inquiry</td>
      <td>Rewards points</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Look up a loyalty account that has associated rewards.</td>
      <td>The expected rewards value should display on the dialog.</td>
    </tr>
    <tr>
      <td>13</td>
      <td>Account Inquiry</td>
      <td>Invalidated rewards</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Look up a loyalty account that has associated rewards.<br/>Add items that would trigger rewards to the check.<br/>Tap Rewards &gt; Look Up Customer.<br/>Remove the items from your check.<br/>Tap Rewards &gt; Look Up Customer.</td>
      <td>The reward should be removed from the check.<br/>The error message Changes to the check have voided applied rewards. Discounts that are no longer applicable have been removed should display.</td>
    </tr>
    <tr>
      <td>14</td>
      <td>Redemption</td>
      <td>Item-level discount</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Look up a loyalty account that has associated rewards.<br/>Add items that would trigger rewards to the check.<br/>Tap Rewards &gt; Look Up Customer.<br/>Tap Redeemto add a reward to the check.</td>
      <td>The reward should apply to the target item on the check.<br/>The amount discounted should be correct.</td>
    </tr>
    <tr>
      <td>15</td>
      <td>Redemption</td>
      <td>Item-level discount</td>
      <td>Tap Pay.</td>
      <td>The reward discount should be correctly carried to the payment screen.</td>
    </tr>
    <tr>
      <td>16</td>
      <td>Redemption</td>
      <td>Item-level discount</td>
      <td>Complete payment on the check.</td>
      <td>The payment should process successfully.</td>
    </tr>
    <tr>
      <td>17</td>
      <td>Redemption</td>
      <td>Check-level discount</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Look up a loyalty account that has associated rewards.<br/>Add items that would trigger rewards to the check.<br/>Tap Rewards &gt; Look Up Customer.<br/>Tap Redeemto add a reward to the check.</td>
      <td>The reward should apply to the check.<br/>The amount discounted should be correct.</td>
    </tr>
    <tr>
      <td>18</td>
      <td>Redemption</td>
      <td>Check-level discount</td>
      <td>Tap Pay.</td>
      <td>The reward discount should be correctly carried to the payment screen.</td>
    </tr>
    <tr>
      <td>19</td>
      <td>Redemption</td>
      <td>Check-level discount</td>
      <td>Complete payment on the check.</td>
      <td>The payment should process successfully.</td>
    </tr>
    <tr>
      <td>20</td>
      <td>Redemption</td>
      <td>Buy one get one discount</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Look up a loyalty account that has associated rewards.<br/>Add items that would trigger rewards to the check.<br/>Tap Rewards &gt; Look Up Customer.</td>
      <td>The expected reward should display, but should be unavailable for redemption.</td>
    </tr>
    <tr>
      <td>21</td>
      <td>Redemption</td>
      <td>Buy one get one discount</td>
      <td>Add items that would trigger rewards to the check.<br/>Tap Rewards &gt; Look Up Customer.</td>
      <td>The expected rewards should be available redemption.<br/>A Redeem button should be present.</td>
    </tr>
    <tr>
      <td>22</td>
      <td>Redemption</td>
      <td>Buy one get one discount</td>
      <td>Tap Redeem to add a reward to the check.</td>
      <td>The reward should apply to the target item on the check.<br/>The amount discounted should be correct.</td>
    </tr>
    <tr>
      <td>23</td>
      <td>Redemption</td>
      <td>Buy one get one discount</td>
      <td>Tap Pay.</td>
      <td>The reward discount should be correctly carried to the payment screen.</td>
    </tr>
    <tr>
      <td>24</td>
      <td>Redemption</td>
      <td>Buy one get one discount</td>
      <td>Complete payment on the check.</td>
      <td>The payment should process successfully.</td>
    </tr>
    <tr>
      <td>25</td>
      <td>Accrual and Reversal</td>
      <td>Without reward applied to check</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Look up a loyalty account that has associated rewards.<br/>Add items to the check.<br/>Tap Pay($).</td>
      <td>The payment should process successfully.<br/>You should see the expected accrual message.</td>
    </tr>
    <tr>
      <td>26</td>
      <td>Accrual and Reversal</td>
      <td>Accrual reverse</td>
      <td>On the Closed Checks tab, find the order placed in case 25.<br/>Tap Pay($).<br/>Void all payments.<br/>In the overflow menu, clock Void Order.<br/>Confirm the void operation.</td>
      <td>The check should be successfully voided in Toast.<br/>You should see the expected reversal message.</td>
    </tr>
    <tr>
      <td>27</td>
      <td>Accrual and Reversal</td>
      <td>With reward applied to check</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Look up a loyalty account that has associated rewards.<br/>Add items that would trigger rewards to the check.<br/>Tap Rewards &gt; Look Up Customer.<br/>Tap Redeemto add a reward to the check.<br/>Tap Pay.<br/>Complete payment on the check.</td>
      <td>The payment should process successfully.<br/>You should see the expected accrual and redeem messages.</td>
    </tr>
    <tr>
      <td>28</td>
      <td>Accrual and Reversal</td>
      <td>Redemption reverse</td>
      <td>On the Closed Checks tab, find the order placed in case 27.<br/>Tap Pay($).<br/>Void all payments.<br/>In the overflow menu, click Void Order.<br/>Confirm the void operation.</td>
      <td>The check should be successfully voided in Toast,.<br/>You should see the expected reversal messages.</td>
    </tr>
    <tr>
      <td>29</td>
      <td>Accrual and Reversal</td>
      <td>With multiple rewards applied to check</td>
      <td>From the Toast POS app &gt; New Order.<br/>Tap Rewards&gt; Look Up Customer.<br/>Look up a loyalty account that has associated rewards.<br/>Add items that would trigger rewards to the check.<br/>Tap Rewards &gt; Look Up Customer.<br/>Tap Redeemto add a reward to the check.<br/>Repeat at least once in order to apply multiple rewards to the check.<br/>Tap Pay.<br/>Complete payment on the check.</td>
      <td>The payment should process successfully.<br/>You should see the expected accrual and redeem messages.</td>
    </tr>
    <tr>
      <td>30</td>
      <td>Accrual and Reversal</td>
      <td>Partial redemption reverse</td>
      <td>On the Closed Checks tab, find the order placed in case 29.<br/>Tap Update.<br/>Select a reward that was redeemed, and void it from the check.<br/>Tap Pay.<br/>Complete payment on the check.</td>
      <td>The check should successfully close.<br/>You should see the expected reversal messages.</td>
    </tr>
  </tbody>
</table>

