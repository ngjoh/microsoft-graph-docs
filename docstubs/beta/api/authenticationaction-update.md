---
title: "Update authenticationAction"
description: ""
localization_priority: Normal
author: "$(metadata.owner)"
ms.prod: "microsoft-identity-platform"
doc_type: "apiPageType"
---

# Update authenticationAction

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of an authenticationAction object.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from most to least privileged) |
| :------------------------------------- | :------------------------------------------ |
| Delegated (work or school account)     |                                             |
| Delegated (personal Microsoft account) |                                             |
| Application                            |                                             |

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

```http

```

## Request headers

| Name          | Description                 |
| :------------ | :-------------------------- |
| Authorization | Bearer {token}. Required.   |
| Content-Type  | application/json. Required. |

## Request Body

In the request body, supply JSON representation of the [authenticationAction](../resources/-authenticationaction.md) object.

<!-- Actions and Functions -->

<!-- CRUD Methods -->

The following table shows the properties that are required when you create an authenticationAction object.

| Property     | Type                                                                     | Description |
| :----------- | :----------------------------------------------------------------------- | :---------- |
| id           | String                                                                   | Read-only.  |
| priority     | Int32                                                                    |             |
| sourceFilter | [authenticationSourceFilter](../resources/authenticationsourcefilter.md) |             |

## Response

If successful, this method returns a `200 OK` response code and an authenticationAction object in the response body.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "update_authenticationaction"
}
-->

```http
PATCH https://graph.microsoft.com/beta/identity/events/onSignupStart/{id}

Content-Type: application/json
Content-Length: 233

{
  "@odata.type": "#microsoft.graph.invokeUserFlowAction",
  "priority": "Int32",
  "sourceFilter": {
    "@odata.type": "#microsoft.graph.authenticationSourceFilter",
    "includeApplications": [
      "String"
    ]
  }
}

```

### Response

**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Microsoft.Cpim.Api.DataModels.authenticationAction"
}
-->

```http
HTTP 1.1 200 OK

Content-Type: application/json
{
  "value": {
  "@odata.type": "#microsoft.graph.invokeUserFlowAction",
  "id": "String(identifier)",
  "priority": "Int32",
  "sourceFilter": {
    "@odata.type": "#microsoft.graph.authenticationSourceFilter",
    "includeApplications": [
      "String"
    ]
  }
}
}

```