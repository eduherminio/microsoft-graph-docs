---
title: "searchEntity: query"
description: "Runs the query specified in the request body. Search results are provided in the response"
ms.localizationpriority: medium
author: "njerigrevious"
ms.prod: "search"
doc_type: "apiPageType"
---

# searchEntity: query

Namespace: microsoft.graph

Runs the query specified in the request body. Search results are provided in the response.


## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "search_query" } -->
[!INCLUDE [permissions-table](../includes/permissions/search-query-permissions.md)]

## HTTP request

```HTTP
POST /search/query
```

## Request headers

| Name          | Description   |
|:--------------|:--------------|
| Authorization | Bearer {token}. Required. |
| Content-type | application/json. Required. |

## Request body

In the request body, provide a JSON object with the following parameters.

| Parameter    | Type        | Description |
|:-------------|:------------|:------------|
|requests|[searchRequest](../resources/searchrequest.md) collection|A collection of one or more search requests each formatted in a JSON blob. Each JSON blob contains the types of resources expected in the response, the underlying sources, paging parameters, requested fields, and actual search query. Be aware of [known limitations](../resources/search-api-overview.md#known-limitations) on searching specific combinations of entity types, and sorting or aggregating search results. |

## Response

If successful, this method returns `HTTP 200 OK` response code and a [searchResponse](../resources/searchresponse.md) collection object in the response body.
 

## Examples

### Example 1: Basic call to perform a search request

The following example shows how to search for expected connector items.

#### Request

```HTTP
POST https://graph.microsoft.com/v1.0/search/query
Content-type: application/json

{
  "requests": [
    {
      "entityTypes": [
        "externalItem"
      ],
      "contentSources": [
        "/external/connections/connectionfriendlyname"
      ],
      "query": {
        "queryString": "contoso product"
      },
      "from": 0,
      "size": 25,
      "fields": [
        "title",
        "description"
      ]
    }
  ]
}
```

#### Response

The following example shows the response.

```HTTP
HTTP/1.1 200 OK
Content-type: application/json

{
  "value": [
    {
      "searchTerms": [
        "searchTerms-value"
      ],
      "hitsContainers": [
        {
          "hits": [
            {
              "hitId": "1",
              "rank": 1,
              "summary": "_summary-value",
              "resource": "The source field will contain the underlying graph entity part of the response"
            }
          ],
          "total": 47,
          "moreResultsAvailable": true
        }
      ]
    }
  ]
}
```

### Example 2: Basic call to use queryTemplate

The following example shows how to use the queryable property **createdBy** to retrieve all files created by a user.

#### Request

```HTTP
POST https://graph.microsoft.com/v1.0/search/query
Content-type: application/json

{
  "requests": [
    {
      "entityTypes": [
        "listItem"
      ],
      "query": {
        "queryString": "contoso",
        "queryTemplate":"{searchTerms} CreatedBy:Bob"
      },
      "from": 0,
      "size": 25
    }
  ]
}
```

#### Response

The following example shows the response.

```HTTP
HTTP/1.1 200 OK
Content-type: application/json

{
    "value": [
        {
            "searchTerms": [
                "contoso"
            ],
            "hitsContainers": [
                {
                    "hits": [
                        {
                            "hitId": "1",
                            "rank": 1,
                            "summary": "_summary-value",
                            "resource": {
                                "@odata.type": "#microsoft.graph.listItem",
                                "id": "c23c7035-73d6-4bad-8901-9e2930d4be8e",
                                "createdBy": {
                                    "user": {
                                        "displayName": "Bob",
                                        "email": "Bob@contoso.com"
                                    }
                                },
                                "createdDateTime": "2021-11-19T17:04:18Z",
                                "lastModifiedDateTime": "2023-03-09T18:52:26Z"
                            }
                        }
                    ],
                    "total": 1,
                    "moreResultsAvailable": false
                }
            ]
        }
    ]
}
```

## See also
- Search [mail messages](/graph/search-concept-messages)
- Search [calendar events](/graph/search-concept-events)
- Search content in SharePoint and OneDrive ([files, lists and sites](/graph/search-concept-files))
- Search [custom types (Graph Connectors)](/graph/search-concept-custom-types) data
- Search with [queryTemplate](/graph/search-concept-query-template)
- [Sort](/graph/search-concept-sort) search results
- Use [aggregations](/graph/search-concept-aggregation) to refine search results


<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "search: query",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


