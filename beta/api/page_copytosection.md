# page: copyToSection
Copies a page to a specific section.

### Prerequisites
One of the following **scopes** is required to execute this API:   
Notes.ReadWrite.CreatedByApp, Notes.ReadWrite, or Notes.ReadWrite.All  
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /me/notes/pages/<id>/Microsoft.Graph.copyToSection
POST /users/<mail>/notes/pages/<id>/Microsoft.Graph.copyToSection
POST /users/<objectId>/notes/pages/<id>/Microsoft.Graph.copyToSection
POST /groups/<objectId>/notes/pages/<id>/Microsoft.Graph.copyToSection
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
|id|String|The id of the destination section.|


### Response
If successful, this method returns a `202 Accepted` response code.

### Example
Here is an example of how to call this API.
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "page_copytosection"
}-->
```http
POST https://graph.microsoft.com/beta/users/<objectId>/notes/pages/<id>/Microsoft.Graph.copyToSection
Content-Type: application/json
Content-Length: 28

{
  "id": "id-value"
}
```

##### Response
Here is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "microsoft.graph.copypagemodel"
} -->
```http
HTTP/1.1 202 Accepted
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "page: copyToSection",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->