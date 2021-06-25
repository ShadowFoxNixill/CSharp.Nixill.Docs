```csharp
public class TwoKeyEntityCollection<TEntity, TKey1, TKey2> : IReadOnlyCollection<TEntity> where TEntity : GTFSTwoPartEntity<TKey1, TKey2>
```

# Summary
A collection of `GTFSTwoPartEntity`s, accessible by their combined keys.

- [Summary](#summary)
- [Remarks](#remarks)
- [Type Parameters](#type-parameters)
- [Constructors](#constructors)
  - [`TwoKeyEntityCollection(IEnumerable<TEntity>)`](#twokeyentitycollectionienumerabletentity)
  - [`TwoKeyEntityCollection(IGTFSDataSource, string, GTFSEntityFactory<TEntity>)`](#twokeyentitycollectionigtfsdatasource-string-gtfsentityfactorytentity)
- [Properties](#properties)
  - [`Count`](#count)
  - [`FirstKeys`](#firstkeys)
  - [`SecondKeys`](#secondkeys)
  - [`this[TKey1, TKey2]`](#thistkey1-tkey2)
- [Methods](#methods)
  - [`Contains(T)`](#containst)
  - [`Contains(TEntity)`](#containstentity)
  - [`Contains((TKey1, TKey2))`](#containstkey1-tkey2)
  - [`GetEnumerator()`](#getenumerator)
  - [`GetUnparsed()`](#getunparsed)
  - [`WithFirstKey(TKey1)`](#withfirstkeytkey1)
  - [`WithSecondKey(TKey2)`](#withsecondkeytkey2)
- [Explicit Interface Implementations](#explicit-interface-implementations)
  - [`IEnumerable.GetEnumerator()`](#ienumerablegetenumerator)



# Remarks
If C# ever makes inferrable type params, this type will be Obsoleted and replaced with `TwoKeyEntityCollection<TEntity>`.



# Type Parameters
* **`TEntity`** (: `GTFSTwoPartEntity<TKey1, TKey2>`): The type of entity that this collection contains.
* **`TKey1`**: The type of `TEntity`'s first key.
* **`TKey2`**: The type of `TEntity`'s second key.



# Constructors


## `TwoKeyEntityCollection(IEnumerable<TEntity>)`
Creates a new `TwoKeyEntityCollection` from the given existing collection of entities.

### Parameters
* `IEnumerable<TEntity>` `objects`: The existing collection to copy.


## `TwoKeyEntityCollection(IGTFSDataSource, string, GTFSEntityFactory<TEntity>)`
Creates a new TwoKeyEntityCollection from the given table in the given feed.

### Parameters
* `IGTFSDataSource` `source`: The data source from which to obtain the elements.
* `string` `tableName`: The table from which to obtain the elements.
* `GTFSEntityFactory<TEntity>` `factory`: The method that creates objects from property collections.



# Properties


## `Count`
Read-only `int`: The number of entities within this collection.


## `FirstKeys`
Read-only `IEnumerable<TKey1>`: The collection of distinct first keys.


## `SecondKeys`
Read-only `IEnumerable<TKey2>`: The collection of distinct second keys.


## `this[TKey1, TKey2]`
Read-only `TEntity`: The entity with the given pair of keys.

If no such entity exists, returns `null`.



# Methods


## `Contains(T)`
Returns `true` iff the collection contains the given entity.

More specifically, this is `true` iff the collection has a key that matches the given entity's ID.

### Parameters
* `T` **`item`**: The item for which to check.


## `Contains(TEntity)`
`bool`: Returns `true` iff the collection contains the given entity.

More specifically, this is `true` iff the collection has a pair of keys that matches the given entity's keys.

### Parameters
* `TEntity` **`item`**: The item to check for.


## `Contains((TKey1, TKey2))`
`bool`: Returns `true` iff the collection contains the pair of keys.

### Parameters
* `(TKey1, TKey2)` **`key`**: The keys to check for.


## `GetEnumerator()`
`IEnumerator<T>`: Returns an enumerator that iterates through a collection.


## `GetUnparsed()`
`IReadOnlyCollection<GTFSUnparsedEntity>`: Returns a read-only view of entities that couldn't be parsed.


## `WithFirstKey(TKey1)`
`IEnumerable<TEntity>`: Returns the subset of this collection containing entities with the given first key.

If no such entities exist, the iterator will yield no results.

### Parameters
* `TKey1` **`key`**: The key to check for.


## `WithSecondKey(TKey2)`
`IEnumerable<TEntity>`: Returns the subset of this collection containing entities with the given second key.

If no such entities exist, the iterator will yield no results.

### Parameters
* `TKey2` **`key`**: The key to check for.



# Explicit Interface Implementations


## `IEnumerable.GetEnumerator()`
`IEnumerator`: Returns an enumerator that iterates through a collection.