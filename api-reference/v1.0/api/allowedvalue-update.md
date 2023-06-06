---
title: "Update allowedValue"
description: "Update the properties of an allowedValue object."
author: "CecilyK"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# Update allowedValue

Namespace: microsoft.graph

Update the properties of an [allowedValue](../resources/allowedvalue.md) object.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "allowedvalue_update" } -->
[!INCLUDE [permissions-table](../includes/permissions/allowedvalue-update-permissions.md)]

[!INCLUDE [rbac-customsecurityattibutes-apis-write](../includes/rbac-for-apis/rbac-customsecurityattibutes-apis-write.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /directory/customSecurityAttributeDefinitions/{customSecurityAttributeDefinitionId}/allowedValues/{allowedValueId}
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body

[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]

|Property|Type|Description|
|:---|:---|:---|
|isActive|Boolean|Indicates whether the predefined value is active or deactivated. If `false`, this predefined value cannot be assigned to any additional supported directory objects. Optional.|

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

### Request

The following example deactivates a predefined value for a custom security attribute definition.

+ Attribute set: `Engineering`
+ Attribute: `Project`
+ Predefined value: `Alpine`

<!-- {
  "blockType": "request",
  "name": "update_allowedvalue",
  "sampleKeys": ["Engineering_Project", "Alpine"]
}
-->
``` http
PATCH https://graph.microsoft.com/v1.0/directory/customSecurityAttributeDefinitions/Engineering_Project/allowedValues/Alpine
Content-Type: application/json
Content-length: 80

{
    "isActive": "false"
}
```

### Response

The following is an example of a response.

<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```
