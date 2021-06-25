```csharp
public class GTFSUnparsedEntity : GTFSEntity
```

# Summary
An entity that did not conform to its type's requirements and therefore failed to parse.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`GTFSUnparsedEntity(GTFSPropertyCollection, Exception)` (protected)](#gtfsunparsedentitygtfspropertycollection-exception-protected)
- [Properties](#properties)
  - [`Exception`](#exception)
  - [`this[string]`](#thisstring)
  - [`Properties` (protected)](#properties-protected)



# Constructors


## `GTFSUnparsedEntity(GTFSPropertyCollection, Exception)` (protected)
Creates a new `GTFSUnparsedEntity`.

### Parameters
* `GTFSPropertyCollection` **`properties`**: The entity's collection of properties.
* `Exception` **`ex`**: The exception which caused the entity to fail parsing.



# Properties


## `Exception`
Read-only `Exception`: The exception which caused the entity to fail parsing.


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.