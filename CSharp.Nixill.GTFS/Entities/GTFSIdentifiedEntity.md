```csharp
public abstract class GTFSIdentifiedEntity : GTFSEntity
```

# Summary
A `GTFSEntity` with a simple, identifier-based primary key.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`GTFSIdentifiedEntity(GTFSPropertyCollection, string)` (protected)](#gtfsidentifiedentitygtfspropertycollection-string-protected)
- [Properties](#properties)
  - [`ID`](#id)
  - [`this[string]`](#thisstring)
  - [`Properties` (protected)](#properties-protected)



# Constructors


## `GTFSIdentifiedEntity(GTFSPropertyCollection, string)` (protected)
Creates a `GTFSIdentifiedEntity`.

### Parameters
* `GTFSPropertyCollection` **`properties`**: The entity's collection of properties.
* `string` **`idName`**: The key of the property that identifies this entity.



# Properties


## `ID`
Read-only `string`: The ID of the entity.

See the class definition for which property is the value of this property.


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.