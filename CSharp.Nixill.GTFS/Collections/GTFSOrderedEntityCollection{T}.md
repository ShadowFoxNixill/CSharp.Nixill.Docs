```csharp
  public class GTFSOrderedEntityCollection<T> : IReadOnlyCollection<T> where T : GTFSOrderedEntity
```



# Summary
A GTFS feed table whose members are sequential elements to some entity.

- [Summary](#summary)
- [Remarks](#remarks)
- [Type Parameters](#type-parameters)
- [Constructors](#constructors)
  - [`GTFSOrderedEntityCollection(IEnumerable<T>)`](#gtfsorderedentitycollectionienumerablet)
  - [`GTFSOrderedEntityCollection(IGTFSDataSource, string, GTFSEntityFactory<T>)`](#gtfsorderedentitycollectionigtfsdatasource-string-gtfsentityfactoryt)
- [Properties](#properties)
  - [`Count`](#count)
  - [`this[string]`](#thisstring)
  - [`this[string, int]`](#thisstring-int)
- [Methods](#methods)
  - [`Contains(T)`](#containst)
  - [`Contains((string, int))`](#containsstring-int)
  - [`Contains(string)`](#containsstring)
  - [`ContainsCeiling((string, int))`](#containsceilingstring-int)
  - [`ContainsFloor((string, int))`](#containsfloorstring-int)
  - [`ContainsHigher((string, int))`](#containshigherstring-int)
  - [`ContainsLower((string, int))`](#containslowerstring-int)
  - [`GetEnumerator()`](#getenumerator)
  - [`GetUnparsed()`](#getunparsed)
- [Explicit Interface Implementations](#explicit-interface-implementations)
  - [`IEnumerable.GetEnumerator()`](#ienumerablegetenumerator)



# Remarks
GTFS Standard examples are the stop times along a route or the points along a shape.



# Type Parameters
* `T : GTFSOrderedEntity`: The type of element contained within the collection.



# Constructors


## `GTFSOrderedEntityCollection(IEnumerable<T>)`
Creates a new `GTFSOrderedEntityCollection` from the given existing collection of entities.

### Parameters
* `IEnumerable<T>` `objects`: The existing collection to copy.


## `GTFSOrderedEntityCollection(IGTFSDataSource, string, GTFSEntityFactory<T>)`
Creates a new `GTFSOrderedEntityCollection` from the given table in the given source.

### Parameters
* `IGTFSDataSource` `source`: The data source from which to obtain the elements.
* `string` `tableName`: The table from which to obtain the elements.
* `GTFSEntityFactory<T>` `factory`: The method that creates objects from property collections.



# Properties


## `Count`
Read-only `int`: The number of elements within this collection.


## `this[string]`
Read-only `IReadOnlyNavigableDictionary<int, T>`: Returns the whole list of elements with the given entity ID, if any exist. Otherwise, `null` is returned.


## `this[string, int]`
Read-only `T`: From the entity with the given ID, this property returns the element with the highest index equal to or less than the given index. If there is no such entity or index, this returns `null`.



# Methods


## `Contains(T)`
`bool`: Returns `true` iff the collection contains the given element.

More specifically, this returns `true` iff the collection has an element with a matching entity ID and index.

### Parameters
* `T` **`item`**: The item whose existence should be verified.


## `Contains((string, int))`
`bool`: Returns `true` iff the collection contains a matching key.

### Parameters
* `(string, int)` **`key`**: The key whose existence should be verified.


## `Contains(string)`
`bool`: Returns `true` iff the collection contains a given entity.

More specifically, this returns `true` iff the collection has any elements with a matching entity ID.

### Parameters
* `string` **`key`**: The entity ID whose existence should be verified.


## `ContainsCeiling((string, int))`
`bool`: Returns `true` iff the collection contains a key higher than or equal to the given key.

More specifically, this returns `true` iff the collection has any elements with a matching entity ID and a higher or equal index.

### Parameters
* `(string, int)` **`key`**: The key to check from.


## `ContainsFloor((string, int))`
`bool`: Returns `true` iff the collection contains a key lower than or equal to the given key.

More specifically, this returns `true` iff the collection has any elements with a matching entity ID and a lower or equal index.

### Parameters
* `(string, int)` **`key`**: The key to check from.


## `ContainsHigher((string, int))`
`bool`: Returns `true` iff the collection contains a key higher than the given key.

More specifically, this returns `true` iff the collection has any elements with a matching entity ID and a higher index.

### Parameters
* `(string, int)` **`key`**: The key to check from.


## `ContainsLower((string, int))`
`bool`: Returns `true` iff the collection contains a key lower than the given key.

More specifically, this returns `true` iff the collection has any elements with a matching entity ID and a lower index.

### Parameters
* `(string, int)` **`key`**: The key to check from.


## `GetEnumerator()`
`IEnumerator<T>`: Returns an enumerator that iterates through a collection.


## `GetUnparsed()`
`IReadOnlyCollection<GTFSUnparsedEntity>`: Returns a read-only view of entities that couldn't be parsed.



# Explicit Interface Implementations


## `IEnumerable.GetEnumerator()`
`IEnumerator`: Returns an enumerator that iterates through a collection.