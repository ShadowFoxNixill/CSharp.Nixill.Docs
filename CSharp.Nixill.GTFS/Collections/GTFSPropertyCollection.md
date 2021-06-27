```csharp
public class IDEntityCollection<T> : IReadOnlyCollection<T> where T : GTFSIdentifiedEntity
```

# Summary
A collection of keys and values specified for a given GTFS Entity, representing a single row from a table.


- [Summary](#summary)
- [Remarks](#remarks)
- [Constructors](#constructors)
  - [`GTFSPropertyCollection(IDictionary<string, string>, string)`](#gtfspropertycollectionidictionarystring-string-string)
  - [`GTFSPropertyCollection(IEnumerable<(string, string)>, string)`](#gtfspropertycollectionienumerablestring-string-string)
- [Properties](#properties)
  - [`Count`](#count)
  - [`Keys`](#keys)
  - [`this[string]`](#thisstring)
  - [`Values`](#values)
- [Methods](#methods)
  - [`ContainsKey(string)`](#containskeystring)
  - [`GetEnumerator()`](#getenumerator)
  - [`TryGetValue(string, out string)`](#trygetvaluestring-out-string)
- [Explicit Interface Implementations](#explicit-interface-implementations)
  - [`IEnumerable.GetEnumerator()`](#ienumerablegetenumerator)



# Remarks
This class is similar to a read-only `Dictionary<string, string>`, except that values of `null` or `""` are ignored and their keys discarded. Additionally, attempting to read the value of a key that doesn't exist simply returns `null` rather than throwing an exception.



# Constructors

## `GTFSPropertyCollection(IDictionary<string, string>, string)`
Creates a new `GTFSPropertyCollection` from a dictionary of keys and values.

### Parameters
* `IDictionary<string, string>` **`input`**: The dictionary to use.
* `string` **`agencyID`** (default `null`): The default `agency_id` to use. If specified, and there's no `agency_id` key in the input, this value will be used for that key.


## `GTFSPropertyCollection(IEnumerable<(string, string)>, string)`
Creates a new `GTFSPropertyCollection` from an enumerable set of two-string tuples.

### Parameters
* `IEnumerable<(string, string)>` **`input`**: The keys and values to use.
* `string` **`agencyID`** (default `null`): The default `agency_id` to use. If specified, and there's no `agency_id` key in the input, this value will be used for that key.



# Properties


## `Count`
Read-only `int`: The number of key-value pairs in the collection.

This may be lower than the `Count` of the input collection, as values that were `null` or the empty string were discarded.


## `Keys`
Read-only `IEnumerable<string>`: An enumerable set of the keys of the collection.

Keys whose values were `null` or the empty string are not included.


## `this[string]`
Read-only `string`: The property with the specified key.

If the key wasn't in the input data, or its value was `null` or the empty string, `null` is returned.


## `Values`
Read-only `IEnumerable<string>`: Returns an enumerable set of the values of the collection.

Values which were `null` or the empty string are not included.



# Methods


## `ContainsKey(string)`
`bool`: Whether or not this collection contains a key with the given name.

This method may return `false` for keys that had been in the input collection, iff their values were `null` or empty string.

### Parameters
* `string` **`key`**: The key to check.


## `GetEnumerator()`
`IEnumerator<KeyValuePair<string, string>>`: Returns an iterator over the key-value pairs in this collection.

Key-value pairs where the value is `null` or empty string are not included.


## `TryGetValue(string, out string)`
`bool`: Attempts to get the value associated with the specified key.

This method may return `false` for keys that had been in the input collection, iff their values were `null` or empty string.

### Parameters:
* `string` **`key`**: The key to check.
* `out string` **`value`**: When this method returns, if the key was found, this variable contains the value for that key. Otherwise, it contains `null`.



# Explicit Interface Implementations


## `IEnumerable.GetEnumerator()`
`IEnumerator`: Returns an enumerator that iterates through a collection.