---
title: "Delete retentionEventType"
description: "Deletes a retentionEventType object."
author: "sseth"
ms.localizationpriority: medium
ms.prod: "security"
doc_type: apiPageType
---

# Delete retentionEventType
Namespace: microsoft.graph.security

Delete a [retentionEventType](../resources/security-retentioneventtype.md) object.

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "security_retentioneventtype_delete" } -->
[!INCLUDE [permissions-table](../includes/permissions/security-retentioneventtype-delete-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
DELETE /security/labels/retentionLabels/{retentionLabelId}/eventType/$ref
DELETE /security/triggerTypes/retentionEventTypes/{retentionEventTypeId}/$ref
DELETE /security/triggers/retentionEvents/{retentionEventId}/retentionEventType/$ref
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

### Request

<!-- {
  "blockType": "request",
  "name": "delete_retentioneventtype"
}
-->
``` http
DELETE https://graph.microsoft.com/v1.0/security/triggerTypes/retentionEventTypes/{retentionEventTypeId}
```


### Response
>
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```

