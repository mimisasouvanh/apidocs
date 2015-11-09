# List pages

Retrieve a list of [page](../resources/page.md) objects.
### Prerequisites
One of the following **scopes** is required to execute this API:  
Notes.Read, Notes.ReadWrite.CreatedByApp, Notes.ReadWrite, Notes.Read.All, or Notes.ReadWrite.All
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /me/notes/pages
GET /users/<mail>/notes/pages
GET /users/<objectId>/notes/pages
GET /groups/<objectId>/notes/pages
```
### Optional query parameters
|Name|Value|Description|
|:---------------|:--------|:-------|
|$search|string|The term or phrase to search for in the page title, page body, image alt text, and image OCR text. Search queries return results sorted by relevance.|
|$count|none|The count of related entities to return in the result set.|
|$expand|string|Comma-separated list of relationships to expand and include in the response. The default response expands `parentSection` and selects the section's `id`, `name`, and `self` properties. Valid values for pages are `parentNotebook` and `parentSection`.|
|$filter|string|Filter string that lets you filter the response based on a set of criteria.|
|$orderby|string|Comma-separated list of properties that are used to sort the order of items in the response collection. The default for pages is `lastModifiedTime desc`.|
|$select|string|Comma-separated list of properties to include in the response.|
|$skip|int|The number of items to skip in the result set.|
|$top|int|The number of items to return in the result set. The default for pages is 20 and the maximum is 100. The default query returns an `@odata.nextLink` that you can use to page through the result set. |

### Request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | `Bearer <token>` A valid OAuth token provided to the app based on the user credentials and the user having authorized access. |
| Accept | string | `application/json` |

### Request body
Do not supply a request body for this method.
### Response
If successful, this method returns a `200 OK` response code and a collection of [page](../resources/page.md) objects in the response body.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "get_pages"
}-->
```http
GET https://graph.microsoft.com/beta/users/<objectId>/notes/pages
Authorization: Bearer <token>
Accept: application/json
```
##### Response
Here is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "microsoft.graph.page",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 484
...

{
  "value": [
    {
      "title": "title-value",
      "createdByAppId": "createdByAppId-value",
      "links": {
        "oneNoteClientUrl": {
          "href": "href-value"
        },
        "oneNoteWebUrl": {
          "href": "href-value"
        }
      },
      "contentUrl": "contentUrl-value",
      "content": "content-value",
      "lastModifiedTime": "datetime-value",
      "id": "id-value",
      "self": "self-value",
      "createdTime": "datetime-value",
      "parentSection": {
        "id": "parentSection-id-value",
        "name": "parentSection-name-value",
        "self": "parentSection-self-value"
      }
    }
  ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "List pages",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->