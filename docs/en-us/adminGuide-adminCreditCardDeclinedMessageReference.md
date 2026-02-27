---
title: "Card declined message reference"
id: adminCreditCardDeclinedMessageReference
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminCreditCardsOmitChunkFromSearchIndex.md
parentSectionTitle: "Credit card payments"
previousSectionFile: adminGuide-adminCreditCardPayments.md
previousSectionTitle: "Credit card payments"
nextSectionFile: adminGuide-adminServiceChargesOmitChunkFromSearchIndex.md
nextSectionTitle: "Service charges"
excerpt: "When a card payment cannot be processed, the Toast POS device shows a..."
procedures: 0
codeExamples: 0
---

When a card payment cannot be processed, the Toast POS device shows a message from the card network. These response messages can be difficult to interpret. The following table shows the response messages received most frequently on Toast POS devices with descriptions for why that message might appear.



> **Note**
> 
> The messages and the descriptions shown in the following tables are produced by the card processor, not by Toast. The information provided in these tables is intended for reference only, and is subject to change without notice by the card network.



<div className="table-wrapper">
<table className="">
  <thead className="">
    <tr className="">
      <th className=""><div className="">Response Message</div></th>
      <th className=""><div className="">Descriptions</div></th>
    </tr>
  </thead>
  <tbody className="">
    <tr className="">
      <td className=""><div className="">*REQUEST DENIED*</div></td>
      <td className=""><div className="">Do not honor</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">AUTH DECLINED</div></td>
      <td className=""><div className="">Do not honor <br/> Transaction not permitted to issuer/cardholder <br/> Exceeds withdrawal limit <br/> Domain Restriction Controls Fail <br/> Declined-transaction in violation of law <br/> Declined PIN attempts</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">AUTH TRN NO AL'W</div></td>
      <td className=""><div className="">Auth transaction not allowed for this payment</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">CALL OPER</div></td>
      <td className=""><div className="">Refer to card issuer <br/> Refer to call center</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">CALL VOICE OPER</div></td>
      <td className=""><div className="">Refer to card issuer <br/> Re-enter transaction</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">CARD EXPIRED</div></td>
      <td className=""><div className="">Expiration date check failed <br/> Expired card <br/> Card expiry date less than current date</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">CARDHLDR DECLINE</div></td>
      <td className=""><div className="">Declined per cardholder request</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">CVD ERROR</div></td>
      <td className=""><div className="">Do not honor</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">DECLINED</div></td>
      <td className=""><div className="">Declined by user <br/> Invalid effective date on card</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">ERR PROC FIELD</div></td>
      <td className=""><div className="">Format error, invalid value in message</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">HOLD - CALL</div></td>
      <td className=""><div className="">Pick up</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">INV CARD NUMBER</div></td>
      <td className=""><div className="">Invalid cardholder account <br/> Account number not found in BIN table</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">INVALID AMOUNT</div></td>
      <td className=""><div className="">Invalid amount</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">INVALID CARD</div></td>
      <td className=""><div className="">Invalid card number</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">INVALID CARD NO</div></td>
      <td className=""><div className="">Invalid card number</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">INVALID EXP DATE</div></td>
      <td className=""><div className="">Invalid expiry date</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">INVALID FUNCTION </div></td>
      <td className=""><div className="">Transaction not permitted to terminal </div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">INVALID MERC NO </div></td>
      <td className=""><div className="">Invalid merchant or terminal </div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">INVALID PIN </div></td>
      <td className=""><div className="">Invalid pin </div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">LOST/STOLEN CARD</div></td>
      <td className=""><div className="">Lost or stolen card</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">NO CHECKING ACCT</div></td>
      <td className=""><div className="">Error</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">PICK UP CARD </div></td>
      <td className=""><div className="">Pick up card  <br/> Decline - pick up card <br/> Pick up card - No Fraud <br/> Pick up card (Special Condition) <br/> Pick up card (Special Condition)(Fraud Account) <br/> Lost card - pick up <br/> Stolen card - pick up</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">PIN TRIES EXCEED</div></td>
      <td className=""><div className="">Re-enter transaction</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">PROC ERROR 13</div></td>
      <td className=""><div className="">System error</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">SECURITY VIOLATION</div></td>
      <td className=""><div className="">Security violation</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">TRAN NOT ALLOWED</div></td>
      <td className=""><div className="">Transaction not permitted to terminal</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">TRANS DENIED</div></td>
      <td className=""><div className="">Do not honor <br/> Invalid cardholder account <br/> Unable to locate record <br/> Insufficient funds <br/> Restricted card <br/> Security violation <br/> Account activity limit exceeded <br/> Allowable number of PIN entry tries exceeded <br/> One or more errors in message <br/> File is unavailable <br/> No credit account <br/> Fraudulent activity detected</div></td>
    </tr>
    <tr className="">
      <td className=""><div className="">TRANS NOT ALLOW</div></td>
      <td className=""><div className="">Transactions not allowed to cardholder <br/> Transactions not allowed to terminal <br/> Illegal transaction - violation of law <br/> Capture transactions not allowed for this payment type <br/> Capture transaction on authorization only terminal <br/> Private label transaction not allowed for terminal <br/> Store reporting transactions not allowed</div></td>
    </tr>
  </tbody>
</table>
</div>

