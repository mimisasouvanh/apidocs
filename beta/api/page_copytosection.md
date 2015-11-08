# page: copyToSection
Copies a page to a specific section.

### Prerequisites
One of the following **scopes** is required to execute this API:   
Notes.ReadWrite.CreatedByApp, Notes.ReadWrite, or Notes.ReadWrite.All  
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /me/notes/pages/<id>/copyToSection
POST /users/<mail>/notes/pages/<id>/copyToSection
POST /users/<objectId>/notes/pages/<id>/copyToSection
POST /groups/<objectId>/notes/pages/<id>/copyToSection
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
|id|String|The id of the destination section.|

<!--groupId missing-->
<!--|siteCollectionId|String||
|siteId|String||-->

### Response
If successful, this method returns `202 Accepted` response code and a [copyPageModel](../resources/copypagemodel.md) object in the response body.

### Example
Here is an example of how to call this API.
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "page_copytosection"
}-->
```http
POST https://graph.microsoft.com/beta/users/<objectId>/notes/pages/<id>/copyToSection
Content-type: application/json
Content-length: 98

{
  "id": "id-value"
}
```

##### Response
Here is an example of the response. <!--TEST no copy*Model in O365 implementation-->
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "microsoft.graph.copypagemodel"
} -->
```http
HTTP/1.1 202 Accepted
Content-Type: application/json
Content-Length: 1258

{
  "parentSection": {
    "isDefault": true,
    "pagesUrl": "pagesUrl-value",
    "name": "name-value",
    "createdBy": "createdBy-value",
    "lastModifiedBy": "lastModifiedBy-value",
    "lastModifiedTime": "datetime-value",
    "id": "id-value",
    "self": "self-value",
    "createdTime": "datetime-value"
  },
  "parentNotebook": {
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
  },
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
  "description": "page: copyToSection",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->