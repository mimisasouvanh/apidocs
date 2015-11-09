# Update page

Update the content of a OneNote page.
### Prerequisites
One of the following **scopes** is required to execute this API:   
Notes.ReadWrite.CreatedByApp, Notes.ReadWrite, or Notes.ReadWrite.All 
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
PATCH /me/notes/pages/<id>
PATCH /users/<mail>/notes/pages/<id>
PATCH /users/<objectId>/notes/pages/<id>
PATCH /groups/<objectId>/notes/pages/<id>
```
### Optional request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | `Bearer <token>` A valid OAuth token provided to the app based on the user credentials and the user having authorized access. |
| Content-Type | string | `application/json` |

### Request body
In the request body, supply an array of [patchContentCommand](../resources/patchcontentcommand.md) objects that represent the changes to the page. For more information and examples, see <a href="https://msdn.microsoft.com/en-us/office/office365/howto/onenote-update-page">Update OneNote pages</a>.

### Response
If successful, this method returns a `204 No Content` response code.  No JSON data is returned for a PATCH request.
### Example
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "update_page"
}-->
```http
PATCH https://graph.microsoft.com/beta/users/<objectId>/notes/pages/<id>
Content-Type: application/json
Content-Length: 391

[
   {
    'target':'#para-id',
    'action':'insert',
    'position':'before',
    'content':'<img src="image-url-or-part-name" alt="image-alt-text" />'
  }, 
  {
    'target':'#list-id',
    'action':'append',
    'content':'<li>new-page-content</li>'
  }
]
```

##### Response
Here is an example of the response. No JSON data is returned for a PATCH request.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "microsoft.graph.page"
} -->
```http
HTTP/1.1 204 No Content
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update page",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->