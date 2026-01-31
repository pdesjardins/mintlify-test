---
title: "Understanding modifier group display order"
id: adminUnderstandingModifierGroupDisplay
type: section
documentId: adminGuide
parentSectionFile: adminGuide-adminModifierGroupDisplayOrderOmitChunkFromSearchIndex.md
parentSectionTitle: "Modifier group display order"
previousSectionFile: adminGuide-adminSettingsAndConditionsThatAffectModifierGroupDisplay.md
previousSectionTitle: "Settings and conditions that affect modifier group display order"
nextSectionFile: adminGuide-adminEnsuringImportantModifierGroupsDisplayFirst.md
nextSectionTitle: "Ensuring important modifier groups display first"
excerpt: "To determine the display order for a menu item's modifier groups, the Toast platform starts by inspecting the Modifier ordering priority setting on the Front of house > Order screen setup > UI..."
keywords: [understanding,modifier,group,display,order,(Menu Group 1 > Modifier B,Required),(Menu Item X > Modifier E,Required),(Menu Group 1 > Modifier A,Optional),(Menu Subgroup 2,Modifier C,Optional),(Menu Item X > Modifier F,Optional)]
procedures: 2
codeExamples: 6
---

### Understanding modifier group display order

To determine the display order for a menu item's modifier groups, the Toast platform starts by inspecting the Modifier ordering priority setting on the Front of house > Order screen setup > UI options page. This section describes the two possible scenarios, when the Modifier ordering priority setting is set to Off and when it is set to On.

**Procedure 8.136. When the Modifier ordering priority is set to Off**

1. If the menu item uses the Size pricing strategy, it will have a Size modifier group associated with it for specifying the size of menu item to order. This Size modifier group is shown first.


2. Next, the remaining modifier groups are sorted by their required/optional setting and put in this order:

- Required modifier groups


- Modifier groups that are optional but include a POS prompt


- Optional modifier groups




3. Next, modifier groups with the same required/optional setting are further sorted according to whether they are inherited from a parent menu group or explicitly defined on the menu item itself. Inherited modifier groups appear first, explicitly defined modifier groups appear second.


4. Next, modifier groups that are inherited from a parent menu group are further sorted using the order that the modifier groups appear in on the menu group’s details page.

Similarly, modifier groups that are explicitly defined on the menu item are further sorted according using the order in which they appear on the menu item details page.



This illustration shows the modifier group display order when the Display Ordering Priority is set to No:

```
- Size modifier group (if one exists)
- Required modifier groups
  - Modifier groups inherited from a parent menu group, in the order 
    shown on the parent menu group's details page
  - Modifier groups defined on the menu item itself, in the order shown
    on the menu item's details page
- Optional with POS prompt modifier groups
  - Modifier groups inherited from a parent menu group, in the order 
    shown on the parent menu group's details page
  - Modifier groups defined on the menu item itself, in the order shown
    on the menu item's details page
- Optional modifier groups
  - Modifier groups inherited from a parent menu group, in the order 
    shown on the parent menu group's details page
  - Modifier groups defined on the menu item itself, in the order shown
    on the menu item's details page
```

**Procedure 8.137. When the Display Ordering Priority is set to Yes**

1. Modifier groups are first sorted by their Display Ordering Priority number. Groups with lower numbers appear before groups with higher numbers or no numbers. For example, a modifier group with a Display Ordering Priorityof 1 appears before a modifier group with a Display Ordering Priority of 2 or those with no number at all.


2. If a Size modifier group exists for the menu item (and it does not have a Display Order Priority number, see the [note](adminUnderstandingModifierGroupDisplay.html#adminNoteAboutSizeModifierGroupsWithDisplayOrderingPriorityNumbers)below), it is sorted after modifier groups that have a Display Ordering Priority number and before modifier groups that do not have a Display Ordering Priority number:

- Groups with a Display Ordering Prioritynumber


- Size modifier group (without a Display Ordering Priority number)


- Groups without a Display Ordering Priority number




3. Next, modifier groups with the same Display Ordering Priority setting are further sorted by their required/optional setting and put in this order:

- Required modifier groups


- Modifier groups that are optional but include a POS prompt


- Optional modifier groups




4. Next, modifier groups with the same required/optional setting are further sorted according to whether they are inherited from a parent menu group or explicitly defined on the menu item itself. Inherited modifier groups appear first, explicitly defined modifier groups appear second.


5. Next, modifier groups that are inherited from a parent menu group are further sorted using the order that the modifier groups appear in on the menu group’s details page.

Similarly, modifier groups that are explicitly defined on the menu item are further sorted according using the order in which they appear on the menu item details page.



This illustration shows the modifier group display order when the Display Ordering Priority is set to Yes:

```
- Modifier groups with a Display Ordering Priority number, in ascending
  order starting from 1
  - Required modifier groups
    - Modifier groups inherited from a parent menu group, in the order 
      shown on the parent menu group's details page
    - Modifier groups defined on the menu item itself, in the order shown
      on the menu item's details page
  - Optional with POS prompt modifier groups
    - Modifier groups inherited from a parent menu group, in the order 
      shown on the parent menu group's details page
    - Modifier groups defined on the menu item itself, in the order shown
      on the menu item's details page
  - Optional modifier groups
    - Modifier groups inherited from a parent menu group, in the order 
      shown on the parent menu group's details page
    - Modifier groups defined on the menu item itself, in the order shown
      on the menu item's details page
- Size modifier group without a Display Ordering Priority number (if one exists)
- Modifier groups without a Display Ordering Priority number
  - Required modifier groups
    - Modifier groups inherited from a parent menu group, in the order 
      shown on the parent menu group's details page
    - Modifier groups defined on the menu item itself, in the order shown
      on the menu item's details page
  - Optional with POS prompt modifier groups
    - Modifier groups inherited from a parent menu group, in the order 
      shown on the parent menu group's details page
    - Modifier groups defined on the menu item itself, in the order shown
      on the menu item's details page
  - Optional modifier groups
    - Modifier groups inherited from a parent menu group, in the order 
      shown on the parent menu group's details page
    - Modifier groups defined on the menu item itself, in the order shown
      on the menu item's details page
```

**Display order when menu subgroups are used **If a menu item is contained within a set of nested menu groups (also called subgroups), then the order of those nested menu groups is taken into account when presenting the required, optional with POS prompt, and optional modifier groups for the menu item.

Consider the following menu hierarchy structure and modifier group assignments:

```
Menu Group 1 - Modifier A, Optional; Modifier B, Required
  Menu Subgroup 2 - Modifier C, Optional; Modifier D, Optional with POS prompt
    Menu Item X - Modifier E, Required; Modifier F, Optional
```

The Toast platform still presents modifier groups for Menu Item X organized by required, optional with POS prompt, and optional settings. Within each of those three categorizations, however, the modifier groups are sequenced according to the nested menu group hierarchy, so Menu Group 1 modifier groups are shown first, followed by Menu Subgroup 2 modifier groups, followed by Menu Item X modifier groups.

This illustration shows the modifier group display order for Menu Item X. To make this example easier to understand, it assumes the Display Ordering Priority is set to No.

```
- Size modifier group (if one exists)
- Required modifier groups
  - Modifier groups inherited from Menu Group 1
    (Menu Group 1 > Modifier B, Required)
  - Modifier groups inherited from Menu Subgroup 2
    (None)
  - Modifier groups defined on the Menu Item X
    (Menu Item X > Modifier E, Required)
- Optional with POS prompt modifier groups
  - Modifier groups inherited from Menu Group 1
    (None)
  - Modifier groups inherited from Menu Subgroup 2
    (Menu Subgroup 2 > Modifier D, Optional with POS prompt)
  - Modifier groups defined on the Menu Item X
    (None)
- Optional modifier groups
  - Modifier groups inherited from Menu Group 1
    (Menu Group 1 > Modifier A, Optional)
  - Modifier groups inherited from Menu Subgroup 2
    (Menu Subgroup 2, Modifier C, Optional)
  - Modifier groups defined on Menu Item X
    (Menu Item X > Modifier F, Optional)
```

Next, we assign priority 1 to some of the modifier groups and set Display Ordering Priority is set to Yes:

```
Menu Group 1 - Modifier A, Optional; Modifier B, Required
  Menu Subgroup 2 - Modifier C, Optional, Priority 1; Modifier D, Optional with POS prompt
    Menu Item X - Modifier E, Required, Priority 1; Modifier F, Optional
```

This illustration shows the modifier group display order for these conditions:

```
- Modifier groups with a Display Ordering Priority number, in ascending
  order starting from 1
  - Required modifier groups
    - Modifier groups inherited from Menu Group 1
      (None)
    - Modifier groups inherited from Menu Subgroup 2
      (None)
    - Modifier groups defined on Menu Item X
      (Menu Item X > Modifier E, Required, Priority 1)
  - Optional with POS prompt modifier groups
    - Modifier groups inherited from Menu Group 1
      (None)
    - Modifier groups inherited from Menu Subgroup 2
      (None)
    - Modifier groups defined on Menu Item X
      (None)
  - Optional modifier groups
    - Modifier groups inherited from Menu Group 1
      (None)
    - Modifier groups inherited from Menu Subgroup 2
      (Menu Subgroup 2 > Modifier C, Optional, Priority 1)
    - Modifier groups defined on Menu Item X
      (None)
- Size modifier group without a Display Ordering Priority number (if one exists)
- Modifier groups without a Display Ordering Priority number
  - Required modifier groups
    - Modifier groups inherited from Menu Group 1
      (Menu Group 1 > Modifier B, Required, No priority)
    - Modifier groups inherited from Menu Subgroup 2
      (None)
    - Modifier groups defined on Menu Item X
      (None)
  - Optional with POS prompt modifier groups
    - Modifier groups inherited from Menu Group 1
      (None)
    - Modifier groups inherited from Menu Subgroup 2
      (Menu Subgroup 2 > Modifier D, Optional with POS prompt, No priority)
    - Modifier groups defined on Menu Item X
      (None)
  - Optional modifier groups
    - Modifier groups inherited from Menu Group 1
      (Menu Group 1 > Modifier A, Optional, No priority)
    - Modifier groups inherited from Menu Subgroup 2
      (None)
    - Modifier groups defined on Menu Item X
      (Menu Item X > Modifier F, Optional, No priority)
```

**Note about Size modifier groups with Display Ordering Priority numbers **Typically, the Size modifier groups that are used to specify menu item sizes do not have Display Ordering Prioritynumbers. This is because they are automatically created when a menu group or item is assigned the Size pricing strategy and, as such, they do not appear as an editable modifier group on the menu group or item’s details page. It is technically possible, however, to manually edit a Size modifier group on the Items Database page in Toast Web and assign it a Display Ordering Priority number. If this occurs, then the Size modifier group is sorted along with any other modifier groups that have a Display Ordering Priority number:

- Groups with a Display Ordering Prioritynumber (including a Size group that has a Display Ordering Priority number)


- Groups without a Display Ordering Prioritynumber



