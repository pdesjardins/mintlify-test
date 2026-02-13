---
title: "Transaction types"
id: apiLoyaltyTransactionDescriptions
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiBuildingALoyaltyIntegrationOmitChunkFromSearchIndex.md
parentSectionTitle: "Loyalty program integrations"
previousSectionFile: apiDevGuide-apiLoyaltyIntegrationOverview.md
previousSectionTitle: "Loyalty integration implementation"
nextSectionFile: apiDevGuide-apiLoyaltyPosWorkflow.md
nextSectionTitle: "POS workflow"
externalReferences: [https://central.toasttab.com/s/article/Reprint-and-Resend-Receipt-from-Payment-Terminal, https://doc.toasttab.com/openapi/loyalty/tag/Data-definitions/schema/ResponseCheck/, https://central.toasttab.com/s/article/Voiding-Items-Payments-and-Checks]
excerpt: "This section provides information about the way the Toast loyalty integration API transactions correspond to Toast platform transactions."
keywords: ["transaction", "types", "LOYALTY_SEARCH", "LOYALTY_INQUIRE", "LOYALTY_REDEEM", "LOYALTY_ACCRUE", "LOYALTY_REVERSE"]
procedures: 0
codeExamples: 0
---

This section provides information about the way the Toast loyalty
    integration API transactions correspond to Toast platform
    transactions.

The Toast platform sends requests to your integration API when
    restaurant employees perform loyalty program transactions at a restaurant.
    You can identify the transaction type for each request using the
    *`Toast-Transaction-Type`* HTTP header parameter. The
    information that you receive in the request body depends on the
    transaction type. Your integration service must return response data
    synchronously. Your response includes information such as the offers
    available to a loyalty program member and error codes that are defined by
    the integration API specification.

The loyalty integration API supports the following transaction
    types:

- `LOYALTY_SEARCH`: Retrieve a list of loyalty accounts
        that match search criteria.


- `LOYALTY_INQUIRE`: Retrieve list of available offers
        for a loyalty member, as well as verify offers that have been applied
        to the check.


- `LOYALTY_REDEEM`: Redeem the offers applied to a
        check.


- `LOYALTY_ACCRUE`: Describe the member's purchases to
        earn credit for future rewards.


- `LOYALTY_REVERSE`: Reverse a previous
        `LOYALTY_REDEEM` or `LOYALTY_ACCRUE`
        transaction.



The following sections provide information about Toast loyalty
    integration transaction types.

## LOYALTY_SEARCH

The search workflow occurs when a restaurant employee selects the
      Rewards button in the Toast POS app and the
      restaurant guest has not already provided an identifying card or other
      form of loyalty program account identification.

**Procedure 10.5. Search workflow**

1. The restaurant employee selects the
          Rewards button in the Toast POS app and enters
          identifying information (name, email address, or phone number) about
          a restaurant guest.


2. The POS sends a search request to your loyalty program
          integration. The request body includes a
          `TransactionInformationSearch` object holding identifying
          information about the restaurant guest.


3. Your loyalty program integration responds to the search
          request. The request body includes a `ResponseSearch`
          object holding list of loyalty accounts that match the search
          criteria. The HTTP header for the response includes a 200 HTTP
          response code if there is at least one account found or a 404 HTTP
          response code if there are no accounts found.


4. The restaurant employee selects the correct account or cancels
          the workflow.



**Example 10.5. Loyalty account search request**

```
{
  "toastTransactionType":"LOYALTY_SEARCH",
  "searchTransactionInformation":{
    "searchCriteria":{
      "firstName":"James",
      "lastName":"Smith",
      "email":null,
      "phone":null
    }
  },
  "checkTransactionInformation":null,
  "reverseTransactionInformation":null
}
```

  
**Example 10.6. Successful loyalty account search response (200 HTTP
        code)**

```
{
  "searchResponse":{
    "accounts":[
      {
        "identifier":"1",
        "firstName":"james",
        "lastName":"smith",
        "phone":"1111111111",
        "email":"a1@toasttab.com",
        "pointsBalance":40
      }
    ]
  },
  "transactionStatus":"ACCEPT"
}
```

  


 You may return a pointsBalance in your response
          to a LOYALTY_SEARCH request, but this balance will not
          display on the POS. The points balance only displays on the POS in
          response to LOYALTY_INQUIRE requests.

**Example 10.7. Loyalty account search response with no accounts found (404
        HTTP code)**

```
{
  "transactionStatus":"ERROR_ACCOUNT_INVALID"
}
```

  
## LOYALTY_INQUIRE

The inquire workflow occurs when a restaurant employee selects the
      Rewards button in the Toast POS app if a restaurant
      guest's loyalty account has already been found. The Toast platform might
      send multiple inquire transactions while handling a single purchase
      interaction for a restaurant guest.

**Procedure 10.6. Inquire workflow**

1. The restaurant employee selects a guest's loyalty account from
          search results or scans, swipes, or keys in the loyalty account
          identifier in the Toast POS app.


2. The POS sends an inquire request to your loyalty program
          integration. The request body includes a
          `TransactionInformationCheck` object holding the
          following information:

- The loyalty program account information that identifies
              the guest.


- The restaurant check for the guest. The check might
              include menu item selections or have no selections. The check
              might include loyalty program offers that have already been
              applied (redemptions).




3. Your loyalty program integration responds to the inquire
          request. The request body includes a `ResponseCheck`
          object holding the following information:

- A list of available offers. You determine which offers to
              include in the list. If an item-level offer is available, you
              must specify the item GUID so the POS knows which item it
              applies to.

Each offer contains a boolean value indicating whether the
              offer is applicable based on the current check contents. If the
              offer is not applicable, the POS will display the offer with
              formatting to indicate that it is not available (for example,
              light gray text) and without a Redeem
              button.


- A list of offers that are currently applied to the check
              that *are not valid*. The POS will remove
              those offers from the check.


- A list of offers that are currently applied to the check
              (redemptions) that *are valid*.


- A `ResponseCheck` object must include an
              `accountInfo` value.


- If you include a numeric `pointsBalance` on
              your `ResponseCheck` object, the points balance will
              display on the POS.




4. The restaurant employee might make changes to the check. For
          example:

- Apply and remove loyalty program offers based on the
              offers that the guest chooses. Each time the employee selects
              the Rewards button, the Toast platform
              sends an inquire request.


- Add and remove items from the check.


- Apply and remove discounts that are not associated with
              the loyalty program to and from the check.




5. The restaurant employee finishes entering the guest's order
          and enters the payment screen of the POS.


6. The POS sends another inquire request. This request repeats
          step [Step 2](apiDevGuide-apiLoyaltyTransactionDescriptions.html#apiLoyaltyInquireStepInquire).


7. Your loyalty program integration responds to the inquire
          request. This response repeats step [Step 3](apiDevGuide-apiLoyaltyTransactionDescriptions.html#apiLoyaltyInquireStepRespond).


8. The POS processes the payment and completes the guest
          transaction.



When discounts display on the POS, all applicable discounts
      display first, followed by all discounts that are not applicable. Within
      each type of discount (applicable and non-applicable), discounts are
      ordered by name alphabetically.

In all scenarios, response contains a list of accepted and
      rejected redemptions, if any.

- If ACCEPTED, redemption is added to check as a
          discount.


- If REJECTED, redemption is removed from the check with an
          error message.

This is still possible if the check changes. For example, add
          two pizzas to the order and apply a BOGO discount, buy two pizzas
          and get a pizza for free. Then remove one of the pizzas. The next
          inquire will indicate that the offer which was previously applied is
          rejected because the check does not have the items that are needed
          to qualify for the offer.





> **Note**
> 
> The Toast platform changes the `tabName` of the check
        with the `firstName` and `lastName` from the
        `accountInfo` object that is in the loyalty program
        integration response to the inquire request.


**Example 10.8. Loyalty inquire request**

```
{
  "toastTransactionType":"LOYALTY_INQUIRE",
  "searchTransactionInformation":null,
  "checkTransactionInformation":{
    "loyaltyIdentifier":"1",
    "check":{
      "guid":"5728df00-d770-4aeb-a4c9-53226a104ac0",
      "entityType":null,
      "externalId":null,
      "displayNumber":"3001",
      "payments":[],
      "appliedDiscounts":[],
      "lastModifiedDevice":null,
      "voidDate":null,
      "paidDate":null,
      "appliedLoyaltyInfo":null,
      "voided":false,
      "paymentStatus":"OPEN",
      "amount":97.42,
      "tabName":null,
      "taxExempt":false,
      "openedDate":"2019-08-24T14:15:22Z",
      "totalAmount":103.51,
      "selections":[
        {
          "guid":"5e4fa4aa-4269-4383-9bbd-774591bbfb3c",
          "entityType":null,
          "externalId":null,
          "deferred":false,
          "preDiscountPrice":87.92,
          "voidReason":null,
          "optionGroup":null,
          "displayName":"Crab Cakes",
          "appliedDiscounts":[],
          "modifiers":[],
          "voidDate":null,
          "fulfillmentStatus":"NEW",
          "salesCategory":null,
          "selectionType":null,
          "price":87.92,
          "voided":false,
          "appliedTaxes":[
            {
              "guid":null,
              "entityType":"AppliedTaxRate",
              "taxRate":{
                "guid":"78aca305-6fbc-42ea-a85b-1671c52367eb",
                "entityType":"TaxRate"
              },
              "rate":0.0625,
              "name":"MA Tax",
              "taxAmount":5.49612811,
              "type":"PERCENT"
            }
          ],
          "itemGroup":{
            "guid":"15694864-225d-4b47-a60b-b9c20986b0af",
            "entityType":"MenuGroup",
            "externalId":"100000000100004070"
          },
          "item":{
            "guid":"5abf524e-31b5-4c1b-a797-7a44d888d071",
            "entityType":"MenuItem",
            "externalId":"100000000100004071"
          },
          "taxInclusion":null,
          "quantity":8.0,
          "unitOfMeasure":null,
          "tax":5.49612811,
          "diningOption":null,
          "voidBusinessDate":null,
          "createdDate":null,
          "preModifier":null,
          "modifiedDate":null
        },
        {
          "guid":"c4c6cd98-d1ba-42f6-87c0-4d8af7486be7",
          "entityType":null,
          "externalId":null,
          "deferred":false,
          "preDiscountPrice":9.5,
          "voidReason":null,
          "optionGroup":null,
          "displayName":"BBQ Pulled Pork Sliders",
          "appliedDiscounts":[],
          "modifiers":[],
          "voidDate":null,
          "fulfillmentStatus":"NEW",
          "salesCategory":null,
          "selectionType":null,
          "price":9.5,
          "voided":false,
          "appliedTaxes":[
            {
              "guid":null,
              "entityType":"AppliedTaxRate",
              "taxRate":{
                "guid":"78aca305-6fbc-42ea-a85b-1671c52367eb",
                "entityType":"TaxRate"
              },
              "rate":0.0625,
              "name":"MA Tax",
              "taxAmount":0.59387189,
              "type":"PERCENT"
            }
          ],
          "itemGroup":{
            "guid":"15694864-225d-4b47-a60b-b9c20986b0af",
            "entityType":"MenuGroup",
            "externalId":"100000000100004070"
          },
          "item":{
            "guid":"a1a96ffc-fb39-422b-93bd-44f15692f707",
            "entityType":"MenuItem",
            "externalId":"100000000100004072"
          },
          "taxInclusion":null,
          "quantity":1.0,
          "unitOfMeasure":null,
          "tax":0.59387189,
          "diningOption":null,
          "voidBusinessDate":null,
          "createdDate":null,
          "preModifier":null,
          "modifiedDate":null
        }
      ],
      "voidBusinessDate":null,
      "deleted":false,
      "createdDevice":null,
      "closedDate":null,
      "deletedDate":null,
      "modifiedDate":null,
      "taxAmount":6.09,
      "appliedServiceCharges":[],
      "customer":null
    },
    "redemptions":[]
  },
  "reverseTransactionInformation":null
}
```

  
**Example 10.9. Successful loyalty inquire response**

```
{
  "checkResponse":{
    "accountInfo":{
      "identifier":"1",
      "firstName":"james",
      "lastName":"smith",
      "phone":"1111111111",
      "email":"a1@gmail.com"
    },
    "offers":[
      {
        "identifier":"4",
        "name":"reward 3",
        "applicable":false,
        "selectionType":"ITEM",
        "amount":"10",
        "quantity":2
      }
    ],
    "rejectedRedemptions":[],
    "appliedRedemptions":[],
    "userMessage":"Visit http://www.website.com to check your points balance."
  },
  "transactionStatus":"ACCEPT"
}
```

  
## LOYALTY_REDEEM

The redeem workflow occurs when the Toast platform processes a
      guest payment and completes a purchase transaction.

The redeem transaction follows the final inquire transaction
      during the payment process of the guest purchase transaction.

**Procedure 10.7. Redeem workflow**

1. The POS sends a redeem request. The request body includes a
          `TransactionInformationCheck` object holding the
          following information:

- The loyalty program account information that identifies
              the guest.


- The restaurant check for the guest. The check might
              include menu item selections or have no selections. The check
              might include loyalty program offers that have been
              applied.




2. Your loyalty program integration responds to the redeem
          request. The request body might include a `ResponseCheck`
          object holding the following information:

- A list of offers that are currently applied to the check
              that *are not valid*. The POS will remove
              those offers from the check.




3. The POS processes the payment and completes the guest
          transaction.





> **Note**
> 
> The Toast platform does not process rewards offer redemptions
        when a restaurant experiences an Internet outage or other network
        disruption. When a restaurant does not have a functioning network, it
        is in *offline mode*. For more information, see
        [Offline mode overview](adminGuide-adminOfflineModeOverview).


**Example 10.10. Loyalty redeem request**

```
{
  "toastTransactionType":"LOYALTY_REDEEM",
  "searchTransactionInformation":null,
  "checkTransactionInformation":{
    "loyaltyIdentifier":"3",
    "check":{
      "guid":"c79ecf26-1540-486c-9aee-e10ef34e228e",
      "entityType":null,
      "externalId":null,
      "displayNumber":"3002",
      "payments":[],
      "appliedDiscounts":[
        {
          "guid":"5318bf86-505a-43fe-91ad-feb6fe6e0ad2",
          "entityType":"AppliedLoyaltyProviderDiscount",
          "approver":{
            "guid":"915ae2ef-a59a-44dd-bea3-a23977cf5e26",
            "entityType":"RestaurantUser",
            "externalId":"100000000100005200"
          },
          "processingState":"PENDING_APPLIED",
          "loyaltyDetails":{
            "vendor":null,
            "referenceId":"1"
          },
          "name":"reward 1",
          "comboItems":[],
          "discountAmount":5,
          "discount":{
            "guid":"e7b9fc51-bb27-47c5-b3e8-c5c47600380e",
            "entityType":"CustomDiscount"
          },
          "nonTaxDiscountAmount":null,
          "triggers":[],
          "appliedPromoCode":null
        }
      ],
      "lastModifiedDevice":null,
      "voidDate":null,
      "paidDate":null,
      "appliedLoyaltyInfo":{
        "guid":null,
        "entityType":null,
        "accrualText":null,
        "accrualFamilyGuid":null,
        "vendor":null,
        "loyaltyIdentifier":"3"
      },
      "voided":false,
      "paymentStatus":"OPEN",
      "amount":38.96,
      "tabName":"jack williams",
      "taxExempt":false,
      "openedDate":"2019-08-24T14:15:22Z",
      "totalAmount":41.4,
      "selections":[
        {
          "guid":"dfa59529-c3d1-4dff-967d-12e19525f749",
          "entityType":null,
          "externalId":null,
          "deferred":false,
          "preDiscountPrice":43.96,
          "voidReason":null,
          "optionGroup":null,
          "displayName":"Crab Cakes",
          "appliedDiscounts":[],
          "modifiers":[],
          "voidDate":null,
          "fulfillmentStatus":"SENT",
          "salesCategory":null,
          "selectionType":null,
          "price":38.96,
          "voided":false,
          "appliedTaxes":[
            {
              "guid":null,
              "entityType":"AppliedTaxRate",
              "taxRate":{
                "guid":"78aca305-6fbc-42ea-a85b-1671c52367eb",
                "entityType":"TaxRate"
              },
              "rate":0.0625,
              "name":"MA Tax",
              "taxAmount":2.44,
              "type":"PERCENT"
            }
          ],
          "itemGroup":{
            "guid":"15694864-225d-4b47-a60b-b9c20986b0af",
            "entityType":"MenuGroup",
            "externalId":"100000000100004070"
          },
          "item":{
            "guid":"5abf524e-31b5-4c1b-a797-7a44d888d071",
            "entityType":"MenuItem",
            "externalId":"100000000100004071"
          },
          "taxInclusion":null,
          "quantity":4,
          "unitOfMeasure":null,
          "tax":2.44,
          "diningOption":null,
          "voidBusinessDate":null,
          "createdDate":null,
          "preModifier":null,
          "modifiedDate":null
        }
      ],
      "voidBusinessDate":null,
      "deleted":false,
      "createdDevice":null,
      "closedDate":null,
      "deletedDate":null,
      "modifiedDate":null,
      "taxAmount":2.44,
      "appliedServiceCharges":[],
      "customer":null
    },
    "redemptions":[
      {
        "identifier":"1",
        "itemId":null,
        "selectionGuid":null,
        "amount":5,
        "quantity":2
      }
    ]
  },
  "reverseTransactionInformation":null
}
```

  
**Example 10.11. Successful loyalty redeem response**

```
{
  "checkResponse":{
    "accountInfo":{
      "identifier":"3",
      "firstName":"jack",
      "lastName":"williams",
      "phone":"1111111113",
      "email":"a3@gmail.com"
    },
    "offers":[
      {
        "identifier":"1",
        "name":"reward 1",
        "applicable":true,
        "selectionType":"CHECK",
        "amount":"5",
        "quantity":4
      },
      {
        "identifier":"3",
        "name":"reward 3",
        "applicable":false,
        "selectionType":"ITEM",
        "amount":"10",
        "itemApplication":[
          {
            "selectionIdentifier":"undefined",
            "amount":"10"
          }
        ],
        "quantity":10
      }
    ],
    "rejectedRedemptions":[],
    "appliedRedemptions":[
      {
        "identifier":"1",
        "itemId":null,
        "selectionGuid":null,
        "amount":5,
        "quantity":2
      }
    ],
    "userMessage":"Visit http://www.website.com to check your points balance"
  },
  "transactionStatus":"ACCEPT"
}
```



(1) The rejectedRedemptions array is empty because
            your loyalty program service determined that all of the redeemed
            reward offers in the redeem request are valid. If your loyalty
            program service determines that a redeemed reward is not valid,
            you must include a RejectedRedemption object in this
            array. For more information, see Handling redeemed offers that are not valid.

(2) The appliedRedemptions array includes a
            Redemption object for each rewards offer that your
            loyalty program service determines is valid for the loyalty
            account and the current guest check.

 In this example, since the quantity of the
            applied redemption is 2 and the amount is 5, the
            total amount discounted will be 10.

(4) Set the transactionStatus to
            ACCEPT to indicate that your service has successfully
            processed the request. The status is ACCEPT even when
            you determine that some redeemed rewards offers are not
            valid.

  
### Handling redeemed offers that are not valid

Each time a restaurant guest chooses to redeem a reward offer,
        the Toast platform sends a redeem request. If you determine that the
        reward offer is no longer valid:

- Include `ACCEPT` in the
            `transactionStatus` value of the
            `LoyaltyTransactionResponse` object you return to the
            Toast platform.


- Include a `RejectedRedemption` object for each
            reward offer that is no longer valid in the
            `rejectedRedemptions` value of the
            `LoyaltyTransactionResponse` object. Each
            `RejectedRedemption` object is required to include a
            `Redemption` object with the
            `appliedDiscountGuid` value to identify the rejected
            reward.


- The Toast platform updates the check. If the guest chooses
            to redeem another reward offer, the POS sends another redeem
            request.



## LOYALTY_ACCRUE



> **Note**
> 
> The Toast platform does not send accrue requests when a
        restaurant experiences an internet outage or other network disruption.
        A Toast POS device stores payments and sends accrue requests for them
        when the device is connected to the network again. When a restaurant
        does not have a functioning network, it is in *offline
        mode*. For more information, see [Offline mode overview](adminGuide-adminOfflineModeOverview).


The accrue workflow occurs as an asynchronous process after a
      guest pays for a check. The Toast platform sends a
      `LOYALTY_ACCRUE` request regardless of the presence of a
      `loyaltyIdentifier`.

**Procedure 10.8. Accrue workflow**

1. The POS sends an accrue request. The request body includes a
          `TransactionInformationCheck` object holding the
          following information:

- The loyalty program account information that identifies
              the guest.


- The restaurant check for the guest. The check might
              include menu item selections or have no selections. The check
              might include loyalty program offers that have been
              applied.




2. Your loyalty program integration responds to the accrue
          request. The request body might include a `ResponseCheck`
          object holding the following information:

- A list of offers that are currently applied to the check
              that *are not valid*. The POS will remove
              those offers from the check.





**Example 10.12. Loyalty accrue request**

```
{
  "toastTransactionType":"LOYALTY_ACCRUE",
  "searchTransactionInformation":null,
  "checkTransactionInformation":{
    "loyaltyIdentifier":null,
    "check":{
      "guid":"5728df00-d770-4aeb-a4c9-53226a104ac0",
      "entityType":"Check",
      "externalId":null,
      "displayNumber":"183",
      "payments":[
        {
          "guid":"8b251345-3cda-486e-91c9-cd760c6087c6",
          "entityType":"OrderPayment",
          "externalId":null,
          "originalProcessingFee":null,
          "amount":8.69,
          "tipAmount":0,
          "amountTendered":9,
          "cashDrawer":{
            "guid":"404a8efc-3eda-471a-a11d-f69358d54084",
            "entityType":"CashDrawer",
            "externalId":null
          },
          "cardType":null,
          "lastModifiedDevice":{
            "id":"f51c0a6ce7da722c"
          },
          "refundStatus":"NONE",
          "houseAccount":null,
          "type":"CASH",
          "voidInfo":null,
          "otherPayment":null,
          "mcaRepaymentAmount":null,
          "createdDevice":{
            "id":"f51c0a6ce7da722c"
          },
          "paidDate":"2019-04-08T21:16:46.738+0000",
          "cardEntryMode":null,
          "paymentStatus":"CAPTURED",
          "paidBusinessDate":20190408,
          "last4Digits":null,
          "refund":null
        }
      ],
      "appliedDiscounts":[],
      "lastModifiedDevice":{
        "id":"f51c0a6ce7da722c"
      },
      "voidDate":null,
      "paidDate":"2019-04-08T21:16:46.767+0000",
      "appliedLoyaltyInfo":null,
      "voided":false,
      "paymentStatus":"CLOSED",
      "amount":8,
      "tabName":"A",
      "taxExempt":false,
      "openedDate":"2019-08-24T14:15:22Z",
      "totalAmount":8.69,
      "selections":[
        {
          "guid":"c3283098-44c1-4712-866a-2b53cdc39b25",
          "entityType":"MenuItemSelection",
          "externalId":null,
          "deferred":false,
          "preDiscountPrice":8,
          "voidReason":null,
          "optionGroup":null,
          "displayName":"Hop Particle Double Ipa",
          "appliedDiscounts":[],
          "modifiers":[],
          "voidDate":null,
          "fulfillmentStatus":"SENT",
          "salesCategory":{
            "guid":"c6909137-0deb-4197-9003-3092294fe1a3",
            "entityType":"SalesCategory",
            "externalId":null
          },
          "selectionType":"NONE",
          "price":8,
          "voided":false,
          "appliedTaxes":[
            {
              "guid":"92894bfa-e56c-4638-9fa9-88e4d24190a3",
              "entityType":"AppliedTaxRate",
              "taxRate":{
                "guid":"9164a65c-5f25-4cb9-8fb9-b55cace11445",
                "entityType":"TaxRate"
              },
              "rate":0.086,
              "name":"State Tax",
              "taxAmount":0.69,
              "type":"PERCENT"
            }
          ],
          "itemGroup":{
            "guid":"e8cee39c-7ff2-4ef1-9de9-e4ab0ee777f0",
            "entityType":"MenuGroup",
            "externalId":null
          },
          "item":{
            "guid":"859d3db8-9dd4-42ab-9f6a-374d09e27825",
            "entityType":"MenuItem",
            "externalId":null
          },
          "taxInclusion":"NOT_INCLUDED",
          "quantity":1,
          "unitOfMeasure":"NONE",
          "tax":0.69,
          "diningOption":{
            "guid":"29481dc5-7a77-4b57-81ba-75710c5b39c8",
            "entityType":"DiningOption",
            "externalId":null
          },
          "voidBusinessDate":null,
          "createdDate":"2019-04-08T21:16:46.345+0000",
          "preModifier":null,
          "modifiedDate":"2019-04-08T21:16:46.361+0000"
        }
      ],
      "voidBusinessDate":null,
      "deleted":false,
      "createdDevice":{
        "id":"f51c0a6ce7da722c"
      },
      "closedDate":"2019-04-08T21:16:46.767+0000",
      "deletedDate":"1970-01-01T00:00:00.000+0000",
      "modifiedDate":"2019-04-08T21:16:48.028+0000",
      "taxAmount":0.69,
      "appliedServiceCharges":[],
      "customer":null
    },
    "redemptions":[]
  },
  "reverseTransactionInformation":null
}
```

  
**Example 10.13. Successful loyalty accrue response**

```
{
  "transactionStatus":"ACCEPT"
}
```

  
### Enabling loyalty messages and QR codes on guest
        receipts

If your loyalty program integration allows guests to earn points
        by scanning a QR code on their receipt, the Toast platform will print
        the QR code if both of the following conditions are met:

- No loyalty account is associated with the check


- The check is in the `CLOSED` state



If both conditions are met, Toast prints the guest receipt with
        a QR code. When your guest scans the QR code, a pop-up banner appears
        with the `LOCATION_GUID:ORDER_GUID:CHECK_GUID`. This
        information is used to look up the guest’s order and apply points to
        their loyalty account in your integration.



> **Note**
> 
> If a guest receipt needs to be reprinted after the check has
          been closed and the QR code has been printed, the receipt must be
          reprinted from the Payment Terminal screen on
          the Toast POS device. For more information, see [Reprint
          and Resend Receipts](https://central.toasttab.com/s/article/Reprint-and-Resend-Receipt-from-Payment-Terminal).


Additionally, you can choose to print an optional customizable
        message on your guest’s receipt by populating the
        `userMessage` field in a `LOYALTY_ACCRUE`
        transaction. For more information, see [Loyalty
        integration specification](https://doc.toasttab.com/openapi/loyalty/tag/Data-definitions/schema/ResponseCheck/).

## LOYALTY_REVERSE

The reverse workflow occurs when a restaurant employee voids
      (undoes) a guest's check or voids items that were affected by a loyalty
      program offer.

**Procedure 10.9. Reverse workflow**

1. The POS sends a reverse request. The request body includes a
          `TransactionInformationReverse` object holding the
          following information:

- The loyalty program account information that identifies
              the guest.


- The identifier of the previous loyalty program transaction
              that needs to be reversed. The identifier of a transaction is in
              the `Toast-Transaction-GUID` header parameter of the
              transaction request.




2. Your loyalty program integration responds to the response
          request. The request body indicates the success or failure of the
          reverse transaction.



**Example 10.14. Loyalty reverse request**

```
{
  "toastTransactionType":"LOYALTY_REVERSE",
  "searchTransactionInformation":null,
  "checkTransactionInformation":null,
  "reverseTransactionInformation":{
    "loyaltyIdentifier":"1",
    "transactionId":"ab11d469-5ed5-4daa-b9d6-addefdb1c1f7",
    "redemptions":[
      {
        "identifier":"5",
        "appliedDiscountGuid":"64456691-c34e-4784-9c6e-fc514a0f4b7b",
        "selectionGuid":null,
        "amount":0.01,
        "quantity":1
      },
      {
        "identifier":"5",
        "appliedDiscountGuid":"64456691-c34e-4784-9c6e-fc514a0f4b7b",
        "selectionGuid":null,
        "amount":0.01,
        "quantity":1
      }
    ]
  }
}
```

  
**Example 10.15. Successful loyalty reverse**

```
{
  "transactionStatus":"ACCEPT"
}
```

  
### Triggering a reverse transaction

You can only reverse redeem and accrue transactions. You reverse
        redeem and accrue transactions you void menu item selections,
        payments, and checks. For information about voiding items, payments,
        and checks in the Toast POS app, see this [Toast
        central article](https://central.toasttab.com/s/article/Voiding-Items-Payments-and-Checks).

The redeem transaction occurs during the payment process. You
        can reverse a redeem transaction after payment by voiding the entire
        check or voiding a menu item selection that is related to the redeem
        transaction.

The accrue transaction occurs asynchronously after you complete
        the payment process. You can reverse an accrue transaction by voiding
        the entire check or by making a change to the payment.

**Example of changing payment**

1. You process a credit card payment.


2. The check is still open.


3. The guest leaves a tip. The guest modifies the payment by
            adding a tip to the total.


4. Although there may not be a change in the accrual amount,
            modifying the payment triggers a reverse transaction for the
            accrue transaction for the payment and it triggers a new accrue
            transaction for the updated payment.



