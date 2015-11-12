# item resource type

The **item** resource represents an item contained in a drive, like a file or folder. The properties of an item provide information about the type of item represented. 
For example, if an item behaves as a [folder](folder.md), it will have the **folder** property set to an instance of the folder resource that contains details about the folder.

### JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "children",
    "createdByUser",
    "lastModifiedByUser",
    "permissions",
    "thumbnails",
    "versions"
  ],
  "@odata.type": "microsoft.graph.item"
}-->

```json
{
  "audio": {
    "@odata.type": "microsoft.graph.audio"
  },
  "cTag": "String-value",
  "children": [
    {
      "@odata.type": "microsoft.graph.item"
    }
  ],
  "content": "Stream-value",
  "createdBy": {
    "@odata.type": "microsoft.graph.identityset"
  },
  "createdByUser": {
    "@odata.type": "microsoft.graph.user"
  },
  "createdDateTime": "String (timestamp)",
  "deleted": {
    "@odata.type": "microsoft.graph.deleted"
  },
  "description": "String-value",
  "eTag": "String-value",
  "file": {
    "@odata.type": "microsoft.graph.file"
  },
  "fileSystemInfo": {
    "@odata.type": "microsoft.graph.filesysteminfo"
  },
  "folder": {
    "@odata.type": "microsoft.graph.folder"
  },
  "id": "String-value (identifier)",
  "image": {
    "@odata.type": "microsoft.graph.image"
  },
  "lastModifiedBy": {
    "@odata.type": "microsoft.graph.identityset"
  },
  "lastModifiedByUser": {
    "@odata.type": "microsoft.graph.user"
  },
  "lastModifiedDateTime": "String (timestamp)",
  "location": {
    "@odata.type": "microsoft.graph.location"
  },
  "name": "String-value",
  "parentReference": {
    "@odata.type": "microsoft.graph.itemreference"
  },
  "permissions": [
    {
      "@odata.type": "microsoft.graph.permission"
    }
  ],
  "photo": {
    "@odata.type": "microsoft.graph.photo"
  },
  "searchResult": {
    "@odata.type": "microsoft.graph.searchresult"
  },
  "size": 1024,
  "specialFolder": {
    "@odata.type": "microsoft.graph.specialfolder"
  },
  "thumbnails": [
    {
      "@odata.type": "microsoft.graph.thumbnailset"
    }
  ],
  "versions": [
    {
      "@odata.type": "microsoft.graph.item"
    }
  ],
  "video": {
    "@odata.type": "microsoft.graph.video"
  },
  "webUrl": "String-value"
}

```
### Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|audio|[audio](audio.md)|Audio metadata, if the item is an audio file. Read-only. |
|cTag|String|An eTag for the content of the item. This eTag is not changed if only the metadata is changed. **Note** This property is not returned if the item is a folder. Read-only. |
|content|Stream|The content stream, if the item represents a file. |
|createdBy|[identitySet](identityset.md)|Identity of the user, device, and application which created the item. Read-only. |
|createdDateTime|DateTimeOffset|Date and time of item creation. Read-only.|
|deleted|[deleted](deleted.md)| Information about the deleted state of the item. Read-only.|
|description|String|Provide a user-visible description of the item. Read-write. |
|eTag|String|eTag for the entire item (metadata + content). Read-only. |
|file|[file](file.md)|File metadata, if the item is a file. Read-only. |
|fileSystemInfo|[fileSystemInfo](filesysteminfo.md)|File system information on client. Read-write. |
|folder|[folder](folder.md)|Folder metadata, if the item is a folder. Read-only. |
|id|String|The unique identifier of the item within the Drive. Read-only. |
|image|[image](image.md)|Image metadata, if the item is an image. Read-only. |
|lastModifiedBy|[identitySet](identityset.md)|Identity of the user, device, and application which last modified the item. Read-only. |
|lastModifiedDateTime|DateTimeOffset|Date and time the item was last modified. Read-only. |
|location|[location](location.md)|Location metadata, if the item has location data. Read-only. |
|name|String|The name of the item (filename and extension). Read-write. |
|parentReference|[itemReference](itemreference.md)|Parent information, if the item has a parent. Read-write. |
|photo|[photo](photo.md)|Photo metadata, if the item is a photo. Read-only. |
|searchResult|[searchResult](searchresult.md)|Search metadata, if the item is from a search result. |
|size|Int64|Size of the item in bytes. Read-only. |
|specialFolder|[specialFolder](specialfolder.md)||
|video|[video](video.md)|Video metadata, if the item is a video. Read-only. |
|webUrl|String|URL that displays the resource in the browser. Read-only. |

**Note:** The eTag and cTag properties work differently on containers (folders). The cTag value is modified when content or metadata of any descendant of the folder is changed. The eTag value is only modified when the folder's properties are changed, except for properties that are derived from descendants (like childCount or lastModifiedDateTime).

### Instance Attributes

Instance attributes are properties with special behaviors. This properties are temporary and either a) define behavior the service should perform or b) provide short-term property values, like a download URL for an item that expires.

|Property name	|Type	|Description|
|:--------------|:-----|:----------|
|@name.conflictBehavior	|string	|The conflict resolution behavior for actions that create a new item. An item will never be returned with this annotation. Write-only.|
|@content.downloadUrl	|string	|A Url that can be used to download this file's content. Authentication is not required with this URL. Read-only.|
|@content.sourceUrl	|string	|When issuing a PUT request, this instance annotation can be used to instruct the service to download the contents of the URL, and store it as the file. Write-only.|

**Note:** The @content.downloadUrl is a short-lived URL and can't be cached. The URL will only be available for a short period of time before it is invalidated.

### Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|children|[item](item.md) collection|Collection containing Item objects for the immediate children of Item. Only items representing folders have children. Read-only. Nullable.|
|createdByUser|[user](user.md)| Identity of the user, device, and application which created the item. Read-only.|
|lastModifiedByUser|[user](user.md)| Identity of the user, device, and application which last modified the item. Read-only.|
|permissions|[permission](permission.md) collection| The set of permissions for the item. Read-only. Nullable.|
|thumbnails|[thumbnailSet](thumbnailset.md) collection|Collection containing [ThumbnailSet](thumbnailSet.md) objects associated with the item. For more info, see [getting thumbnails](../items/thumbnails.md). Read-only. Nullable.|
|versions|[item](item.md) collection|A list of items containing the previous versions. Read-only. Nullable.|

### Methods

| Method		                                           | Return Type                                |Description                                                                             |
|:-----------------------------------------------------|:-------------------------------------------|:---------------------------------------------------------------------------------------|
| [Get item](../api/item_get.md)                       | [item](item.md)                            | Read properties and relationships of item object.                                      |
| [Create item](../api/item_post_children.md)          | [item](item.md)                            | Create a new item by posting to the children collection.                               |
| [List children](../api/item_list_children.md)        | [item](item.md) collection                 | Get a children object collection.                                                      |
| [Create permission](../api/item_post_permissions.md) | [permission](permission.md)                | Create a new permission by posting to the permissions collection.                      |
| [List permissions](../api/item_list_permissions.md)  | [permission](permission.md) collection     | Get a permission object collection.                                                    |
| [List thumbnails](../api/item_list_thumbnails.md)    | [thumbnailSet](thumbnailset.md) collection | Get a thumbnailSet object collection.                                                  |
| [update](../api/item_update.md)                      | [item](item.md)                            | Update item object.                                                                    |
| [delete](../api/item_delete.md)                      | None                                       | Delete item object.                                                                    |
| [copy](../api/item_copy.md)                          | [item](item.md)                            | Copy an item to another location in the drive.                                         |
| [createLink](../api/item_createlink.md)              | [permission](permission.md)                | Create a sharing link to allow users to access the content without signing in.         |
| [invite](../api/item_invite.md)                      | [permission](permission.md) collection     | Invite users to access the item by adding permissions and sending them a notification. |
| [search](../api/item_search.md)                      | [item](item.md) collection                 | Search for items matching a query.                                                     |


**Note:** In OneDrive for Business, the cTag property is not returned, if the item is a folder.
 
<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "item resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
