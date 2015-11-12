# section: copyToNotebook
Copies a section to a specific notebook.

### Prerequisites
One of the following **scopes** is required to execute this API:   
Notes.ReadWrite.CreatedByApp, Notes.ReadWrite, or Notes.ReadWrite.All 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /me/notes/sections/<id>/Microsoft.Graph.copyToNotebook
POST /users/<mail>/notes/sections/<id>/Microsoft.Graph.copyToNotebook
POST /users/<objectId>/notes/sections/<id>/Microsoft.Graph.copyToNotebook
POST /groups/<objectId>/notes/sections/<id>/Microsoft.Graph.copyToNotebook
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
|groupId|String|The id of the group to copy to. Use only when copying to an Office 365 group.|
|id|String|The id of the destination notebook. |
|renameAs|String|The name of the copy. Defaults to the name of the existing item. |

### Response
If successful, this method returns a `202 Accepted` response code.

### Example
Here is an example of how to call this API.
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "section_copytonotebook"
}-->
```http
POST https://graph.microsoft.com/beta/users/<objectId>/notes/sections/<id>/Microsoft.Graph.copyToNotebook
Content-Type: application/json
Content-Length: 56

{
  "id": "id-value",
  "renameAs": "renameAs-value"
}
```

##### Response
Here is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "microsoft.graph.copysectionmodel"
} -->
```http
HTTP/1.1 202 Accepted
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