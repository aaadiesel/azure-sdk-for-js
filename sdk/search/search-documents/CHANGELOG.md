# Release History

## 1.0.0-preview.4 (2020-06-08)

- [Breaking] Changed `ListIndexes` operation to a pageable operation.
- [Breaking] Added `onlyIfUnchanged` parameter for CreateOrUpdate and Delete operations.
- [Breaking] Removed `$select` property for the List operations.
- [Breaking] Refactored `SearchServiceClient` and split it to `SearchIndexClient` and `SearchIndexerClient` and changed `SearchIndexClient` class to `SearchClient` class.
- [Breaking] Moved non-optional parameters from options bag.
- [Breaking] Renamed `countDocuments` method to `getDocumentsCount` method.
- [Breaking] In `search` method, moved the `searchText` parameter from the options bag to method parameter. 
- [Breaking] In `indexDocuments` method, the options parameter is renamed to `IndexDocumentsOptions`.
- [Breaking] Modified `deleteDocuments` method to get documents as a parameter.
- [Breaking] In `getIndexStatistics` method, renamed the return type from `GetIndexStatisticsResult` to `SearchIndexStatistics`.
- [Breaking] In `getServiceStatistics` method, renamed the return type from `ServiceStatistics` to `SearchServiceStatistics`.
- [Breaking] Modified `DataSource` model name to `DataSourceConnection`. Changed all references in the method names, parameters, etc.
- [Breaking] Renamed `SimpleDataType` model to `SearchFieldDataType` model.
- [Breaking] Modified the names of several models & parameters. Please refer [#8984](https://github.com/Azure/azure-sdk-for-js/issues/8984), [#9037](https://github.com/Azure/azure-sdk-for-js/issues/9037) and [#8383](https://github.com/Azure/azure-sdk-for-js/issues/8383) for a detailed list of renames.
- Added separate methods for getting just names such as `listIndexesNames`, `listSynonymMapsNames`, etc.
- Added `getSearchClient` method to the `SearchIndexClient` class.

## 1.0.0-preview.3 (2020-05-05)

- Added support for Indexers API (Create, Get, List, etc.)
- Added support for Datasources API.(Create, Get, List, etc.)
- Fixed a bug where GeographyPoints were serialized incorrectly causing latitude and longitude to be flipped.

## 1.0.0-preview.2 (2020-04-06)

- [Breaking] Package renamed to `@azure/search-documents` and version number reset to `1.0.0-preview.2`.
- Support for index management operations using the `SearchServiceClient`.
- [Breaking] `indexDocuments` on `SearchIndexClient` now takes an `IndexDocumentsBatch` object instead of a raw action array. This new type helps compose an array of actions to be performed on the index.
- [Breaking] In `SearchIndexClient`, removed options `mergeIfExists` and `uploadIfNotExists` on `uploadDocuments` and `mergeDocuments` and replaced them with new helper `mergeOrUploadDocuments`.
- The type `IndexAction` was renamed to `IndexDocumentsAction`.
- [Breaking] Removed `SearchApiKeyCredential` and replaced with `AzureKeyCredential`.
- [Breaking] Search results accessed `byPage` now have an opaque `continuationToken` in place of `nextLink` and `nextPageParameters`.

## 11.0.0-preview.1 (2020-03-09)

- Initial implementation of the data-plane Cognitive Search Client. The version number starts at 11 to align with client libraries in other languages.
- This first preview has support for document operations on an index, such as querying and document management.
