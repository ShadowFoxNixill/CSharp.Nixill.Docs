```csharp
public class FareRule : GTFSEntity
```

# Summary
A single fare rule.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`GTFSEntity(GTFSPropertyCollection)` (protected)](#gtfsentitygtfspropertycollection-protected)
- [Properties](#properties)
  - [`ContainsID`](#containsid)
  - [`DestinationID`](#destinationid)
  - [`FareID`](#fareid)
  - [`OriginID`](#originid)
  - [`RouteID`](#routeid)
  - [`this[string]`](#thisstring)
  - [`Properties` (protected)](#properties-protected)



# Constructors


## `GTFSEntity(GTFSPropertyCollection)` (protected)
Creates a new `GTFSEntity`.

### Parameters
* `GTFSPropertyCollection` **`properties`**: The entity's collection of properties.



# Properties


## `ContainsID`
Read-only `string`: Identifies the zones that a rider will enter while using a given fare class.

This is the value of the `contains_id` property of the entity.


## `DestinationID`
Read-only `string`: Identifies the destination fare zone.

This is the value of the `destination_id` property of the entity. If a class has multiple destination zones, a `FareRule` would exist for each zone.


## `FareID`
Read-only `string`: Identifies the fare class to which this record applies.

This is the value of the `fare_id` property of the entity.


## `OriginID`
Read-only `string`: Identifies the origin fare zone.

This is the value of the `origin_id` property of the entity. If a class has multiple origin zones, a `FareRule` would exist for each zone.


## `RouteID`
Read-only `string`: Identifies the route to which this fare class applies.

This is the value of the `route_id` property of the entity. If multiple routes apply, a `FareRule` would exist for each route.


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.