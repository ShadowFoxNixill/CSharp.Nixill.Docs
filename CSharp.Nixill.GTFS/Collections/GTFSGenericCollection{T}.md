```csharp
public class GTFSGenericCollection<T> : IReadOnlyCollection<T> where T : GTFSEntity
```

# Summary
Generic immutable collection of GTFS entities.



# Type Parameters
* **`T`** : `GTFSEntity`: The type of entity that this collection contains.



# Constructors


## `GTFSGenericCollection(IEnumerable<T>)`
Creates a new `GTFSGenericCollection` from the given existing collection of entities.

### Parameters
* `IEnumerable<T>` `objects`: The existing collection to copy.


## `GTFSGenericCollection(IGTFSDataSource, string, GTFSEntityFactory<T>)`
Creates a new `GTFSGenericCollection` from the given table in the given feed.

### Parameters
* `IGTFSDataSource` `source`: The data source from which to obtain the elements.
* `string` `tableName`: The table from which to obtain the elements.
* `GTFSEntityFactory<T>` `factory`: The method that creates objects from property collections.



# Properties


## `Count`
Read-only `int`: The number of entities within this collection.



# Methods


## `GetEnumerator()`
`IEnumerator<T>`: Returns an enumerator that iterates through a collection.


## `GetUnparsed()`
`IReadOnlyCollection<GTFSUnparsedEntity>`: Returns a read-only view of entities that couldn't be parsed.



# Explicit Interface Implementations


## `IEnumerable.GetEnumerator()`
`IEnumerator`: Returns an enumerator that iterates through a collection.