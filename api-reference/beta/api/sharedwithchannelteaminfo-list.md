---
title: "List sharedWithChannelTeamInfo"
description: "Get the list of teams shared with a channel."
author: "devjha-ms"
doc_type: "apiPageType"
ms.localizationpriority: high
ms.prod: "microsoft-teams"
---

# List sharedWithChannelTeamInfo
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get the list of [teams](../resources/sharedwithchannelteaminfo.md) shared with a [channel](../resources/channel.md). This operation is allowed only for channels with a **membershipType** value of `shared`.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|ChannelMember.Read.All, ChannelMember.ReadWrite.All |
|Delegated (personal Microsoft account)|Not supported.|
|Application|ChannelMember.Read.All, ChannelMember.ReadWrite.All |

> **Note**: This API supports admin permissions. Global admins and Microsoft Teams service admins can access teams that they are not a member of.

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /teams/{team-id}/channels/{channel-id}/sharedWithTeams
```

## Optional query parameters
This method supports the `$filter` and `$select` [OData query parameters](/graph/query-parameters) to help customize the response.

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [sharedWithChannelTeamInfo](../resources/sharedwithchannelteaminfo.md) objects in the response body.

## Examples

### Request
The following is an example of the request.
<!-- {
  "blockType": "request",
  "name": "list_sharedwithchannelteaminfo"
}
-->
``` http
GET https://graph.microsoft.com/beta/teams/893075dd-2487-4122-925f-022c42e20265/channels/19:561fbdbbfca848a484f0a6f00ce9dbbd@thread.tacv2/sharedWithTeams
```


### Response
The following is an example of the response.
<!-- {
  "blockType": "response",
  "@odata.type": "microsoft.graph.sharedWithChannelTeamInfo",
  "isCollection": true
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.sharedWithChannelTeamInfo",
      "id": "2173de69-de69-2173-69de-732169de7321",
      "tenantId": "b3246f44-b4gb-4627-96c6-25b18fa2c910",
      "displayName": "Team Contosso",
      "isHostTeam": true
    },
    {
      "@odata.type": "#microsoft.graph.sharedWithChannelTeamInfo",
      "id": "893075dd-2487-4122-86db-022c42e20265",
      "displayName": "Team fabricam",
      "isHostTeam": false,
      "tenantId": "b3246f44-b4gb-5678-96c6-25b18fa2c910"
    }
  ]
}
```

