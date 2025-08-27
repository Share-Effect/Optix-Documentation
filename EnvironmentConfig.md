# Environment Configuration

This document outlines the settings available in the environment configuration.

## Table of Contents
- [`EnvironmentConfig`](#environmentconfig)
- [`EnvironmentType`](#environmenttype)
- [`EntityConfig`](#entityconfig)
- [`SaveLocationReference`](#savelocationreference)
- [`CaseListReference`](#caselistreference)
- [`TaskListReference`](#tasklistreference)
- [`DropOffLocation`](#dropofflocation)
- [`SearchScope`](#searchscope)
- [`LifeCycleListReference`](#lifecyclelistreference)
- [`KnowledgeBaseSite`](#knowledgebasesite)
- [`Datasource`](#datasource)
- [`ListReference`](#listreference)
- [`App`](#app)
- [`Link`](#link)
- [`CustomAction`](#customaction)
- [`CustomSearchResultRefiner`](#customsearchresultrefiner)
- [`DatasourceDisplayField`](#datasourcedisplayfield)
- [`AssignedToMeOptions`](#assignedtomeoptions)
- [`LinkedSharePointItems`](#linkedsharepointitems)
- [`LifeCycleItemAction`](#lifecycleitemaction)
- [`returnedProperty`](#returnedproperty)
- [`DatasourceLookupField`](#datasourcelookupfield)
- [`DatasourceRelation`](#datasourcerelation)
- [`LifeCycleItemActionType`](#lifecycleitemactiontype)
- [`ListContenttypeReference`](#listcontenttypereference)
- [`ListItemReference`](#listitemreference)

---

<a name="environmentconfig"></a>
## `EnvironmentConfig`
The main configuration object for the environment.

| Property | Type | Description |
|---|---|---|
| `id` | `string` | Unique identifier for the environment. |
| `tenantId` | `string` | The ID of the tenant. |
| `environmentId` | `string` | The Power Platform environment ID. |
| `environmentType` | [`EnvironmentType`](#environmenttype) | The type of environment (Production or Sandbox). |
| `administrators` | `string[]` | A list of administrator user IDs. |
| `domainName` | `string` | The domain name of the tenant. |
| `productName` | `string` (optional) | The name of the product to display. |
| `productDescription` | `string` (optional) | The description of the product to display. |
| `entities` | [`EntityConfig[]`](#entityconfig) | Configuration for data entities. |
| `documentLibraries` | [`SaveLocationReference[]`](#savelocationreference) | Document libraries to save new documents to. |
| `caseLists` | [`CaseListReference[]`](#caselistreference) | Lists that contain cases. |
| `taskLists` | [`TaskListReference[]`](#tasklistreference) | Lists that contain tasks. |
| `dropOffLocations` | [`DropOffLocation[]`](#dropofflocation) | Specific locations for document drop-off. |
| `searchScopes` | [`SearchScope[]`](#searchscope) | Defines search scopes for the homepage. |
| `lifeCycleLists` | [`LifeCycleListReference[]`](#lifecyclelistreference) | Lists for lifecycle management. |
| `knowdledgeBaseSites` | [`KnowledgeBaseSite[]`](#knowledgebasesite) | Sites that act as knowledge bases. |
| `settings` | `any` (optional) | General settings for the application. |
| `theme` | `any` (optional) | Theme for the application. |

<a name="environmenttype"></a>
## `EnvironmentType`
Enum for the environment type.

| Value | Description |
|---|---|
| `Production` | A production environment. |
| `Sandbox` | A sandbox or test environment. |

<a name="entityconfig"></a>
## `EntityConfig`
Configuration for a single data entity.

| Property | Type | Description |
|---|---|---|
| `id` | `string` | Unique identifier for the entity. |
| `name` | `string` | The name of the entity. |
| `pluralName` | `string` (optional) | The plural name of the entity. |
| `icon` | `string` | The icon to represent the entity. |
| `color` | `string` | The color associated with the entity. |
| `datasource` | [`Datasource`](#datasource) (optional) | The primary data source for this entity. |
| `infoLists` | [`ListReference[]`](#listreference) | References to lists containing additional information. |
| `noteLists` | [`ListReference[]`](#listreference) | References to lists for notes. |
| `caseLists` | [`ListReference[]`](#listreference) | References to lists for cases related to this entity. |
| `documentLibraries` | [`SaveLocationReference[]`](#savelocationreference) | Locations where documents for this entity can be saved. |
| `apps` | [`App[]`](#app) | Power Apps associated with this entity. |
| `links` | [`Link[]`](#link) | Useful links related to this entity. |
| `documentTemplateLibraries` | [`ListReference[]`](#listreference) (optional) | Libraries containing document templates. |
| `customActions` | [`CustomAction[]`](#customaction) (optional) | Custom actions available for this entity. |
| `customSearchResultRefiners` | [`CustomSearchResultRefiner[]`](#customsearchresultrefiner) (optional) | Custom refiners for search results. |
| `customSearchResultFields` | [`DatasourceDisplayField[]`](#datasourcedisplayfield) (optional) | Custom fields to display in search results. |
| `settings` | `any` (optional) | Entity-specific settings. |

<a name="savelocationreference"></a>
## `SaveLocationReference`
Reference to a location (document library) where documents can be saved.

| Property | Type | Description |
|---|---|---|
| `groupId` | `string` | The ID of the SharePoint group (site). |
| `listId` | `string` | The ID of the document library. |
| `hideAddButton` | `boolean` (optional) | If true, hides the 'Add' button in the UI. |
| `customActions` | [`CustomAction[]`](#customaction) (optional) | Custom actions for this save location. |

<a name="caselistreference"></a>
## `CaseListReference`
Reference to a SharePoint list that contains cases.

| Property | Type | Description |
|---|---|---|
| `groupId` | `string` | The ID of the SharePoint group (site). |
| `listId` | `string` | The ID of the case list. |
| `AssignedToMeOptions` | [`AssignedToMeOptions`](#assignedtomeoptions) | Options for the 'Assigned to Me' view. |
| `powerAppId` | `string` (optional) | The ID of a Power App to use for this case list. |
| `linkedSharePointItems` | [`LinkedSharePointItems[]`](#linkedsharepointitems) (optional) | Defines linked SharePoint items. |
| `caseClosedStatusses` | `string[]` (optional) | A list of statuses that are considered 'closed'. |
| `titlePrefix` | `string` (optional) | A prefix for the title of new cases. |

<a name="tasklistreference"></a>
## `TaskListReference`
Reference to a SharePoint list that contains tasks.

| Property | Type | Description |
|---|---|---|
| `groupId` | `string` | The ID of the SharePoint group (site). |
| `listId` | `string` | The ID of the task list. |
| `powerAppId` | `string` (optional) | The ID of a Power App to use for this task list. |

<a name="dropofflocation"></a>
## `DropOffLocation`
A specific location for document drop-off.

| Property | Type | Description |
|---|---|---|
| `groupId` | `string` | The ID of the SharePoint group (site). |
| `listId` | `string` | The ID of the drop-off library. |

<a name="searchscope"></a>
## `SearchScope`
Defines a scope for search operations.

| Property | Type | Description |
|---|---|---|
| `scopeId` | `string` | A unique ID for the search scope. |
| `groupIds` | `string[]` | The SharePoint group IDs to include in the scope. |
| `query` | `string` | The search query string. |
| `title` | `string` | The title of the search scope. |
| `description` | `string` | A description of the search scope. |
| `customSearchResultRefiners` | [`CustomSearchResultRefiner[]`](#customsearchresultrefiner) (optional) | Custom refiners for search results. |
| `customSearchResultFields` | [`DatasourceDisplayField[]`](#datasourcedisplayfield) (optional) | Custom fields to display in search results. |

<a name="lifecyclelistreference"></a>
## `LifeCycleListReference`
Reference to a list for lifecycle management.

| Property | Type | Description |
|---|---|---|
| `groupId` | `string` | The ID of the SharePoint group (site). |
| `listId` | `string` | The ID of the lifecycle list. |
| `actions` | [`LifeCycleItemAction[]`](#lifecycleitemaction) | Actions available for items in this list. |

<a name="knowledgebasesite"></a>
## `KnowledgeBaseSite`
A site that acts as a knowledge base.

| Property | Type | Description |
|---|---|---|
| `siteId` | `string` | The ID of the SharePoint site. |

<a name="datasource"></a>
## `Datasource`
Defines a data source for an entity.

| Property | Type | Description |
|---|---|---|
| `id` | `string` | Unique identifier for the datasource. |
| `type` | `string` | The type of the datasource (e.g., 'sharepoint', 'dataverse'). |
| `primary` | `boolean` | Whether this is the primary datasource for the entity. |
| `searchProperty` | `string` | The main identifier for a record in the external source. |
| `returnedProperties` | [`returnedProperty[]`](#returnedproperty) | Properties returned for searching and auto-filling fields. |
| `groupId` | `string` (optional) | SharePoint group ID. |
| `listId` | `string` (optional) | SharePoint list ID. |
| `entityName` | `string` (optional) | Dataverse entity name. |
| `displayProperty` | `string` (optional) | Property to display for Graph Connector results. |
| `connectionId` | `string` (optional) | Graph Connector connection ID. |
| `fields` | [`DatasourceDisplayField[]`](#datasourcedisplayfield) (optional) | Fields for Dataverse and Graph Connector. |
| `lookupFields` | [`DatasourceLookupField[]`](#datasourcelookupfield) (optional) | Lookup fields for Dataverse. |
| `relations` | [`DatasourceRelation[]`](#datasourcerelation) (optional) | Relationships to other datasources. |
| `itemsQuery` | `string` (optional) | Custom query for retrieving items. |

<a name="listreference"></a>
## `ListReference`
A generic reference to a SharePoint list.

| Property | Type | Description |
|---|---|---|
| `groupId` | `string` | The ID of the SharePoint group (site). |
| `listId` | `string` | The ID of the list. |

<a name="app"></a>
## `App`
A Power App associated with an entity.

| Property | Type | Description |
|---|---|---|
| `title` | `string` | The title of the app. |
| `description` | `string` (optional) | A description of the app. |
| `icon` | `string` | The icon for the app. |
| `color` | `string` (optional) | A color associated with the app. |
| `powerAppId` | `string` | The ID of the Power App. |

<a name="link"></a>
## `Link`
A useful link related to an entity.

| Property | Type | Description |
|---|---|---|
| `title` | `string` | The title of the link. |
| `description` | `string` (optional) | A description of the link. |
| `iconUrl` | `string` (optional) | The URL of an icon for the link. |
| `color` | `string` (optional) | A color associated with the link. |
| `url` | `string` | The URL of the link. |

<a name="customaction"></a>
## `CustomAction`
A custom action that can be performed.

| Property | Type | Description |
|---|---|---|
| `type` | `number` | The type of the action. |
| `title` | `string` | The title of the action. |
| `icon` | `string` | The icon for the action. |
| `powerAppId` | `string` | The ID of a Power App to launch for the action. |

<a name="customsearchresultrefiner"></a>
## `CustomSearchResultRefiner`
A custom refiner for search results.

| Property | Type | Description |
|---|---|---|
| `managedProperty` | `string` | The managed property to use for refining. |
| `displayName` | `string` (optional) | The display name for the refiner. |

<a name="datasourcedisplayfield"></a>
## `DatasourceDisplayField`
A field to display from a datasource.

| Property | Type | Description |
|---|---|---|
| `fieldName` | `string` | The name of the field. |
| `fieldDisplayName` | `string` | The name to display for the field. |

<a name="assignedtomeoptions"></a>
## `AssignedToMeOptions`
Options for the 'Assigned to Me' view.

| Property | Type | Description |
|---|---|---|
| `viewId` | `string` | The ID of the SharePoint list view. |

<a name="linkedsharepointitems"></a>
## `LinkedSharePointItems`
Defines linked SharePoint items.

| Property | Type | Description |
|---|---|---|
| `fieldName` | `string` | The name of the field. |
| `uploadLocation` | [`ListContenttypeReference`](#listcontenttypereference) | The location to upload documents to. |
| `documentTemplate` | [`ListItemReference`](#listitemreference) | A template for the document. |
| `AvailableInStatuses` | `string[]` (optional) | Statuses in which this is available. |

<a name="lifecycleitemaction"></a>
## `LifeCycleItemAction`
An action for a lifecycle list item.

| Property | Type | Description |
|---|---|---|
| `title` | `string` | The title of the action. |
| `description` | `string` | A description of the action. |
| `type` | [`LifeCycleItemActionType`](#lifecycleitemactiontype) | The type of the action. |
| `actionUrl` | `string` | The URL to execute for the action. |

<a name="returnedproperty"></a>
## `returnedProperty`
A property returned from a datasource search.

| Property | Type | Description |
|---|---|---|
| `returnProperty` | `string` | The property to return. |
| `autoFillFieldNames` | `string[]` (optional) | Fields to auto-fill with this property's value. |
| `managedProperty` | `string` | The corresponding managed property. |
| `value` | `any` (optional) | The value of the property. |

<a name="datasourcelookupfield"></a>
## `DatasourceLookupField`
A lookup field in a datasource.

| Property | Type | Description |
|---|---|---|
| `fieldName` | `string` | The name of the lookup field. |

<a name="datasourcerelation"></a>
## `DatasourceRelation`
A relationship between datasources.

| Property | Type | Description |
|---|---|---|
| `id` | `string` | A unique ID for the relation. |
| `property` | `string` | The property that defines the relationship. |
| `datasourceId` | `string` | The ID of the related datasource. |
| `type` | `string` (optional) | The type of the relationship. |
| `searchProperty` | `string` (optional) | The property to search on in the related datasource. |
| `entityName` | `string` (optional) | The entity name of the related datasource. |

<a name="lifecycleitemactiontype"></a>
## `LifeCycleItemActionType`
Enum for the lifecycle item action type.

| Value | Description |
|---|---|
| `Delete` | A delete action. |
| `Action` | A generic action. |

<a name="listcontenttypereference"></a>
## `ListContenttypeReference`
A reference to a content type within a list.

| Property | Type | Description |
|---|---|---|
| `groupId` | `string` | The ID of the SharePoint group (site). |
| `listId` | `string` | The ID of the list. |
| `contentTypeId` | `string` | The ID of the content type. |

<a name="listitemreference"></a>
## `ListItemReference`
A reference to a specific list item.

| Property | Type | Description |
|---|---|---|
| `webUrl` | `string` | The URL of the SharePoint web. |
| `listId` | `string` | The ID of the list. |
| `listItemId` | `number` | The ID of the list item. |
