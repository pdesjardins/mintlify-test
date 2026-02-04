---
title: "Completing shift review offline"
id: adminCompletingShiftReviewOffline
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformPaymentsOfflineModeOmitChunkFromSearchIndex.md
parentSectionTitle: "Offline support"
previousSectionFile: adminGuide-adminOfflineCCPayments.md
previousSectionTitle: "Offline card payments"
nextSectionFile: adminGuide-adminPendingTipsWhenOffline.md
nextSectionTitle: "Pending tips when offline"
excerpt: "If your Toast POS device is offline, you will be unable to complete shift review. During offline mode, you are unable to:"
keywords: ["completing", "shift", "review", "offline"]
procedures: 0
codeExamples: 0
---

If your Toast POS device is offline, you will be unable to complete shift review. During offline mode, you are unable to:

- Close checks


- Declare cash tips


- Reconcile cash and tips


- Clock out



## Starting your shift when offline

If you are offline at the start of your shift, you will be unable to log in to a Toast POS device, however you can clock in and start your shift by using the normal procedure of signing in with a passcode and then clocking in on the Clock In/Out screen.

After clocking in, employees should follow these best practices:

- Each employee should use the same Toast POS device to take orders during their shift. More than one employee can work on a single device, but it is important that each employee use the same device while in offline mode.


- Do not restart the device. During offline mode, data will continue to be stored in the device until the connection is resumed. Note that the data will survive a power failure.


- Do not clock in on separate devices. When an employee clocks in, a time entry record for the employee is created locally on the device that cannot be synced with the cloud during offline mode. When the devices come back online, the time entry is synced with the cloud and is available in Toast Web. If multiple devices are used to clock in, each device will have a separate time entry stored locally that may cause a conflict when the devices come back online and sync with the cloud.



## Ending your shift when offline

If you are offline at the end of your shift, your shift review workflow is dependent on if shift review is required or optional.

- If shift review is required: Shift review cannot be completed offline and you should not attempt to clock out. Inform your manager of your clock out time and follow the steps below to complete your shift review while offline.


- If shift review is optional: Shift review cannot be completed offline but you can clock out on your local device. It is important to clock out using the same device you clocked in with.



Follow the steps below to complete shift review offline as an employee or manager.

**Procedure 6.128. To complete shift review offline as an employee**

1. Submit any cash in hand to your manager.


2. Work with your manager to determine how tips are paid out while devices are offline.


3. Inform your manager of your clock out time.



**Procedure 6.129. To complete shift review offline as a manager**

1. Collect all cash in hand payments from employees.


2. Keep merchant copies of receipts signed by guests as records for payments taken offline.


3. Tipping out becomes seamless once your device is back online; if tipping while offline, keep a written record of what is tipped out.


4. Note employee clock out times.



When the restaurant is back online, the manager can use the Time Entries report to [adjust the time entry](adminOfflineEmployees.html#adminOfflineTimeEntries) for the employee.



> **Note**
> 
> Depending on the setting of the [Auto Clock-out](adminOfflineEmployees.html#adminOfflineAutoClock) restaurant option, clocked-in employees may be automatically clocked out at the end of the business day.


