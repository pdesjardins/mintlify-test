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


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Case number</div></th>
      <th className=""><div className="">Card type</div></th>
      <th className=""><div className="">Test case name</div></th>
      <th className=""><div className="">Steps</div></th>
      <th className=""><div className="">Expected results</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">1</div></td>
      <td className=""><div className="">Non-Existent Card</div></td>
      <td className=""><div className="">Add Value</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Gift Cards &gt; Add Value ($). <br/> Enter any value, and click Next. <br/> Swipe or enter a number not associated with a gift card at that restaurant.</div></td>
      <td className=""><div className="">Gift card cannot be found error message appears.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">2</div></td>
      <td className=""><div className="">Non-Existent Card</div></td>
      <td className=""><div className="">Balance Inquiry</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Gift Cards &gt; Balance Inquiry. <br/> Swipe or enter a number not associated with a gift card at that restaurant.</div></td>
      <td className=""><div className="">Gift card cannot be found error message appears.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">3</div></td>
      <td className=""><div className="">Non-Existent Card</div></td>
      <td className=""><div className="">Redeem</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Add items to your order. <br/> Click Pay. <br/> Click Gift Card. <br/> Swipe or enter a number not associated with a gift card at that restaurant.</div></td>
      <td className=""><div className="">Gift card cannot be found error message appears.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">4</div></td>
      <td className=""><div className="">Non-Existent Card</div></td>
      <td className=""><div className="">Sell Card</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Gift Cards &gt; Sell Card. <br/> Enter any value, and click <code className="">Next</code>. <br/> Swipe or enter a number not associated with a gift card at the restaurant.</div></td>
      <td className=""><div className="">Gift card cannot be found error message appears.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">5</div></td>
      <td className=""><div className="">Inactive Card</div></td>
      <td className=""><div className="">Add Value</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Gift Cards &gt; Add Value ($). <br/> Enter any value, and click Next. <br/> Swipe an inactive gift card.</div></td>
      <td className=""><div className="">The gift card is inactive error message appears.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">6</div></td>
      <td className=""><div className="">Inactive Card</div></td>
      <td className=""><div className="">Balance Inquiry</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Gift Cards &gt; Balance Inquiry. <br/> Swipe an inactive gift card.</div></td>
      <td className=""><div className="">The gift card is inactive error message appears.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">7</div></td>
      <td className=""><div className="">Inactive Card</div></td>
      <td className=""><div className="">Redeem</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Add items to your order. <br/> Click Pay. <br/> Click Gift Card. <br/> Swipe an inactive gift card.</div></td>
      <td className=""><div className="">The gift card is inactive error message appears.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">8</div></td>
      <td className=""><div className="">Inactive Card</div></td>
      <td className=""><div className="">Sell Card</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Gift Cards &gt; Sell Card. <br/> Enter any value, and click Next. <br/> Swipe inactive gift card.</div></td>
      <td className=""><div className="">The gift card should display as an item selection on the check, for the amount for which you sold it.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">9</div></td>
      <td className=""><div className="">Inactive Card</div></td>
      <td className=""><div className="">Sell Card</div></td>
      <td className=""><div className="">Pay cash for the check you created in case 8, which contains the gift card.</div></td>
      <td className=""><div className="">You should be able to sell and pay for the gift card successfully.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">10</div></td>
      <td className=""><div className="">Inactive Card</div></td>
      <td className=""><div className="">Sell Card</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Gift Cards &gt; Balance Inquiry. <br/> Swipe the gift card.</div></td>
      <td className=""><div className="">The gift card's balance should be the amount for which you sold it.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">11</div></td>
      <td className=""><div className="">Inactive Card</div></td>
      <td className=""><div className="">Reverse Sell Card</div></td>
      <td className=""><div className="">Follow the steps from case 8. <br/> From the Toast POS app, navigate to the Closed Orders tab. <br/> Locate the check from your card sale. <br/> Click Update, then Pay, then Void. Confirm the void operation. <br/> In the overflow menu, click Void Order. Confirm the void operation. <br/> Create a new order. <br/> Click Gift Card. <br/> Click Balance Inquiry. <br/> Enter in the card number for the gift card you originally sold. <br/> Click Done.</div></td>
      <td className=""><div className="">The gift card is inactive error message appears.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">12</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Balance Inquiry</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Gift Cards &gt; Balance Inquiry. <br/> Swipe active gift card.</div></td>
      <td className=""><div className="">The balance should be the correct and expected balance on the card.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">13</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Redeem Full Order</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Add items to your order. <br/> Ensure that the total amount due is less than the amount on the gift card. <br/> Click Pay. <br/> Click Gift Card. <br/> Swipe an active gift card.</div></td>
      <td className=""><div className="">The order should go to the Paid Checks tab on the POS, and it should have a gift card payment for the full order amount.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">14</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Redeem Full Order</div></td>
      <td className=""><div className="">Run a balance inquiry on the card used in case 13.</div></td>
      <td className=""><div className="">The balance should be decremented by the amount of the previous order.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">15</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Redeem Partial Order</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Add items to your order. <br/> Ensure the total amount due is more than the amount on the gift card. <br/> Click Pay. <br/> Click Gift Card. <br/> Swipe an active gift card.</div></td>
      <td className=""><div className="">The Payments screen will open. <br/> Verify that there is a gift card payment for the full amount of the gift card in the payments list. <br/> Verify that there is a balance due.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">16</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Redeem Partial Order</div></td>
      <td className=""><div className="">Complete the order from case 15 with a second payment.</div></td>
      <td className=""><div className="">The order should appear on the Paid Checks tab.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">17</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Redeem Partial Order</div></td>
      <td className=""><div className="">Run a balance inquiry on the card used in case 16.</div></td>
      <td className=""><div className="">The card balance should be $0.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">18</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Reverse Redeem</div></td>
      <td className=""><div className="">On the Paid Checks tab, locate one of the orders created and paid for in one of the previous two tests. <br/> Click Pay ($). <br/> Note the card number you use to pay for this order, and the amount of money for which you redeem it. <br/> Click each payment and press Remove / Void. <br/> In the overflow menu, clock Void Order. <br/> Create a new order. <br/> Run a balance inquiry on the gift card for which you voided the payment.</div></td>
      <td className=""><div className="">The card balance should be incremented by the amount of the voided payment.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">19</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Tip Without Digital Receipts</div></td>
      <td className=""><div className="">On the the Toast POS app home screen, navigate to the Setup section and click Device Setup. <br/> Turn off digital receipts. <br/> From the home screen, in the Mode section, click Payment Terminal. <br/> Create an order worth less than the value of an active gift card. <br/> Click Pay. <br/> Click Gift Card. <br/> On the Paid Checks tab, locate the previous check and click Pay ($). <br/> Enter in a tip that the gift card has enough money to cover. <br/> Click Update, and then Close.</div></td>
      <td className=""><div className="">The check should be moved to the Closed Checks tab.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">20</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Tip Without Digital Receipts</div></td>
      <td className=""><div className="">Run a balance inquiry on the card used in case 19.</div></td>
      <td className=""><div className="">The balance on the card should be decremented by the amount of the check and tip.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">21</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Tip With Digital Receipts</div></td>
      <td className=""><div className="">On the the Toast POS app home screen, navigate to the Setup section and click Device Setup. <br/> Turn Digital Receipts on. <br/> From the home screen, in the Mode section, click Payment Terminal. <br/> Create an order worth less than the value on an active gift card. <br/> Click Pay. <br/> Click Gift Card. <br/> When the tip dialog appears, select a tip amount less than the gift card balance. This dialog does not allow you to tip more than the balance on the card. <br/> Complete the order.</div></td>
      <td className=""><div className="">The check should be moved to the Closed Checks tab.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">22</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Tip With Digital Receipts</div></td>
      <td className=""><div className="">Get the balance of the card used in case 21.</div></td>
      <td className=""><div className="">The balance on the card should be decremented by the amount of the check and tip.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">23</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Add Value</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Gift Cards &gt; Add Value ($). <br/> Enter any value, and click Next. <br/> Swipe an active gift card.</div></td>
      <td className=""><div className="">Verify that Add Value ($) is added to the check for the correct amount.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">24</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Add Value</div></td>
      <td className=""><div className="">Complete the order from case 23.</div></td>
      <td className=""><div className="">The check should move to the Closed Checks tab.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">25</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Add Value</div></td>
      <td className=""><div className="">Run a balance inquiry on the card used in cases 23-24.</div></td>
      <td className=""><div className="">The card balance should be increased by the correct amount.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">26</div></td>
      <td className=""><div className="">Active Card</div></td>
      <td className=""><div className="">Reverse Add Value</div></td>
      <td className=""><div className="">On the Closed Checks tab, find the order created in case 25. <br/> Click Pay ($). <br/> Void all payments. <br/> In the overflow menu, click Void Order. <br/> Confirm the void operation. <br/> Create a new order. <br/> Click Gift Card and then click Balance Inquiry. <br/> Swipe the card whose Add Value action was voided.</div></td>
      <td className=""><div className="">The gift card balance should be decremented by the voided Add Value action.</div></td>
    </tr>
  </tbody>
</table>
</div>

## Loyalty integration test plan

You can use this test plan while you build your gift card integration. Your integration should be able to successfully complete all cases in this plan before it goes live.

You should also ensure that your integration successfully [authenticates](apiDevGuide-apiLoyaltyIntegrationAuthentication)the JSON objects that you receive.

You can [download a CSV version of this test plan](toast-api-integration-checklist-loyalty.csv).


<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Case number</div></th>
      <th className=""><div className="">Category</div></th>
      <th className=""><div className="">Test case</div></th>
      <th className=""><div className="">Steps</div></th>
      <th className=""><div className="">Expected results</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">1</div></td>
      <td className=""><div className="">Account Lookup</div></td>
      <td className=""><div className="">Card swipe</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Swipe a card associated with a loyalty account at that restaurant.</div></td>
      <td className=""><div className="">The expected loyalty account should appear.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">2</div></td>
      <td className=""><div className="">Account Lookup</div></td>
      <td className=""><div className="">Card swipe</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Swipe a card NOT associated with a loyalty account at that restaurant.</div></td>
      <td className=""><div className="">The Invalid Account error message should appear.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">3</div></td>
      <td className=""><div className="">Account Lookup</div></td>
      <td className=""><div className="">Card swipe</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Swipe a card that is NOT a loyalty account card.</div></td>
      <td className=""><div className="">The Card swiped is not a rewards card error message should appear.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">4</div></td>
      <td className=""><div className="">Account Lookup</div></td>
      <td className=""><div className="">Keying in number</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Key in a card number associated with a loyalty account at that restaurant.</div></td>
      <td className=""><div className="">The expected loyalty account should appear.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">5</div></td>
      <td className=""><div className="">Account Lookup</div></td>
      <td className=""><div className="">Scanning QR code</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer &gt; Scan. <br/> Scan a QR code associated with a loyalty account at that restaurant.</div></td>
      <td className=""><div className="">The expected loyalty account should appear.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">6</div></td>
      <td className=""><div className="">Account Lookup</div></td>
      <td className=""><div className="">Scanning QR code</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer &gt; Scan. <br/> Scan a QR code NOT associated with a loyalty account at that restaurant.</div></td>
      <td className=""><div className="">The Invalid Account error message should appear.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">7</div></td>
      <td className=""><div className="">Account Lookup</div></td>
      <td className=""><div className="">By email</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer &gt; Lookup. <br/> Key in an email address associated with a loyalty account at that restaurant.</div></td>
      <td className=""><div className="">The expected loyalty account should appear.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">8</div></td>
      <td className=""><div className="">Account Lookup</div></td>
      <td className=""><div className="">By phone number</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer &gt; Lookup. <br/> Key in a phone number associated with a loyalty account at that restaurant.</div></td>
      <td className=""><div className="">The expected loyalty account should appear.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">9</div></td>
      <td className=""><div className="">Account Lookup</div></td>
      <td className=""><div className="">By name</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer &gt; Lookup. <br/> Key in a name associated with a loyalty account at that restaurant.</div></td>
      <td className=""><div className="">The expected loyalty account should appear.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">10</div></td>
      <td className=""><div className="">Account Inquiry</div></td>
      <td className=""><div className="">Unavailable rewards</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Look up a loyalty account that has associated rewards.</div></td>
      <td className=""><div className="">The expected rewards value should display, but because the awards are unavailable for redemption, you should not be able to apply them to a check.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">11</div></td>
      <td className=""><div className="">Account Inquiry</div></td>
      <td className=""><div className="">Available rewards</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Look up a loyalty account that has associated rewards. <br/> Add items that would trigger rewards to the check. <br/> Tap Rewards &gt; Look Up Customer.</div></td>
      <td className=""><div className="">The expected rewards should be available redemption. <br/> A Redeem button should be present.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">12</div></td>
      <td className=""><div className="">Account Inquiry</div></td>
      <td className=""><div className="">Rewards points</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Look up a loyalty account that has associated rewards.</div></td>
      <td className=""><div className="">The expected rewards value should display on the dialog.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">13</div></td>
      <td className=""><div className="">Account Inquiry</div></td>
      <td className=""><div className="">Invalidated rewards</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Look up a loyalty account that has associated rewards. <br/> Add items that would trigger rewards to the check. <br/> Tap Rewards &gt; Look Up Customer. <br/> Remove the items from your check. <br/> Tap Rewards &gt; Look Up Customer.</div></td>
      <td className=""><div className="">The reward should be removed from the check. <br/> The error message Changes to the check have voided applied rewards. Discounts that are no longer applicable have been removed should display.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">14</div></td>
      <td className=""><div className="">Redemption</div></td>
      <td className=""><div className="">Item-level discount</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Look up a loyalty account that has associated rewards. <br/> Add items that would trigger rewards to the check. <br/> Tap Rewards &gt; Look Up Customer. <br/> Tap Redeem to add a reward to the check.</div></td>
      <td className=""><div className="">The reward should apply to the target item on the check. <br/> The amount discounted should be correct.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">15</div></td>
      <td className=""><div className="">Redemption</div></td>
      <td className=""><div className="">Item-level discount</div></td>
      <td className=""><div className="">Tap Pay.</div></td>
      <td className=""><div className="">The reward discount should be correctly carried to the payment screen.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">16</div></td>
      <td className=""><div className="">Redemption</div></td>
      <td className=""><div className="">Item-level discount</div></td>
      <td className=""><div className="">Complete payment on the check.</div></td>
      <td className=""><div className="">The payment should process successfully.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">17</div></td>
      <td className=""><div className="">Redemption</div></td>
      <td className=""><div className="">Check-level discount</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Look up a loyalty account that has associated rewards. <br/> Add items that would trigger rewards to the check. <br/> Tap Rewards &gt; Look Up Customer. <br/> Tap Redeem to add a reward to the check.</div></td>
      <td className=""><div className="">The reward should apply to the check. <br/> The amount discounted should be correct.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">18</div></td>
      <td className=""><div className="">Redemption</div></td>
      <td className=""><div className="">Check-level discount</div></td>
      <td className=""><div className="">Tap Pay.</div></td>
      <td className=""><div className="">The reward discount should be correctly carried to the payment screen.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">19</div></td>
      <td className=""><div className="">Redemption</div></td>
      <td className=""><div className="">Check-level discount</div></td>
      <td className=""><div className="">Complete payment on the check.</div></td>
      <td className=""><div className="">The payment should process successfully.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">20</div></td>
      <td className=""><div className="">Redemption</div></td>
      <td className=""><div className="">Buy one get one discount</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Look up a loyalty account that has associated rewards. <br/> Add items that would trigger rewards to the check. <br/> Tap Rewards &gt; Look Up Customer.</div></td>
      <td className=""><div className="">The expected reward should display, but should be unavailable for redemption.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">21</div></td>
      <td className=""><div className="">Redemption</div></td>
      <td className=""><div className="">Buy one get one discount</div></td>
      <td className=""><div className="">Add items that would trigger rewards to the check. <br/> Tap Rewards &gt; Look Up Customer.</div></td>
      <td className=""><div className="">The expected rewards should be available redemption. <br/> A Redeem button should be present.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">22</div></td>
      <td className=""><div className="">Redemption</div></td>
      <td className=""><div className="">Buy one get one discount</div></td>
      <td className=""><div className="">Tap Redeem to add a reward to the check.</div></td>
      <td className=""><div className="">The reward should apply to the target item on the check. <br/> The amount discounted should be correct.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">23</div></td>
      <td className=""><div className="">Redemption</div></td>
      <td className=""><div className="">Buy one get one discount</div></td>
      <td className=""><div className="">Tap Pay.</div></td>
      <td className=""><div className="">The reward discount should be correctly carried to the payment screen.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">24</div></td>
      <td className=""><div className="">Redemption</div></td>
      <td className=""><div className="">Buy one get one discount</div></td>
      <td className=""><div className="">Complete payment on the check.</div></td>
      <td className=""><div className="">The payment should process successfully.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">25</div></td>
      <td className=""><div className="">Accrual and Reversal</div></td>
      <td className=""><div className="">Without reward applied to check</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Look up a loyalty account that has associated rewards. <br/> Add items to the check. <br/> Tap Pay($).</div></td>
      <td className=""><div className="">The payment should process successfully. <br/> You should see the expected accrual message.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">26</div></td>
      <td className=""><div className="">Accrual and Reversal</div></td>
      <td className=""><div className="">Accrual reverse</div></td>
      <td className=""><div className="">On the Closed Checks tab, find the order placed in case 25. <br/> Tap Pay($). <br/> Void all payments. <br/> In the overflow menu, clock Void Order. <br/> Confirm the void operation.</div></td>
      <td className=""><div className="">The check should be successfully voided in Toast. <br/> You should see the expected reversal message.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">27</div></td>
      <td className=""><div className="">Accrual and Reversal</div></td>
      <td className=""><div className="">With reward applied to check</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Look up a loyalty account that has associated rewards. <br/> Add items that would trigger rewards to the check. <br/> Tap Rewards &gt; Look Up Customer. <br/> Tap Redeem to add a reward to the check. <br/> Tap Pay. <br/> Complete payment on the check.</div></td>
      <td className=""><div className="">The payment should process successfully. <br/> You should see the expected accrual and redeem messages.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">28</div></td>
      <td className=""><div className="">Accrual and Reversal</div></td>
      <td className=""><div className="">Redemption reverse</div></td>
      <td className=""><div className="">On the Closed Checks tab, find the order placed in case 27. <br/> Tap Pay($). <br/> Void all payments. <br/> In the overflow menu, click Void Order. <br/> Confirm the void operation.</div></td>
      <td className=""><div className="">The check should be successfully voided in Toast,. <br/> You should see the expected reversal messages.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">29</div></td>
      <td className=""><div className="">Accrual and Reversal</div></td>
      <td className=""><div className="">With multiple rewards applied to check</div></td>
      <td className=""><div className="">From the Toast POS app &gt; New Order. <br/> Tap Rewards &gt; Look Up Customer. <br/> Look up a loyalty account that has associated rewards. <br/> Add items that would trigger rewards to the check. <br/> Tap Rewards &gt; Look Up Customer. <br/> Tap Redeem to add a reward to the check. <br/> Repeat at least once in order to apply multiple rewards to the check. <br/> Tap Pay. <br/> Complete payment on the check.</div></td>
      <td className=""><div className="">The payment should process successfully. <br/> You should see the expected accrual and redeem messages.</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">30</div></td>
      <td className=""><div className="">Accrual and Reversal</div></td>
      <td className=""><div className="">Partial redemption reverse</div></td>
      <td className=""><div className="">On the Closed Checks tab, find the order placed in case 29. <br/> Tap Update. <br/> Select a reward that was redeemed, and void it from the check. <br/> Tap Pay. <br/> Complete payment on the check.</div></td>
      <td className=""><div className="">The check should successfully close. <br/> You should see the expected reversal messages.</div></td>
    </tr>
  </tbody>
</table>
</div>

