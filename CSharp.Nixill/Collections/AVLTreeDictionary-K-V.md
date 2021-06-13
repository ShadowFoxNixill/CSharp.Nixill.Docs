# Summary
This is an implementation of `IDictionary<K, V>` backed by an AVL tree.

- [Summary](#summary)
- [Remarks](#remarks)
- [Type parameters](#type-parameters)
- [Constructors](#constructors)
  - [`AVLTreeSet()`](#avltreeset)
  - [`AVLTreeSet(IComparer<K>)`](#avltreeseticomparerk)
  - [`AVLTreeSet(Comparison<T>)`](#avltreesetcomparisont)
  - [`AVLTreeSet(IEnumerable<KeyValuePair<K, V>>)`](#avltreesetienumerablekeyvaluepairk-v)
  - [`AVLTreeSet(IEnumerable<KeyValuePair<K, V>>, IComparer<K>)`](#avltreesetienumerablekeyvaluepairk-v-icomparerk)
  - [`AVLTreeSet(IEnumerable<KeyValuePair<K, V>>, Comparison<T>)`](#avltreesetienumerablekeyvaluepairk-v-comparisont)
- [Properties](#properties)
  - [`this[K]`](#thisk)
  - [`Count`](#count)
  - [`IsReadOnly`](#isreadonly)
  - [`Keys`](#keys)
  - [`Values`](#values)
- [Methods](#methods)
  - [`Add(K, V)`](#addk-v)
  - [`Add(KeyValuePair<K, V>)`](#addkeyvaluepairk-v)
  - [`CeilingEntry(K)`](#ceilingentryk)
  - [`CeilingKey(K)`](#ceilingkeyk)
  - [`Clear()`](#clear)
  - [`Contains(KeyValuePair<K, V>)`](#containskeyvaluepairk-v)
  - [`ContainsCeiling(K)`](#containsceilingk)
  - [`ContainsFloor(K)`](#containsfloork)
  - [`ContainsHigher(K)`](#containshigherk)
  - [`ContainsKey(K)`](#containskeyk)
  - [`ContainsLower(K)`](#containslowerk)
  - [`CopyTo(KeyValuePair<K, V>[], int)`](#copytokeyvaluepairk-v-int)
  - [`EntriesAround(K)`](#entriesaroundk)
  - [`FloorEntry(K)`](#floorentryk)
  - [`FloorKey(K)`](#floorkeyk)
  - [`GetEnumerator()`](#getenumerator)
  - [`HigherEntry(K)`](#higherentryk)
  - [`HigherKey(K)`](#higherkeyk)
  - [`HighestEntry()`](#highestentry)
  - [`HighestKey()`](#highestkey)
  - [`IsEmpty()`](#isempty)
  - [`KeysAround(K)`](#keysaroundk)
  - [`LowerEntry(K)`](#lowerentryk)
  - [`LowerKey(K)`](#lowerkeyk)
  - [`LowestEntry()`](#lowestentry)
  - [`LowestKey()`](#lowestkey)
  - [`Remove(K)`](#removek)
  - [`Remove(KeyValuePair<K, V>)`](#removekeyvaluepairk-v)
  - [`TryGetCeilingEntry(K, out KeyValuePair<K, V>)`](#trygetceilingentryk-out-keyvaluepairk-v)
  - [`TryGetCeilingKey(K, out K)`](#trygetceilingkeyk-out-k)
  - [`TryGetFloorEntry(K, out KeyValuePair<K, V>)`](#trygetfloorentryk-out-keyvaluepairk-v)
  - [`TryGetFloorKey(K, out K)`](#trygetfloorkeyk-out-k)
  - [`TryGetHigherEntry(K, out KeyValuePair<K, V>)`](#trygethigherentryk-out-keyvaluepairk-v)
  - [`TryGetHigherKey(K, out K)`](#trygethigherkeyk-out-k)
  - [`TryGetLowerEntry(K, out KeyValuePair<K, V>)`](#trygetlowerentryk-out-keyvaluepairk-v)
  - [`TryGetLowerKey(K, out K)`](#trygetlowerkeyk-out-k)
  - [`TryGetValue(K, out V)`](#trygetvaluek-out-v)
- [Explicit Interface Implementations](#explicit-interface-implementations)
  - [`IEnumerable.GetEnumerator()`](#ienumerablegetenumerator)



# Remarks
The `AVLTreeDictionary<K, V>` is backed by an `AVLTreeSet<K, V>` with a comparer that runs the given comparison function on two elements' keys, ignoring values.



# Type parameters
* **`K`**: The type of the keys stored in the dictionary.
* **`V`**: The type of the values stored in the dictionary.



# Constructors

## `AVLTreeSet()`
Initializes a new instance of the `AVLTreeSet` class, using the type's default `Comparer<K>`.

### Exceptions
* **`InvalidOperationException`**: The type isn't naturally comparable.


## `AVLTreeSet(IComparer<K>)`
Initializes a new instance of the `AVLTreeSet` class, using a specified `IComparer<K>`.

### Parameters
* `IComparer<K>` **`comparer`**: The comparer that compares the elements of the set.


## `AVLTreeSet(Comparison<T>)`
Initializes a new instance of the `AVLTreeSet` class, using a specified comparison function.

### Parameters
* `Comparison<K>` **`comparer`**: The function that compares the elements of the set.


## `AVLTreeSet(IEnumerable<KeyValuePair<K, V>>)`
Initializes a new instance of the `AVLTreeSet` class, using the type's default `Comparer<K>`.

### Parameters
* `IEnumerable<KeyValuePair<K, V>>` **`elems`**: The elements with which to pre-populate the set.

### Exceptions
* **`InvalidOperationException`**: The type isn't naturally comparable.


## `AVLTreeSet(IEnumerable<KeyValuePair<K, V>>, IComparer<K>)`
Initializes a new instance of the `AVLTreeSet` class, using a specified `IComparer<K>`.

### Parameters
* `IEnumerable<KeyValuePair<K, V>>` **`elems`**: The elements with which to pre-populate the set.
* `IComparer<K>` **`comparer`**: The comparer that compares the elements of the set.


## `AVLTreeSet(IEnumerable<KeyValuePair<K, V>>, Comparison<T>)`
Initializes a new instance of the `AVLTreeSet` class, using a specified comparison function.

### Parameters
* `IEnumerable<KeyValuePair<K, V>>` **`elems`**: The elements with which to pre-populate the set.
* `Comparison<K>` **`comparer`**: The function that compares the elements of the set.



# Properties


## `this[K]`
`V` - The element with the specified key.

### Parameters
* `K` **`key`**: The key of the element to get or set.

### Exceptions
* **`ArgumentNullException`**: key is `null`.
* **`KeyNotFoundException`**: The property is retrieved and key is not found.


## `Count`
`int` - The number of items contained in the `AVLTreeDictionary<K, V>`.


## `IsReadOnly`
`bool` - Whether or not this `AVLTreeDictionary<K, V>` is read-only (always `false`).


## `Keys`
`ICollection<K>` - An `ICollection<T>` containing the keys of the `AVLTreeDictionary<K, V>`.

The order of the keys in the returned `ICollection<K>` is smallest to largest.


## `Values`
`ICollection<V>` - An `ICollection<T>` containing the values of the `AVLTreeDictionary<K, V>`.

The order of the values in the returned `ICollection<V>` is the value of the smallest to largest keys.



# Methods


## `Add(K, V)`
`void` - Adds an entry with the given key and value to the `AVLTreeDictionary<K, V>`.

### Parameters
* `K` **`key`**: The key to use for the entry.
* `V` **`value`**: The value to use for the entry.

### Exceptions
* **`ArgumentNullException`**: `key` is `null`.
* **`ArgumentException`**: An entry already exists with the same key.


## `Add(KeyValuePair<K, V>)`
`void` - Adds the given entry to the `AVLTreeDictionary<K, V>`, potentially replacing any entry with the same key.

### Parameters
* `KeyValuePair<K, V>` **`entry`**: The entry to add to the dictionary.

### Exceptions
* **`ArgumentNullException`**: The 


## `CeilingEntry(K)`
`KeyValuePair<K, V>` - Gets the entry with the lowest key greater than or equal to a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentOutOfRangeException`**: No greater or equal key exists.
* **`ArgumentNullException`**: The given value is `null`.
* **`InvalidOperationException`**: The dictionary contains no elements.


## `CeilingKey(K)`
`K` - Gets the lowest key greater than or equal to a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentOutOfRangeException`**: No greater or equal key exists.
* **`ArgumentNullException`**: The given value is `null`.
* **`InvalidOperationException`**: The dictionary contains no elements.


## `Clear()`
`void` - Clears the dictionary.


## `Contains(KeyValuePair<K, V>)`
`bool` - Whether or not the dictionary contains an entry with the given key and value.

This method returns `true` iff an entry matches in *both* key and value. To check for just the key, use [`ContainsKey(K)`](#containskeyk).

### Parameters
* `KeyValuePair<K, V>` **`entry`**: The entry to check for presence in the dictionary.


## `ContainsCeiling(K)`
`bool` - Whether or not the `AVLTreeDictionary<K, V>` has a key that is greater than or equal to a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `ContainsFloor(K)`
`bool` - Whether or not the `AVLTreeDictionary<K, V>` has a key that is less than or equal to a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `ContainsHigher(K)`
`bool` - Whether or not the `AVLTreeDictionary<K, V>` has a key that is greater than a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `ContainsKey(K)`
`bool` - Whether or not the `AVLTreeDictionary<K, V>` has a key that is equal to a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `ContainsLower(K)`
`bool` - Whether or not the `AVLTreeDictionary<K, V>` has a key that is less than a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `CopyTo(KeyValuePair<K, V>[], int)`
`void` - Copies the entries of the dictionary to a one-dimensional array.

### Parameters
* `KeyValuePair<K, V>[]` **`array`**: The array to which to copy the entries.
* `int` **`index`**: The index at which to begin copying.

### Exceptions
* **`ArgumentOutOfRangeException`**: `index` is less than 0, or the array size plus `index` is less than the number of elements in the dictionary.
* **`NullReferenceException`**: `array` is `null`.


## `EntriesAround(K)`
`NodeTriplet<KeyValuePair<K, V>>` - Returns a `NodeTriplet` with the following entries, if they exist:

* The highest key less than the given value.
* The key equal to the given value.
* The lowest key greater than the given value.

### Parameters
* `K` **`from`**: The value to test.


## `FloorEntry(K)`
`KeyValuePair<K, V>` - Gets the entry with the highest key less than or equal to a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentOutOfRangeException`**: No lesser key exists.
* **`ArgumentNullException`**: The given value is `null`.
* **`InvalidOperationException`**: The dictionary contains no elements.


## `FloorKey(K)`
`K` - Gets the highest key less than or equal to a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentOutOfRangeException`**: No lesser key exists.
* **`ArgumentNullException`**: The given value is `null`.
* **`InvalidOperationException`**: The dictionary contains no elements.


## `GetEnumerator()`
`IEnumerator<KeyValuePair<K, V>>` - Returns an enumerator over the dictionary's entries.


## `HigherEntry(K)`
`KeyValuePair<K, V>` - Gets the entry with the lowest key greater than a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentOutOfRangeException`**: No greater key exists.
* **`ArgumentNullException`**: The given value is `null`.
* **`InvalidOperationException`**: The dictionary contains no elements.


## `HigherKey(K)`
`K` - Gets the lowest key greater than a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentOutOfRangeException`**: No greater key exists.
* **`ArgumentNullException`**: The given value is `null`.
* **`InvalidOperationException`**: The dictionary contains no elements.


## `HighestEntry()`
`KeyValuePair<K, V>` - Returns the entry with the highest key in the dictionary.

### Exceptions
* **`InvalidOperationExeption`**: The dictionary is empty.


## `HighestKey()`
`K` - Returns the highest key in the dictionary.

### Exceptions
* **`InvalidOperationExeption`**: The dictionary is empty.


## `IsEmpty()`
`bool` - Returns whether or not the `AVLTreeDictionary<K, V>` is empty.


## `KeysAround(K)`
`NodeTriplet<K>` - Returns a `NodeTriplet` with the following keys, if they exist:

* The highest key less than the given value.
* The key equal to the given value.
* The lowest key greater than the given value.

### Parameters
* `K` **`from`**: The value to test.


## `LowerEntry(K)`
`KeyValuePair<K, V>` - Gets the entry with the highest key less than a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentOutOfRangeException`**: No lesser key exists.
* **`ArgumentNullException`**: The given value is `null`.
* **`InvalidOperationException`**: The dictionary contains no elements.


## `LowerKey(K)`
`K` - Gets the highest key less than a given value.

### Parameters
* `K` **`from`**: The value to test.

### Exceptions
* **`ArgumentOutOfRangeException`**: No lesser key exists.
* **`ArgumentNullException`**: The given value is `null`.
* **`InvalidOperationException`**: The dictionary contains no elements.


## `LowestEntry()`
`KeyValuePair<K, V>` - Returns the entry with the lowest key in the dictionary.

### Exceptions
* **`InvalidOperationExeption`**: The dictionary is empty.


## `LowestKey()`
`K` - Returns the lowest key in the dictionary.

### Exceptions
* **`InvalidOperationExeption`**: The dictionary is empty.


## `Remove(K)`
`bool` - Removes the entry with the specified key from the dictionary, returning whether or not this method was successful. (A key not found will cause a return value of `false`.)

### Parameters
* `K` **`key`**: The key of the entry to remove.

### Exceptions
* **`ArgumentNullException`**: `key` is `null`.


## `Remove(KeyValuePair<K, V>)`
`bool` - Removes the entry with the speciied key and value from the dictionary, returning whether or not this method was successful.

Note that the method will only be successful if both the key and value match. To remove by key only, use [`Remove(K)`](#removek).

### Parameters
* `KeyValuePair<K, V>` **`entry`**: The entry to remove.

### Exceptions
* **`ArgumentNullException`**: `entry`'s key is `null`.


## `TryGetCeilingEntry(K, out KeyValuePair<K, V>)`
`bool` - Gets the entry with the lowest key greater than or equal to a given value, and returns whether or not such an entry exists.

### Parameters
* `K` **`from`**: The value to test.
* `out KeyValuePair<K, V>` **`value`**: When this method exits, this contains the entry with the higher or equal key, if such an entry exists. Otherwise, this contains an entry with the default values for the types.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `TryGetCeilingKey(K, out K)`
`bool` - Gets the lowest key greater than or equal to a given value, and returns whether or not such a key exists.

### Parameters
* `K` **`from`**: The value to test.
* `out K` **`value`**: When this method exits, this contains the higher or equal key, if such a key exists. Otherwise, this contains the default value for the key's type.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `TryGetFloorEntry(K, out KeyValuePair<K, V>)`
`bool` - Gets the entry with the highest key less than or equal to a given value, and returns whether or not such an entry exists.

### Parameters
* `K` **`from`**: The value to test.
* `out KeyValuePair<K, V>` **`value`**: When this method exits, this contains the entry with the lower or equal key, if such an entry exists. Otherwise, this contains an entry with the default values for the types.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `TryGetFloorKey(K, out K)`
`bool` - Gets the highest key less than or equal to a given value, and returns whether or not such a key exists.

### Parameters
* `K` **`from`**: The value to test.
* `out K` **`value`**: When this method exits, this contains the lower or equal key, if such a key exists. Otherwise, this contains the default value for the key's type.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `TryGetHigherEntry(K, out KeyValuePair<K, V>)`
`bool` - Gets the entry with the lowest key greater than a given value, and returns whether or not such an entry exists.

### Parameters
* `K` **`from`**: The value to test.
* `out KeyValuePair<K, V>` **`value`**: When this method exits, this contains the entry with the higher key, if such an entry exists. Otherwise, this contains an entry with the default values for the types.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `TryGetHigherKey(K, out K)`
`bool` - Gets the lowest key greater than a given value, and returns whether or not such a key exists.

### Parameters
* `K` **`from`**: The value to test.
* `out K` **`value`**: When this method exits, this contains the higher key, if such a key exists. Otherwise, this contains the default value for the key's type.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `TryGetLowerEntry(K, out KeyValuePair<K, V>)`
`bool` - Gets the entry with the highest key less than a given value, and returns whether or not such an entry exists.

### Parameters
* `K` **`from`**: The value to test.
* `out KeyValuePair<K, V>` **`value`**: When this method exits, this contains the entry with the lower key, if such an entry exists. Otherwise, this contains an entry with the default values for the types.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `TryGetLowerKey(K, out K)`
`bool` - Gets the highest key less than a given value, and returns whether or not such a key exists.

### Parameters
* `K` **`from`**: The value to test.
* `out K` **`value`**: When this method exits, this contains the lower key, if such a key exists. Otherwise, this contains the default value for the key's type.

### Exceptions
* **`ArgumentNullException`**: The given value is `null`.


## `TryGetValue(K, out V)`
`bool` - Get the value of the entry with the specified key, and returns whether or not such an entry exists.

### Parameters
* `K` **`key`**: The key to test.
* `out V` **`value`**: When this method exits, this contains the value from the entry with the given key, if such an entry exists. Otherwise, this contains the default value for the entry's type.

### Exceptions
* **`ArgumentNullException`**: `key` is `null`.



# Explicit Interface Implementations


## `IEnumerable.GetEnumerator()`
`IEnumerator` - Returns a typeless enumerator over the dictionary's entries.
