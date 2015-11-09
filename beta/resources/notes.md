# notes resource type

The entry point for OneNote resources.

All calls to the OneNote service through the Microsoft Graph API use this service root URL:

```
https://graph.microsoft.com/<version>/<context>/notes/ 
```

OneNote support is in preview, so the version is always `beta`. 

Only user and group contexts are supported. Accessing SharePoint site notebooks is currently not supported. Choosing the permission scopes your app should request depends both on the context and your app's functionality. 

**User notebooks**

To access OneNote notebooks that are owned by a user, use one of the following service root URLs:

```
https://graph.microsoft.com/beta/me/notes/ (current user)
https://graph.microsoft.com/beta/users/<mail>/notes/
https://graph.microsoft.com/beta/users/<objectId>/notes/
```

The following permission scopes apply to user-context routes:

|Scope|Permission|Description|
|:------|:------|:------|
| Notes.Create | Create pages in OneNote notebooks | Can view the titles of your notebooks and sections; create new pages in any location. Cannot view or edit existing pages. |  
| Notes.ReadWrite.CreatedByApp | Application-only OneNote notebook access | Can view the titles of your notebooks and sections; create new pages; view and modify pages created by the app. Cannot view or modify pages created by other apps or in password protected sections. |  
| Notes.Read | View OneNote notebooks | Can view the contents of your notebooks and sections. Cannot create new pages; modify existing pages; access password protected sections. |  
| Notes.ReadWrite | View and modify OneNote notebooks | Can view the titles of your notebooks and sections; view and modify all your pages; create new pages. Cannot access password protected sections. |  


**Group notebooks**

To access OneNote notebooks that are owned by a group, use the following service root URL:

```
https://graph.microsoft.com/beta/groups/<objectId>/notes/
```

The following permission scopes apply to the group-context route:

|Scope|Permission|Description|
|:------|:------|:------|
| Notes.Read.All | Read all groups | Can read all group properties and memberships; read group calendar and conversations on public groups and groups the signed in user is a member of. |  
| Notes.ReadWrite.All | Read and write all groups | Can create groups on behalf of the signed-in user and read all group properties and memberships; update group properties and memberships for groups the signed-in user owns; read and write group calendar and conversations on public groups and groups the signed-in user is a member of. |  
| Group.Read |  |  |
| Group.Write |  |  |
| Group.Read.All | Read all groups | Can read all group properties and memberships; read group calendar and conversations on public groups and groups the signed in user is a member of. | 
| Group.ReadWrite.All | Read and write all groups | Can create groups on behalf of the signed-in user and read all group properties and memberships; update group properties and memberships for groups the signed-in user owns; read and write group calendar and conversations on public groups and groups the signed-in user is a member of. | 


<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "notebooks",
    "pages",
    "resources",
    "sectionGroups",
    "sections"
  ],
  "@odata.type": "microsoft.graph.notes"
}-->

### Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|notebooks|[Notebook](notebook.md) collection|The collection of OneNote notebooks that are owned by the user or group. Read-only. Nullable.|
|pages|[Page](page.md) collection|The pages in all OneNote notebooks that are owned by the user or group.  Read-only. Nullable.|
|resources|[Resource](resource.md) collection |The image and other file resources in OneNote pages. Getting a resources collection is not supported, but you can [get the binary content of a specific resource](resource.md). Read-only. Nullable.|
|sectionGroups|[SectionGroup](sectiongroup.md) collection|The section groups in all OneNote notebooks that are owned by the user or group.  Read-only. Nullable.|
|sections|[Section](section.md) collection|The sections in all OneNote notebooks that are owned by the user or group.  Read-only. Nullable.|


### Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Create notebook](../api/notes_post_notebooks.md) |[Notebook](notebook.md)| Create a notebook by posting to the notebooks collection.|
|[List notebooks](../api/notes_list_notebooks.md) |[Notebook](notebook.md) collection| Get a collection of notebooks.|
|[Create page](../api/notes_post_pages.md) |[Page](page.md)| Create a page by posting to the pages collection.|
|[List pages](../api/notes_list_pages.md) |[Page](page.md) collection| Get a collection of pages.|
|[List sectionGroups](../api/notes_list_sectiongroups.md) |[SectionGroup](sectiongroup.md) collection| Get a collection of section groups.|
|[List sections](../api/notes_list_sections.md) |[Section](section.md) collection| Get a collection of sections.|

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "notes resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->