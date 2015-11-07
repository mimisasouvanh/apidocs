# section: copyToNotebook
Copies a section to a specific notebook.

### Prerequisites
One of the following **scopes** is required to execute this API:   
Notes.ReadWrite.CreatedByApp, Notes.ReadWrite, or Notes.ReadWrite.All 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /me/notes/sections/<id>/copyToNotebook
POST /users/<mail>/notes/sections/<id>/copyToNotebook
POST /users/<objectId>/notes/sections/<id>/copyToNotebook
POST /groups/<objectId>/notes/sections/<id>/copyToNotebook
```
### Request headers
| Name       | Type | Description|
|:---------------|:--------|:----------|
| Authorization  | string  | `Bearer <token>` A valid OAuth token provided to the app based on the user credentials and the user having authorized access. |
| Content-Type | string | `application/json` |

### Request body
In the request body, provide a JSON object with the following parameters.

| Parameter	   | Type	|Description|
|:---------------|:--------|:----------|
|id|String|The id of the destination notebook. |
|renameAs|String|The name of the copy. Defaults to the name of the existing item. |

<!--groupId missing-->
<!--|siteCollectionId|String||
|siteId|String||-->

### Response
If successful, this method returns `202 Accepted` response code and a [copySectionModel](../resources/copysectionmodel.md) object in the response body.

### Example
Here is an example of how to call this API.
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "section_copytonotebook"
}-->
```http
POST https://graph.microsoft.com/beta/users/<objectId>/notes/sections/<id>/copyToNotebook
Content-type: application/json
Content-length: 130

{
  "id": "id-value",
  "siteCollectionId": "siteCollectionId-value",
  "siteId": "siteId-value",
  "renameAs": "renameAs-value"
}
```

##### Response
Here is an example of the response. <!--TEST no copy*Model in O365 implementation-->
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "microsoft.graph.copysectionmodel"
} -->
```http
HTTP/1.1 202 Accepted
Content-Type: application/json
Content-Length: 276

{
  "isDefault": true,
  "pagesUrl": "pagesUrl-value",
  "name": "name-value",
  "createdBy": "createdBy-value",
  "lastModifiedBy": "lastModifiedBy-value",
  "lastModifiedTime": "datetime-value",
  "id": "id-value",
  "self": "self-value",
  "createdTime": "datetime-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "section: copyToNotebook",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->