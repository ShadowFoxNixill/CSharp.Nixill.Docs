```csharp
public abstract class GTFSOrderedEntity : GTFSTwoPartEntity<string, int>
```

# Summary
A `GTFSEntity` with a two-part composite key.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`GTFSOrderedEntity(GTFSPropertyCollection, string, string)` (protected)](#gtfsorderedentitygtfspropertycollection-string-string-protected)
- [Properties](#properties)
  - [`FirstKey`](#firstkey)
  - [`ID`](#id)
  - [`Index`](#index)
  - [`SecondKey`](#secondkey)
  - [`this[string]`](#thisstring)
  - [`Properties` (protected)](#properties-protected)



# Constructors


## `GTFSOrderedEntity(GTFSPropertyCollection, string, string)` (protected)
Creates a new `GTFSOrderedEntity`.

### Parameters
* `GTFSPropertyCollection` **`properties`**: The entity's collection of properties.
* `string` **`idKey`**: Which property is the ID of the entity.
* `int` **`indexKey`**: Which property is the index of the entity.



# Properties


## `FirstKey`
Read-only `string`: The ID of the entity.

See the class definition for which property is the value of this key.


## `ID`
Read-only `string`: The ID of the entity.

See the class definition for which property is the value of this key.


## `Index`
Read-only `int`: The index of the entity.

See the class definition for which property is the value of this key.


## `SecondKey`
Read-only `int`: The index of the entity.

See the class definition for which property is the value of this key.


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.