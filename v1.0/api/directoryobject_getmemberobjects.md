# directoryObject: getMemberObjects
Call the **getMemberObjects** function on a user, contact, group to get the groups **and** directory roles that it is a member of. The function is transitive. 

**Note**: The maximum number of groups and directory roles that can be returned is 2046. If the target object has direct or transitive membership in more than 2046 groups and directory roles, the function returns an HTTP error response with an error code of _Directory_ResultSizeLimitExceeded_.

### Prerequisites
The following **scopes** are required to execute this API: _Group.Read.All_ OR _Group.ReadWrite.All_
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /users/<id>/Microsoft.Graph.Microsoft.Graph.getMemberObjects
POST /groups/<id>/Microsoft.Graph.Microsoft.Graph.getMemberObjects
POST /contacts/<id>/Microsoft.Graph.getMemberObjects

```
### Request headers
| Name       | Type | Description|
|:---------------|:--------|:----------|
| X-Sample-Header  | string  | Sample HTTP header. Update accordingly or remove if not needed|

### Request body
In the request body, provide a JSON object with the following parameters.

| Parameter	   | Type	|Description|
|:---------------|:--------|:----------|
|securityEnabledOnly|Boolean||

### Response
If successful, this method returns `200, OK` response code and String collection object in the response body.

### Example
Here is an example of how to call this API.
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "directoryobject_getmemberobjects"
}-->
```http
POST https://graph.microsoft.com/v1.0/users/<id>/Microsoft.Graph.getMemberObjects
Content-type: application/json
Content-length: 33

{
  "securityEnabledOnly": true
}
```

##### Response
Here is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "string",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 39

{
  "value": [
    "String-value"
  ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "directoryObject: getMemberObjects",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->