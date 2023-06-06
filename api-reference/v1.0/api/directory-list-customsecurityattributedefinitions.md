---
title: "List customSecurityAttributeDefinitions"
description: "Get a list of the customSecurityAttributeDefinition objects and their properties."
author: "CecilyK"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# List customSecurityAttributeDefinitions

Namespace: microsoft.graph

Get a list of the [customSecurityAttributeDefinition](../resources/customsecurityattributedefinition.md) objects and their properties.

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "directory_list_customsecurityattributedefinitions" } -->
[!INCLUDE [permissions-table](../includes/permissions/directory-list-customsecurityattributedefinitions-permissions.md)]

The signed-in user must also be assigned one of the following [directory roles](/azure/active-directory/roles/permissions-reference):

+ Attribute Definition Reader
+ Attribute Assignment Administrator
+ Attribute Definition Administrator

By default, Global Administrator and other administrator roles do not have permissions to read, define, or assign custom security attributes.

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /directory/customSecurityAttributeDefinitions
```

## Optional query parameters

This method supports the `$select`, `$top`, `$expand`, and `$filter` (`eq`) OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

The **allowedValues** navigation property is not returned or expanded by default and must be specified in an `$expand` query. For example, `/directory/customSecurityAttributeDefinitions?$expand=allowedValues`.

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [customSecurityAttributeDefinition](../resources/customsecurityattributedefinition.md) objects in the response body.

## Examples

### Example 1: Get all custom security attributes

The following example gets all custom security attribute definitions in a tenant.

#### Request

The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "list_customsecurityattributedefinition"
}
-->
``` http
GET https://graph.microsoft.com/v1.0/directory/customSecurityAttributeDefinitions
```

#### Response

The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.customSecurityAttributeDefinition)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#directory/customSecurityAttributeDefinitions",
    "value": [
        {
            "attributeSet": "Engineering",
            "description": "Active projects for user",
            "id": "Engineering_Project",
            "isCollection": true,
            "isSearchable": true,
            "name": "Project",
            "status": "Available",
            "type": "String",
            "usePreDefinedValuesOnly": true
        },
        {
            "attributeSet": "Engineering",
            "description": "Target completion date",
            "id": "Engineering_ProjectDate",
            "isCollection": false,
            "isSearchable": true,
            "name": "ProjectDate",
            "status": "Available",
            "type": "String",
            "usePreDefinedValuesOnly": false
        },
        {
            "attributeSet": "Operations",
            "description": "Target completion date",
            "id": "Operations_Level",
            "isCollection": false,
            "isSearchable": true,
            "name": "Deployment level",
            "status": "Available",
            "type": "String",
            "usePreDefinedValuesOnly": true
        }
    ]
}
```

### Example 2: Filter custom security attributes based on name

The following example retrieves custom security attribute definitions that are named `Project` and are active.

#### Request

The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "list_customsecurityattributedefinition_filter_name"
}
-->
``` http
GET https://graph.microsoft.com/v1.0/directory/customSecurityAttributeDefinitions?$filter=name+eq+'Project'%20and%20status+eq+'Available'
```

#### Response

The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.customSecurityAttributeDefinition)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#directory/customSecurityAttributeDefinitions",
    "value": [
        {
            "attributeSet": "Engineering",
            "description": "Active projects for user",
            "id": "Engineering_Project",
            "isCollection": true,
            "isSearchable": true,
            "name": "Project",
            "status": "Available",
            "type": "String",
            "usePreDefinedValuesOnly": true
        },
        {
            "attributeSet": "Operations",
            "description": "Approved projects",
            "id": "Operations_Project",
            "isCollection": true,
            "isSearchable": true,
            "name": "Project",
            "status": "Available",
            "type": "String",
            "usePreDefinedValuesOnly": true
        }
    ]
}
```

### Example 3: Filter custom security attributes based on attribute set

The following example retrieves custom security attribute definitions that are in the `Engineering` attribute set, are active, and of type String.

#### Request

The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "list_customsecurityattributedefinition_filter_attributeset"
}
-->
``` http
GET https://graph.microsoft.com/v1.0/directory/customSecurityAttributeDefinitions?$filter=attributeSet+eq+'Engineering'%20and%20status+eq+'Available'%20and%20type+eq+'String'
```

#### Response

The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.customSecurityAttributeDefinition)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#directory/customSecurityAttributeDefinitions",
    "value": [
        {
            "attributeSet": "Engineering",
            "description": "Active projects for user",
            "id": "Engineering_Project",
            "isCollection": true,
            "isSearchable": true,
            "name": "Project",
            "status": "Available",
            "type": "String",
            "usePreDefinedValuesOnly": true
        },
        {
            "attributeSet": "Engineering",
            "description": "Target completion date (YYYY/MM/DD)",
            "id": "Engineering_ProjectDate",
            "isCollection": false,
            "isSearchable": true,
            "name": "ProjectDate",
            "status": "Available",
            "type": "String",
            "usePreDefinedValuesOnly": false
        }
    ]
}
```
