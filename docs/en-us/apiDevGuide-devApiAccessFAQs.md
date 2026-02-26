---
title: "Standard API access FAQs"
id: devApiAccessFAQs
type: section
documentId: apiDevGuide
parentSectionFile: apiDevGuide-ifYoureAStandardApiAccessDeveloperOmitChunkFromSearchIndex.md
parentSectionTitle: "If you're a standard API access developer"
previousSectionFile: apiDevGuide-devApiAccessWebhookSubscriptions.md
previousSectionTitle: "Standard API access webhook subscriptions"
nextSectionFile: apiDevGuide-devApiAccessSupportStandardApiAccess.md
nextSectionTitle: "Standard API access support"
excerpt: "Why is the &quot;Manage Credentials&quot; interface not visible? You must have the &quot;Manage Integrations&quot; permission to view the &quot;Manage Credentials&quot; interface."
keywords: ["POST", "GET"]
procedures: 0
codeExamples: 0
---

| **Q:** | Why is the "Manage Credentials" interface not visible? | 
| **A:** | You must have the "Manage Integrations" permission to view the "Manage Credentials" interface. | 

| **Q:** | How do I add new locations to my existing credentials? | 
| **A:** | You can add new locations on the Edit credentials page. For information on how to edit which location(s) you have standard API access to, see [Editing standard API access credentials](apiDevGuide-devApiAccessCredentials#devApiAccessEditingCredentials). | 

| **Q:** | Why is there a lock next to a Toast POS location that is not available (appears dimmed)? | 
| **A:** | If a location displays a lock and is displayed as not available (appears dimmed), that indicates that the location does not have access to Toast Restaurant Management Suite Essentials or higher. Every location you want to have standard API access to requires a subscription to Toast Restaurant Management Suite Essentials or higher.Changes made to locations with an active subscription to Toast Restaurant Management Suite Essentials or higher may take a few minutes to be reflected in the Toast platform. | 

| **Q:** | Why am I seeing a 401 error when making an API request? | 
| **A:** | You may see a 401 error because you did not authenticate with valid credentials. For more information on authentication, see [Authentication and restaurant access](apiDevGuide-authentication). For more information about error codes, see [API responses and errors](apiDevGuide-apiResponsesAndErrors). | 

| **Q:** | Why am I seeing a 403 error when making an API request? | 
| **A:** | You may see a 403 error message when making an API request for any of the following reasons:- You made a `POST` request. Standard API access only supports `GET` requests.
- You tried to access the `menus /v3`endpoints. Standard API access only supports `menus /v2` endpoints.
- Your credentials do not include access to this restaurant. For information on how to edit which location(s) you have standard API access to, see [Editing standard API access credentials](apiDevGuide-devApiAccessCredentials#devApiAccessEditingCredentials).
- Your API client is missing the required scope for this endpoint. For information on how to edit the scopes configured for a client, see [Editing standard API access credentials](apiDevGuide-devApiAccessCredentials#devApiAccessEditingCredentials).



> **Note**
> 
> This list is not exhaustive. For more information about error codes, see [API responses and errors](apiDevGuide-apiResponsesAndErrors).


 | 

| **Q:** | Why don't I have access to create standard API access credentials? | 
| **A:** | Confirm that you have the Manage Integrations permission for the location(s) you want to create credentials for. If you do not have permission, contact your restaurant or store team to have the permission assigned. | 

| **Q:** | Why can’t I see guest data in the JSON for an in-store order? | 
| **A:** | Guest data is only provided for orders that have a dining behavior of either Takeout or Delivery. Guest data is not provided for in-store orders. | 

