```csharp
public class GTFSTwoPartEntity<TKey1, TKey2> : GTFSEntity
```

# Summary
A `GTFSEntity` with a two-part composite key.

- [Summary](#summary)
- [Type parameters](#type-parameters)
- [Constructors](#constructors)
  - [`GTFSTwoPartEntity(GTFSPropertyCollection, TKey1, TKey2)` (protected)](#gtfstwopartentitygtfspropertycollection-tkey1-tkey2-protected)
- [Properties](#properties)
  - [`FirstKey`](#firstkey)
  - [`SecondKey`](#secondkey)
  - [`this[string]`](#thisstring)
  - [`Properties` (protected)](#properties-protected)



# Type parameters
* **`TKey1`**: The type of the first key of this entity.
* **`TKey2`**: The type of the second key of this entity.



# Constructors


## `GTFSTwoPartEntity(GTFSPropertyCollection, TKey1, TKey2)` (protected)
Creates a new `GTFSTwoPartEntity`.

### Parameters
* `GTFSPropertyCollection` **`properties`**: The entity's collection of properties.
* `TKey1` **`firstKey`**: The first key of the entity.
* `TKey2` **`secondKey`**: The second key of the entity.



# Properties


## `FirstKey`
Read-only `TKey1`: The first key of the entity.

See the class definition for which property is the value of this key.


## `SecondKey`
Read-only `TKey2`: The second key of the entity.

See the class definition for which property is the value of this key.


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.