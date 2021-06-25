```csharp
public abstract class GTFSEntity
```

# Summary
A single entity from a GTFS feed.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`GTFSEntity(GTFSPropertyCollection)` (protected)](#gtfsentitygtfspropertycollection-protected)
- [Properties](#properties)
  - [`this[string]`](#thisstring)
  - [`Properties` (protected)](#properties-protected)



# Constructors


## `GTFSEntity(GTFSPropertyCollection)` (protected)
Creates a new `GTFSEntity`.

### Parameters
* `GTFSPropertyCollection` **`properties`**: The entity's collection of properties.



# Properties


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.