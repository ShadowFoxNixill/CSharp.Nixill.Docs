```csharp
public interface IGTFSDataSource
```

# Summary
Interface for GTFS data sources.

- [Summary](#summary)
- [Methods](#methods)
  - [`GetObjects<T>(string, GTFSEntityFactory<T>, List<GTFSUnparsedEntity>)`](#getobjectststring-gtfsentityfactoryt-listgtfsunparsedentity)



# Methods


## `GetObjects<T>(string, GTFSEntityFactory<T>, List<GTFSUnparsedEntity>)`
`IEnumerable<T>`: Returns an enumerable collection of objects parsed from the given table in the data source.

### Type parameters
* **`T`** (: `GTFSEntity`): The type of entities created from the requested table.

### Parameters
* `string` **`table`**: The table being requested from the data source.
* `GTFSEntityFactory<T>` **`factory`**: The method that turns properties into objects.
* `List<GTFSUnparsedEntity>` **`unparsed`** (default `null`): If provided, a list where entities that throw an exceptio nduring parsing are stored. If not provided, any generated exceptions are thrown.