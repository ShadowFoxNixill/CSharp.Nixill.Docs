```csharp
public class ZipGTFSDataSource : IGTFSDataSource
```

# Summary
An `IGTFSDataSource` using a zip archive as its backend.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`ZipGTFSDataSource(ZipArchive)`](#zipgtfsdatasourceziparchive)
  - [`ZipGTFSDataSource(string)`](#zipgtfsdatasourcestring)
- [Methods](#methods)
  - [`GetObjects<T>(string, GTFSEntityFactory<T>, [List<GTFSUnparsedEntity>])`](#getobjectststring-gtfsentityfactoryt-listgtfsunparsedentity)



# Constructors


## `ZipGTFSDataSource(ZipArchive)`
Creates a `ZipGTFSDataSource` using an existing `ZipArchive` object.

### Parameters
* `ZipArchive` **`archive`**: The archive to use.


## `ZipGTFSDataSource(string)`
Creates a `ZipGTFSDataSource` using a new `ZipArchive` object referring to `archiveName`.

### Parameters
* `string` **`archiveName`**: The name of the archive to use.



# Methods


## `GetObjects<T>(string, GTFSEntityFactory<T>, [List<GTFSUnparsedEntity>])`
`IEnumerable<T>`: Returns an enumerable collection of objects parsed from the given table in the data source.

### Type parameters
* **`T`** (: `GTFSEntity`): The type of entities created from the requested table.

### Parameters
* `string` **`table`**: The table being requested from the data source.
* `GTFSEntityFactory<T>` **`factory`**: The method that turns properties into objects.
* `List<GTFSUnparsedEntity>` **`unparsed`** (optional): If provided, a list where entities that throw an exceptio nduring parsing are stored. If not provided, any generated exceptions are thrown.