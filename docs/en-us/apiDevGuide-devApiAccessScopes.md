---
title: "Standard API access scopes"
id: devApiAccessScopes
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-ifYoureAStandardApiAccessDeveloperOmitChunkFromSearchIndex.md
parentSectionTitle: "If you're a standard API access developer"
previousSectionFile: apiDevGuide-devApiAccessRequirements.md
previousSectionTitle: "Standard API access requirements"
nextSectionFile: apiDevGuide-devApiAccessResources.md
nextSectionTitle: "Standard API access resources"
excerpt: "Scopes determine the actions that your Toast API client has permission to perform, which is authenticated using the client ID and secret created in Toast Web. For more information, see ."
keywords: ["delivery_info.address:read", "DeliveryInfo", "digital_schedule:read", "Customer"]
procedures: 0
codeExamples: 0
---

Scopes determine the actions that your Toast API client has
    permission to perform, which is authenticated using the client ID and
    secret created in Toast Web. For more information, see [Scopes](apiDevGuide-apiScopes).

Standard API access provides access to the following scopes:

| Scope | Toast API | 
| --- | --- |
| `cashmgmt:read` | cash management API | 
| `config:read` | configuration API | 
| `delivery_info.address:read`

> **Note**
> 
> This scope exposes additional information in the
                `DeliveryInfo` object of the orders API.


 | orders API | 
| `digital_schedule:read` | order management configuration API | 
| `guest.pi:read`

> **Note**
> 
> This scope to exposes additional information in the
                `Customer` object of the orders API.


 | orders API | 
| `kitchen:read` | kitchen API | 
| `labor.employees:read` | labor API | 
| `labor:read` | labor API | 
| `menus:read` | menus v2 API | 
| `orders:read` | orders API | 
| `packaging:read` | packaging configuration API | 
| `restaurants:read` | restaurant availability API, restaurants API | 
| `stock:read` | stock API | 

