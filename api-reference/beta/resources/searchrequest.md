---
title: "searchRequest resource type"
description: "searchRequest "
localization_priority: Normal
author: "nmoreau"
ms.prod: "search"
doc_type: "resourcePageType"
---

# searchRequest resource type

The search request to be sent to the query endpoint. It contains the type of entities expected in the response, the underlying sources, the paging parameters, the fields request and the actual search query.

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|stored_fields|String collection|Contains the fields to be returned for earch _so urces object. Note this is only applicable when entityType=`microsoft.graph.externalItem`is specified in the response.|
|contentSources|String collection|Contains the Connection to be targetted. <br>It should respect the following format : `/external/connections/connectionid` where `connectionid` has been defined in the Connectors Administration <br> Note contentSource is only applicable when entityType=`microsoft.graph.externalItem`. |
|enableTopResults|Boolean|This will trigger relevance sorting for messages <br> This is only applicable for entityType=`microsoft.graph.message`|
|entityTypes|String collection| Possible values are: `microsoft.graph.event`, `microsoft.graph.message`, `microsoft.graph.driveItem`, `microsoft.graph.externalFile`, `microsoft.graph.externalItem`.|
|from|Int32|Specifies the offset for the search results. Offset 0 will returm the very first result|
|query|[searchQuery](searchquery.md)|contains the query terms|
|size|Int32|The size of the page to be retrieved.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.searchRequest",
  "baseType": null
}-->

```json
{
  "_sources": ["String"],
  "contentSources": ["String"],
  "enableTopResults": true,
  "entityType": "String",
  "entityTypes": ["String"],
  "from": 1024,
  "query": {"@odata.type": "microsoft.graph.searchQuery"},
  "size": 1024
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "searchRequest resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->