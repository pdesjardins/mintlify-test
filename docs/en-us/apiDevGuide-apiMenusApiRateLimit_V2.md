---
title: "Menus API rate limit"
id: apiMenusApiRateLimit_V2
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-apiGettingMenuInformationOmitChunkFromSearchIndex.md
parentSectionTitle: "Getting menu information"
previousSectionFile: apiDevGuide-apiDeterminingIfYourMenuJsonIsOutdated_V2.md
previousSectionTitle: "Determining if a restaurant's menu data has gone stale"
nextSectionFile: apiDevGuide-apiMenusApiReturnsFullyResolvedJson_V2.md
nextSectionTitle: "Menus API returns fully resolved JSON"
excerpt: "The GET /menus endpoint of the menus API uses an endpoint rate limit for each..."
keywords: ["menus", "rate", "limit", "GET /menus", "GET /metadata"]
procedures: 0
codeExamples: 0
---

The `GET /menus` endpoint of the menus API uses an endpoint rate limit for each client of one request per second per location. Requests that your API client makes for one restaurant do not affect the client's rate limits for any other restaurant. Note that this is a lower rate limit than the default API rate limit that is enforced for other Toast APIs. The `GET /metadata` endpoint of the menus API uses the default API rate limit described in [Toast rate limit values](apiDevGuide-apiRateLimiting#apiToastRateLimits).

For more information on rate limits for Toast APIs, see [Rate limiting](apiDevGuide-apiRateLimiting).

