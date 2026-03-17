---
title: "Creating an assembly line"
id: platformKDSCreatingAssemblyLines
type: section
documentId: adminGuide
parentSectionFile: adminGuide-platformKitchenConfigurationOmitChunkFromSearchIndex.md
parentSectionTitle: "Kitchen configuration"
previousSectionFile: adminGuide-adminAddPrepStation.md
previousSectionTitle: "Adding a prep station"
nextSectionFile: adminGuide-adminAddKitchenPrinter.md
nextSectionTitle: "Adding a kitchen printer"
excerpt: "An assembly line is created using prep stations that are then moved into the correct sequence. Before you create an assembly line, make sure that:"
keywords: ["creating", "assembly", "line"]
procedures: 1
codeExamples: 0
---

An assembly line is created using prep stations that are then moved into the correct sequence. Before you create an assembly line, make sure that:

- You [created prep stations](adminGuide-adminAddPrepStation).


- You set the [**Fulfillment Method**](adminGuide-adminKitchenDiningRoomReference#configFulfillmentMethod) setting to **Fulfill at each station independently**.


- You verified that the menu entity and the assembly line you plan to assign to that menu entity use at least one of the same prep stations.



After you verify that these prerequisites are complete, you can create the assembly line and then assign the [assembly line to the relevant menus, menu groups, and menu items](adminGuide-platformKDSRoutingUsingAssemblyLines#platformKDSAssignAssemblyLinesToMenuEntities).

There is no maximum number of prep stations that you can use in an assembly line, but you can only use a prep station once in an assembly line.

The following procedure is for creating an assembly line for a single-restaurant location. For information about how to create assembly lines for multi-location restaurants, see [Assembly lines for multi-location restaurants](adminGuide-platformKDSCreatingAssemblyLines#platformKDSCreatingAssemblyLinesMultiLocation).

**Procedure 10.2. To create an assembly line**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose **Kitchen &gt; Kitchen stations &gt; Assembly lines**. The **Assembly Lines** page opens.


3. Select the **Add new** button in the top right. The **New assembly line** dialog opens.


4. Using the **Name** text box, assign a name to the assembly line and select **Okay**. The assembly line page opens.


5. Under the **Sequence Prep Stations** section, use the **Prep stations** dropdown menu to select the prep stations you want to use in the assembly line. You can also use the search box within the dropdown menu to find a specific prep station.


6. Use the reorder icon to hold and move the prep stations into the order you want items to travel through when using the assembly line.


7. Select the **Save** button. The assembly line page closes.


8. Publish your changes.



## Assembly lines for multi-location restaurants

Assembly lines use versioning and targets for multi-location restaurants. The following procedure is for creating an assembly line for a multi-location restaurant. For information about versions, see [Versions](adminGuide-versions). For information about targets, see [Targets](adminGuide-targets).

**Procedure 10.3. To create an assembly line for multi-location restaurants**

1. [Access Toast Web](adminGuide-adminAccessToastAdminBackend).


2. Choose **Kitchen &gt; Kitchen stations &gt; Assembly lines**. The **Assembly Lines** page opens.


3. Use the locations dropdown menu to select which locations you want to view.


4. Select the **Add new** button in the top right. The **New assembly line** dialog opens.


5. Using the **Name** text box, assign a name to the assembly line.


6. Select the **Target** dropdown menu. The **Select Target** dialog opens.


7. Using either the **Restaurant groups** or **Locations** tab, select the location you want to have access to this assembly line. You can only choose one location.



> **Note**
> 
> The **Owner** setting automatically defaults to the **Target** setting.



8. Select **Okay**. The assembly line page opens.



> **Note**
> 
> The **Location specific variant** option is currently unavailable.



9. Under the **Sequence Prep Stations** section, use the **Prep stations** dropdown menu to select the prep stations you want to use in the assembly line. You can also use the search box within the dropdown menu to find a specific prep station.


10. Use the reorder icon to hold and move the prep stations into the order you want items to travel through when using the assembly line.


11. Select the **Save** button. The assembly line page closes.


12. Publish your changes.



