---
title: "Update skillProficiency"
description: "Update the properties of skillProficiency object in a user's profile."
localization_priority: Normal
author: "kevinbellinger"
ms.prod: "people"
doc_type: "apiPageType"
---

# Update skillproficiency

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [skillProficiency](../resources/skillproficiency.md) object in a user's [profile](../resources/profile.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | User.ReadWrite, User.ReadWrite.All          |
| Delegated (personal Microsoft account) | User.ReadWrite, User.ReadWrite.All          |
| Application                            | User.ReadWrite.All                          |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
PATCH /me/profile/skills/{id}
```

## Request headers

| Name           |Description                  |
|:---------------|:----------------------------|
| Authorization  | Bearer {token}. Required.   |
| Content-Type   | application/json. Required. |


## Request body

In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance, don't include existing values that haven't changed.

| Property     | Type            | Description                                                                                                                        |
|:-------------|:----------------|:-----------------------------------------------------------------------------------------------------------------------------------|
|categories    |String collection| Contains categories a user has associated with the skill (eg: personal, professional, hobby)                                       |
|displayName   |String           | Contains a friendly name for the skill.                                                                                            | 
|proficiency   |string           | Possible values are: `elementary`, `limitedWorking`, `generalProfessional`, `advancedProfessional`, `expert`, `unknownFutureValue`.|
|webUrl        |String           | Contains a link to an information source about the skill.                                                                          |

## Response

If successful, this method returns a `200 OK` response code and an updated [skillProficiency](../resources/skillproficiency.md) object in the response body.

## Examples

### Request

The following is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_skillproficiency"
}-->

```http
PATCH https://graph.microsoft.com/beta/me/profile/skills/{id}
Content-type: application/json

{
  "categories": [
    "categories-value"
  ],
  "displayName": "displayName-value",
  "proficiency": "proficiency-value",
  "webUrl": "webUrl-value"
}
```

### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability. All the properties will be returned from an actual call.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.skillProficiency"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "categories": [
    "categories-value"
  ],
  "displayName": "displayName-value",
  "proficiency": "proficiency-value",
  "webUrl": "webUrl-value"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update skillproficiency",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->