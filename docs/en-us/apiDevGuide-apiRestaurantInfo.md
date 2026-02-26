---
title: "Restaurant information overview"
id: apiRestaurantInfo
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-portalApiGettingRestaurantInfoOmitChunkFromSearchIndex.md
parentSectionTitle: "Chapter 6. Restaurant info"
previousSectionFile: apiDevGuide-portalApiGettingRestaurantInfoOmitChunkFromSearchIndex.md
previousSectionTitle: "Chapter 6. Restaurant info"
nextSectionFile: apiDevGuide-apiRestaurantBusinessDate.md
nextSectionTitle: "Restaurant closeoutHour and business dates"
excerpt: "The restaurants API has endpoints that let you obtain two types of information about restaurants:"
keywords: ["/restaurants/v1/groups/{managementGroupGUID}/restaurants", "/restaurants/v1/restaurants/{restaurantGUID}"]
procedures: 0
codeExamples: 0
---

The restaurants API has endpoints that let you obtain two types of information about restaurants:

- The `/restaurants/v1/groups/&#123;managementGroupGUID&#125;/restaurants`endpoint returns a list of the restaurants that belong to a restaurant management group.


- The `/restaurants/v1/restaurants/&#123;restaurantGUID&#125;`endpoint returns configuration information about a specific restaurant location. This configuration information is more business oriented (such as the restaurant's location, services, and schedules) than the information returned by the [configuration API](apiDevGuide-apiPartnersGettingAccessibleRestaurants).



