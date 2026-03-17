---
title: "Time entries and breaks"
id: platformShiftsTimeEntriesAndBreaks
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformShiftsOverviewOmitChunkFromSearchIndex.md
parentSectionTitle: "Shifts"
previousSectionFile: adminGuide-platformScheduledShifts.md
previousSectionTitle: "Scheduled shifts for schedule enforcement"
nextSectionFile: adminGuide-platformShiftsBusinessRules.md
nextSectionTitle: "Shifts and time entries business rules"
externalReferences: [https://central.toasttab.com/s/article/Building-Breaks-in-Toast?language=en_US]
excerpt: "A time entry is a record of when an employee actually worked for a given shift. A time entry includes a clock-in timestamp and a clock-out timestamp. A time entry is always associated with a..."
keywords: ["time", "entries", "breaks"]
procedures: 0
codeExamples: 0
---

A *time entry* is a record of when an employee actually worked for a given shift. A time entry includes a clock-in timestamp and a clock-out timestamp. A time entry is always associated with a completed shift, and typically there is one time entry per shift.

Some Toast Web pages and reports use the term *time card* instead of time entry. A time entry and a time card are the same record of an employee's work.

Breaks are periods during the shift when the employee is not working. Employees record breaks based on their eligibility and the configuration of a location. Breaks are stored as part of a shift record.

Breaks must occur within the clock-in to clock-out period for a time entry and cannot overlap each other.

You configure break types, missed break tracking, and break acknowledgement for your locations in Toast Web. For more information, see [this Toast Central article](https://central.toasttab.com/s/article/Building-Breaks-in-Toast?language=en_US).

