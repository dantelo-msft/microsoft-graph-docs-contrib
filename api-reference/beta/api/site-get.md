---
author: spgraph-docs-team
description: "Retrieve properties and relationships for a site resource."
title: Get a SharePoint Site
ms.localizationpriority: medium
ms.subservice: "sharepoint"
doc_type: apiPageType
ms.date: 04/05/2024
---
# Get a site resource

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve properties and relationships for a [site][] resource.
A **site** resource represents a team site in SharePoint.

[site]: ../resources/site.md

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "site_get" } -->
[!INCLUDE [permissions-table](../includes/permissions/site-get-permissions.md)]

## HTTP request

### Get the tenant's root site

To access the root SharePoint site within a tenant:

<!-- { "blockType": "ignored" } -->

```http
GET /sites/root
GET /sites/contoso.sharepoint.com
```

### Access a site by server-relative URL

If you have the server-relative URL for a **site** resource, you can construct a request as follows:

```http
GET /sites/{hostname}:/{server-relative-path}
```

### Access a group team site

To access the team site for a group:

```http
GET /groups/{group-id}/sites/root
```

## Examples

### Example 1: Get a site using the site ID
#### Request

The following example shows a request that gets a site by its site ID. A site ID is the value of the **id** property of its **site** resource. For more information on the format of the site ID, see [site](../resources/site.md#id-property).

<!-- { "blockType": "request", "name": "get-site", "sampleKeys": ["contoso.sharepoint.com,2C712604-1370-44E7-A1F5-426573FDA80A,2D2244C3-251A-49EA-93A8-39E1C3A060FE"] } -->

```msgraph-interactive
GET https://graph.microsoft.com/beta/sites/contoso.sharepoint.com,2C712604-1370-44E7-A1F5-426573FDA80A,2D2244C3-251A-49EA-93A8-39E1C3A060FE
```

#### Response
The following example shows the response.
<!-- { "blockType": "response", "@type": "microsoft.graph.site", "truncated": true } -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "contoso.sharepoint.com,2C712604-1370-44E7-A1F5-426573FDA80A,2D2244C3-251A-49EA-93A8-39E1C3A060FE",
  "owner": {
    "user": {
      "displayName": "Daron Spektor",
      "id": "5280E7FE-DC7A-4486-9490-E790D81DFEB3"
    }
  },
  "displayName": "OneDrive Team Site",
  "name": "1drvteam",
  "createdDateTime": "2017-05-09T20:56:00Z",
  "lastModifiedDateTime": "2017-05-09T20:56:01Z",
  "webUrl": "https://contoso.sharepoint.com/teams/1drvteam"
}
```

### Example 2: Get a site by server relative URL
#### Request

The following example shows a request that gets a site by its hostname and server relative path.

<!-- { "blockType": "request", "name": "get-site-by-url", "scopes": "sites.read.all", "sampleKeys": ["contoso.sharepoint.com:/teams/1drvteam"] } -->
```http
GET https://graph.microsoft.com/beta/sites/contoso.sharepoint.com:/teams/1drvteam
```

#### Response
The following example shows the response.
<!-- { "blockType": "response", "@type": "microsoft.graph.site", "truncated": true } -->
```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "contoso.sharepoint.com,2C712604-1370-44E7-A1F5-426573FDA80A,2D2244C3-251A-49EA-93A8-39E1C3A060FE",
  "displayName": "OneDrive Team Site",
  "name": "1drvteam",
  "createdDateTime": "2017-05-09T20:56:00Z",
  "lastModifiedDateTime": "2017-05-09T20:56:01Z",
  "webUrl": "https://contoso.sharepoint.com/teams/1drvteam"
}
```

### Example 3: Get the site of a group
#### Request
The following example shows a request that gets a group's site by the **id** property of a [group](../resources/group.md).

<!-- { "blockType": "request", "name": "get-site-by-group"} -->
```msgraph-interactive
GET https://graph.microsoft.com/beta/groups/2C712604-1370-44E7-A1F5-426573FDA80A/sites/root
```

#### Response
The following example shows the response.

<!-- { "blockType": "response", "@type": "microsoft.graph.site", "truncated": true } -->
```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "contoso.sharepoint.com,2C712604-1370-44E7-A1F5-426573FDA80A,2D2244C3-251A-49EA-93A8-39E1C3A060FE",
  "displayName": "OneDrive Team Site",
  "name": "1drvteam",
  "createdDateTime": "2017-05-09T20:56:00Z",
  "lastModifiedDateTime": "2017-05-09T20:56:01Z",
  "webUrl": "https://contoso.sharepoint.com/teams/1drvteam"
}
```
<!--
{
  "type": "#page.annotation",
  "description": "",
  "keywords": "",
  "section": "documentation",
  "tocPath": "Sites/Get by ID",
  "suppressions": [
  ]
}
-->


