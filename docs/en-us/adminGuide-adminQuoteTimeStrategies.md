---
title: "Quote time strategies"
id: adminQuoteTimeStrategies
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminQuoteTimeStrategyOmitChunkFromSearchIndex.md
parentSectionTitle: "Quote time strategy"
previousSectionFile: adminGuide-adminQuoteTimeStrategyOverview.md
previousSectionTitle: "Quote time strategy overview"
nextSectionFile: adminGuide-adminQuoteTimeStrategySettings.md
nextSectionTitle: "Quote time strategy settings"
excerpt: "The following sections describe the various quote time strategies available."
keywords: ["quote", "time", "strategies"]
procedures: 0
codeExamples: 0
---

The following sections describe the various quote time strategies
    available.

## SmartQuote



> **Note**
> 
> To use SmartQuote, you must have a
        subscription to the Digital Storefront Suite and at least one Kitchen
        Display System (KDS).


The SmartQuote strategy automatically sets
      quote times based on your restaurant’s historical order data and other
      various data inputs. You can set minimum and maximum prep time values
      and SmartQuote provides a prep time estimate that
      falls within the values set.



> **Important**
> 
> The accuracy of SmartQuote predictions
        relies heavily on the quality and quantity of the data used for
        training the AI model. Insufficient or biased data could lead to
        inaccurate predictions. Please consider these limitations when
        interpreting results.


**Example 3.3. Example: Estimated immediate fulfillment time when SmartQuote
        quote time strategy is enabled**

In this example:

- Your restaurant is currently accepting Toast online
            orders.


- You set your minimum prep time for 10 minutes.


- You set your maximum prep time for 30 minutes.



A guest places an ASAP online order for takeout at 1:00 PM. The
        Toast-provided SmartQuote prep time is 20
        minutes. The guest’s order will be ready at 1:20 PM.

  
## Manual



> **Important**
> 
> If you do not have a subscription to the Digital Storefront
        Suite, you can only use the Manual quote time
        strategy.


The Manual strategy sets quote times based on
      the amount of time the kitchen needs to prepare the items in an order
      placed for takeout or delivery. The delivery quote time only applies to
      first-party delivery and not Toast Delivery Services (TDS) orders. The
      delivery quote time must be the same or more than the takeout
      time.

**Example 3.4. Example: Estimated immediate fulfillment time when Manual quote
        time strategy is enabled**

In this example:

- Your restaurant is currently accepting Toast online
            orders.


- Takeout time = 15 minutes.


- Delivery time = 25 minutes.



A guest places an ASAP Toast online order for takeout at 1:00
        PM. The configured Manual quote time is 15
        minutes. The guest’s order will be ready at 1:15 PM.

A guest places an ASAP Toast online order for delivery at 1:00
        PM. The configured Manual quote time is 25
        minutes. The guest’s order will be ready and delivered by 1:25
        PM.

  
## Kitchen capacity

The Kitchen capacity strategy sets quote
      times based on the number of orders or items the kitchen can prepare in
      a 15-minute time interval. First, set a quote time, which serves as the
      base time for the Kitchen capacity strategy. Then
      set your kitchen capacity by either the number of orders or by the
      number of items that your kitchen can prepare in a 15-minute interval.
      If you use the Kitchen capacity strategy it applies
      to both takeout and delivery orders.

When the Kitchen capacity strategy is
      enabled, it affects Toast Online Ordering in the following ways:
      

- The estimated fulfillment time for orders placed for
            immediate fulfillment increases when the kitchen capacity is
            reached for the next available 15-minute interval.


- When the kitchen capacity is reached for any 15-minute
            interval, that time is removed from the list of available
            fulfillment times that guests can choose when scheduling future
            orders.


- The estimated fulfillment time for orders placed for
            immediate fulfillment increases when the kitchen capacity or an
            order pricing condition is met.


- Order items are either prepared in the single time slot (if
            the slot can contain all the order items) or in sequential time
            slots.



**Example 3.5. Example: Estimated immediate fulfillment time increases when
          kitchen capacity is reached**

In this example:

- Your restaurant is currently accepting Toast online orders
              for immediate fulfillment.


- Quote time = 15 minutes.


- You have specified a capacity of three orders per 15
              minutes.



Three guests place online orders at 1:00 PM. Due to the
          configured prep time of 15 minutes, they see an estimated
          fulfillment time of 15-20 minutes. When these three orders are
          placed, the capacity for the 15-minute time interval is met. When a
          fourth guest places an order for immediate availability, the
          estimated fulfillment time increases.

  


**Example 3.6. Example: Time slot removed from list of available times when
          kitchen capacity is reached**

In this example:

- Your restaurant allows guests to schedule Toast online
              orders for future fulfillment.


- Quote time = 15 minutes.


- You have specified a capacity of three orders per 15
              minutes.



Three guests place online orders for future fulfillment and
          choose the same available fulfillment time of 3:00 PM on a specific
          business day. When these three orders are placed, the capacity for
          that 15-minute time interval is met. When a fourth guest schedules
          an order on the same business day, the 3:00 PM time slot no longer
          appears on the list of available fulfillment times. Only time slots
          for where order capacity hasn't already been met are
          displayed.

  


You can use the Kitchen capacity quote time
      strategy with an [Order price rule](adminGuide-adminQuoteTimeStrategies#adminOrderPriceStrategy).

**Example 3.7. Example: Estimated immediate fulfillment time increases when
        kitchen capacity is reached or the order pricing condition is
        met**

In this example:

- Your restaurant allows guests to place online orders for
            immediate fulfillment.


- Quote time = 15 minutes.


- You have specified a capacity of three orders per 15
            minutes.


- You have specified an order price rule to add 20 minutes for
            orders over $20.00.



Three guests each place a $40.00 Toast online order. The quote
        time for each order is adjusted and increases from 15 to 35 minutes
        due to the order price rule. When these three orders are placed, the
        capacity for the 15-minute time interval is met and exceeded.

  
**Example 3.8. Example: Estimated quote time for an immediate order when the
        kitchen capacity item throttling setting is reached**

In this example:

- Your restaurant is currently accepting Toast online orders
            for immediate fulfillment.


- Quote time = 15 minutes.


- You have specified a capacity of five items per 15
            minutes.

It is 4:00 PM and you have the following time slots filled
            with orders:

- 4:15 - 4:30 PM with a three item order.


- 4:45 - 5:00 PM with a two item order.


- 5:45 - 6:00 PM with a five item order.




- A guest places a 15 item order.



In this example, there are three sequential time slots available
        starting at 5:00 - 5:15 PM, 5:15 - 5:30 PM, and 5:30 - 5:45 PM. The
        Toast platform prioritizes sequential time slots if available. The
        order is completed by filling in the available time slots:

- 5:00 - 5:15 PM with five items.


- 5:15 - 5:30 PM with five items.


- 5:30 - 5:45 PM with five items.



The guest’s quote time for their 15 item order is 5:45
        PM.

  
## Order price

The Order price strategy sets quote times
      based on the total order price. This strategy applies to both takeout
      and delivery orders.

When the Order price strategy is enabled, the
      estimated fulfillment time for orders placed for immediate fulfillment
      increases if the pricing condition is met.

**Example 3.9. Example: Estimated fulfillment time increases when the order
          pricing condition is met**

In this example:

- Your restaurant allows guests to place Toast online orders
              for immediate fulfillment.


- Prep time = 15 minutes.


- You have specified an order price rule to add 20 minutes
              for orders over $20.00.



A guest places a $40.00 Toast online order for immediate
          fulfillment. The quote time is adjusted and increases from 15 to 35
          minutes due to the total order price.

  


