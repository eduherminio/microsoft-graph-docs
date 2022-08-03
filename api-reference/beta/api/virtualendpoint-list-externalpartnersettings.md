---
title: "List cloudPcExternalPartnerSettings"
description: "Get a list of the cloudPcExternalPartnerSetting objects and their properties."
author: "Shaowei-Dong"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: apiPageType
---

# List cloudPcExternalPartnerSettings
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [cloudPcExternalPartnerSetting](../resources/cloudpcexternalpartnersetting.md) objects and their properties.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|CloudPC.Read.All, CloudPC.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|CloudPC.Read.All, CloudPC.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /deviceManagement/virtualEndpoint/externalPartnerSettings
```

## Optional query parameters
This method supports the `$select` and `$filter` OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [cloudPcExternalPartnerSetting](../resources/cloudpcexternalpartnersetting.md) objects in the response body.

## Examples

### Example 1: Get all external partner settings

#### Request

The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "list_cloudpcexternalpartnersetting"
}
-->
``` http
GET https://graph.microsoft.com/beta/deviceManagement/virtualEndpoint/externalPartnerSettings
```


#### Response
The following is an example of the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.cloudPcExternalPartnerSetting",
  "isCollection": true
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context": "https://canary.graph.microsoft.com/testprodbeta_cpc_int/$metadata#deviceManagement/virtualEndpoint/externalPartnerSettings",
  "value": [
    {
      "id": "b3548526-e615-3785-3118-be70b3968ec5",
      "partnerId": "198d7140-80bb-4843-8cc4-811377a49a92",
      "enableConnection": true,
      "lastSyncDateTime": "2020-11-03T12:43:14Z",
      "status": "available",
      "statusDetails": "The external partner is available"
    },
    {
      "id": "dc6422cb-3001-45a7-9dcd-21207eea6b0e",
      "partnerId": "459a0e56-da26-4ba1-a729-8eeef733425b",
      "enableConnection": true,
      "lastSyncDateTime": "2020-11-03T12:43:14Z",
      "status": "available",
      "statusDetails": "The external partner is available"
    }
  ]
}
```

### Example 2: Use $select to get all external partner settings

#### Request

The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "list_cloudpcexternalpartnersetting"
}
-->
``` http
GET https://graph.microsoft.com/beta/deviceManagement/virtualEndpoint/externalPartnerSettings?$select=id,partnerId,enableConnection
```


#### Response
The following is an example of the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.cloudPcExternalPartnerSetting",
  "isCollection": true
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#deviceManagement/virtualEndpoint/externalPartnerSettings(id,partnerId,enableConnection)",
  "value": [
    {
      "id": "b3548526-e615-3785-3118-be70b3968ec5",
      "partnerId": "198d7140-80bb-4843-8cc4-811377a49a92",
      "enableConnection": true
    },
    {
      "id": "dc6422cb-3001-45a7-9dcd-21207eea6b0e",
      "partnerId": "459a0e56-da26-4ba1-a729-8eeef733425b",
      "enableConnection": true
    }
  ]
}
```