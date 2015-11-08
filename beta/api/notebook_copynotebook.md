# notebook: copyNotebook
Copies a notebook to the Notebooks folder in the destination Documents library. The folder is created if it doesn't exist.

### Prerequisites
One of the following **scopes** is required to execute this API:   
Notes.ReadWrite.CreatedByApp, Notes.ReadWrite, or Notes.ReadWrite.All 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /me/notes/notebooks/<id>/copyNotebook
GET /users/<mail>/notes/notebooks/<id>/copyNotebook
GET /users/<objectId>/notes/notebooks/<id>/copyNotebook
GET /groups/<objectId>/notes/notebooks/<id>/copyNotebook

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
|renameAs|String|The name of the copy. Defaults to the name of the existing item. |

<!--groupId missing-->
<!--|siteCollectionId|String||
|siteId|String||-->

### Response
If successful, this method returns `202 Accepted` response code and a [copyNotebookModel](../resources/copynotebookmodel.md) object in the response body.

### Example
Here is an example of how to call this API.
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "notebook_copynotebook"
}-->
```http
POST https://graph.microsoft.com/beta/users/<objectId>/notes/notebooks/<id>/copyNotebook
Content-type: application/json
Content-length: 110

{
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
  "@odata.type": "microsoft.graph.copynotebookmodel"
} -->
```http
HTTP/1.1 202 Accepted
Content-Type: application/json
Content-Length: 516

{
  "isDefault": true,
  "userRole": "userRole-value",
  "isShared": true,
  "sectionsUrl": "sectionsUrl-value",
  "sectionGroupsUrl": "sectionGroupsUrl-value",
  "links": {
    "oneNoteClientUrl": {
      "href": "href-value"
    },
    "oneNoteWebUrl": {
      "href": "href-value"
    }
  },
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
  "description": "notebook: copyNotebook",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->