---
author: sangle7
description: "Removes a sitePage from the site pages list in a site."
ms.date: 05/07/2018
title: Delete a page from a SharePoint site
ms.localizationpriority: medium
ms.prod: "sharepoint"
doc_type: apiPageType
---
# Delete page from the site pages list of a site

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Removes a [sitePage][] from the site pages [list][] in a [site][].

[sitePage]: ../resources/sitepage.md
[list]: ../resources/list.md
[site]: ../resources/site.md

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "sitepage_delete" } -->
[!INCLUDE [permissions-table](../includes/permissions/sitepage-delete-permissions.md)]

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
DELETE /sites/{site-id}/pages/{page-id}
```

## Optional request headers

| Name       | Value | Description
|:-----------|:------|:--------------------------------------------------------
| _if-match_ | etag  | If this request header is included and the eTag provided does not match the current tag on the item, a `412 Precondition Failed` response is returned and the item will not be deleted.

## Request body

Do not supply a request body with this method.
<!-- TODO: should we provide a URL to recover/undelete the file, if one exists? -->

## Response

If successful, this call returns a `204 No Content` response to indicate that the resource was deleted and there was nothing to return.

## Example

<!-- { "blockType": "request", "name": "delete-page", "scopes": "files.readwrite sites.readwrite.all" } -->

##### Request

```http
DELETE /sites/{site-id}/pages/{page-id}
```
##### Response

<!-- { "blockType": "response" } -->

```http
HTTP/1.1 204 No Content
```

<!--
{
  "type": "#page.annotation",
  "description": "Delete a page in the SitePages list in a site.",
  "keywords": "",
  "section": "documentation",
  "tocPath": "Pages/Delete",
  "suppressions": []
}
-->


