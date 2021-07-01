```csharp
public class IDEntityCollection<T> : IReadOnlyCollection<T> where T : GTFSIdentifiedEntity
```

# Summary
A collection of `GTFSIdentifiedEntity`s, accessible by their IDs.

- [Summary](#summary)
- [Type Parameters](#type-parameters)
- [Constructors](#constructors)
  - [`IDEntityCollection(IEnumerable<T>)`](#identitycollectionienumerablet)
  - [`IDEntityCollection(IGTFSDataSource, string, GTFSEntityFactory<T>)`](#identitycollectionigtfsdatasource-string-gtfsentityfactoryt)
- [Properties](#properties)
  - [`Count`](#count)
  - [`this[string]`](#thisstring)
- [Methods](#methods)
  - [`Contains(T)`](#containst)
  - [`GetEnumerator()`](#getenumerator)
  - [`GetUnparsed()`](#getunparsed)
- [Explicit Interface Implementations](#explicit-interface-implementations)
  - [`IEnumerable.GetEnumerator()`](#ienumerablegetenumerator)



# Type Parameters
* **`T`** : `GTFSIdentifiedEntity`: The type of entity that this collection contains.



# Constructors


## `IDEntityCollection(IEnumerable<T>)`
Creates a new `IDEntityCollection` from the given existing collection of entities.

### Parameters
* `IEnumerable<T>` `objects`: The existing collection to copy.


## `IDEntityCollection(IGTFSDataSource, string, GTFSEntityFactory<T>)`
Creates a new IDEntityCollection from the given table in the given feed.

### Parameters
* `IGTFSDataSource` `source`: The data source from which to obtain the elements.
* `string` `tableName`: The table from which to obtain the elements.
* `GTFSEntityFactory<T>` `factory`: The method that creates objects from property collections.



# Properties


## `Count`
Read-only `int`: The number of entities within this collection.


## `this[string]`
Read-only `T`: The entity with this key, if the collection contains one. Otherwise, this returns `null`.



# Methods


## `Contains(T)`
Returns `true` iff the collection contains the given entity.

More specifically, this is `true` iff the collection has a key that matches the given entity's ID.

### Parameters
* `T` **`item`**: The item for which to check.


## `GetEnumerator()`
`IEnumerator<T>`: Returns an enumerator that iterates through a collection.


## `GetUnparsed()`
`IReadOnlyCollection<GTFSUnparsedEntity>`: Returns a read-only view of entities that couldn't be parsed.



# Explicit Interface Implementations


## `IEnumerable.GetEnumerator()`
`IEnumerator`: Returns an enumerator that iterates through a collection.