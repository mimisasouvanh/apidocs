# assignLicense


### Prerequisites
One of the following **scopes** is required to execute this API: 
*User.ReadWrite.All; Directory.ReadWrite.All*
### HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /users/<objectId>/Microsoft.Graph.assignLicense
POST /users/<userPrincipalName>/Microsoft.Graph.assignLicense
```
### Request headers
| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer %token%  |
| Content-Type  | application/json  |

### Request body
In the request body, provide a JSON object with the following parameters.

| Parameter	   | Type	|Description|
|:---------------|:--------|:----------|
|addLicenses|AssignedLicense|A collection of [AssignedLicense](../resources/assignedlicense.md) objects that specify the licenses to add. You can disable plans associated with a license by setting the **disabledPlans** property on an [AssignedLicense](../resources/assignedlicense.md) object.|
|removeLicenses|Guid|A collection of GUIDs that identify the licenses to remove.|

### Response
If successful, this method returns `200, OK` response code and [User](../resources/user.md) object in the response body.

### Example
Here is an example of how to call this API.
##### Request
Here is an example of the request.
<!-- {
  "blockType": "request",
  "name": "user_assignlicense"
}-->
```http
POST https://graph.microsoft.com/v1.0/users/<objectId>/Microsoft.Graph.assignLicense
Content-type: application/json

{
  "id": "id-value",
  "addLicenses": [
    {
      "disabledPlans": [
        "disabledPlans-value"
      ],
      "skuId": "skuId-value"
    }
  ],
  "removeLicenses": [
    "removeLicenses-value"
  ]
}
```

##### Response
Here is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": false,
  "@odata.type": "microsoft.graph.user"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "accountEnabled": true,
  "assignedLicenses": [
    {
      "disabledPlans": [
        "disabledPlans-value"
      ],
      "skuId": "skuId-value"
    }
  ],
  "assignedPlans": [
    {
      "assignedTimestamp": "datetime-value",
      "capabilityStatus": "capabilityStatus-value",
      "service": "service-value",
      "servicePlanId": "servicePlanId-value"
    }
  ],
  ...
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "user: assignLicense",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->