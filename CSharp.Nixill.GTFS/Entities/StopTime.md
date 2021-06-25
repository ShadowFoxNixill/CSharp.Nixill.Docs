```csharp
public abstract class GTFSOrderedEntity : GTFSTwoPartEntity<string, int>
```

# Summary
Represents a single instance of a trip serving a stop.

- [Summary](#summary)
- [Properties](#properties)
  - [`ArrivalTime`](#arrivaltime)
  - [`ContinuousDropoff`](#continuousdropoff)
  - [`ContinuousPickup`](#continuouspickup)
  - [`DepartureTime`](#departuretime)
  - [`DropoffType`](#dropofftype)
  - [`FirstKey`](#firstkey)
  - [`Headsign`](#headsign)
  - [`ID`](#id)
  - [`Index`](#index)
  - [`PickupType`](#pickuptype)
  - [`SecondKey`](#secondkey)
  - [`ShapeDistTraveled`](#shapedisttraveled)
  - [`StopID`](#stopid)
  - [`StopSequence`](#stopsequence)
  - [`this[string]`](#thisstring)
  - [`Timepoint`](#timepoint)
  - [`TripID`](#tripid)
  - [`Properties` (protected)](#properties-protected)
- [Methods](#methods)
  - [`Factory(IEnumerable<(string, string)>)` (static)](#factoryienumerablestring-string-static)



# Properties


## `ArrivalTime`
Read-only `Duration?`: Arrival time at this stop.

This is the value of the `arrival_time` property of the entity.

For times occurring after midnight on the service day, the time is a value greater than `24:00:00` in `HH:mm:ss` local time for the day on which the trip schedule begins.

Scheduled stops where the vehicle strictly adheres to the specified arrival and departure times are timepoints. If this stop is not a timepoint, it is recommended for feed producers  to provide an estimated or interpolated time. If this is not available, <c>ArrivalTime</c> may be left empty. Further, feed producers should indicate that interpolated times are provided with <C>Timepoint == false</c>. If interpolated times are indicated with <c>Timepoint == false</c>, then time points must be indicated with <c>Timepoint == true</c>. Feed producers should provide arrival times for all stops that are time points. An arrival time must be specified for the first and the last stop in a trip.


## `ContinuousDropoff`
Read-only `PickupDropoffType`: Indicates whether a rider can alight from the transit vehicle at any point along the vehicle’s travel path.

This is the value of the <c>continuous_drop_off</c> property of the entity, and defaults to the `Route`'s `ContinuousDropoff` value (which itself defaults to `PickupDropoffType.Unavailable`). The path is described by <c>Shapes</c>, from this <c>StopTime</c> to the next <c>StopTime</c> in the trip’s <c>StopSequence</c>. The continuous drop-off behavior indicated in <c>StopTime</c>s overrides any behavior defined in <see cref="Route" />s.


## `ContinuousPickup`
Read-only `PickupDropoffType`: Indicates whether a rider can board the transit vehicle at any point along the vehicle’s travel path.

This is the value of the <c>continuous_pickup</c> property of the entity, and defaults to the `Route`'s `ContinuousPickup` value (which itself defaults to `PickupDropoffType.Unavailable`). The path is described by <c>Shapes</c>, from this <c>StopTime</c> to the next <c>StopTime</c> in the trip’s <c>StopSequence</c>. The continuous pickup behavior indicated in <c>StopTime</c>s overrides any behavior defined in <see cref="Route" />s.


## `DepartureTime`
Read-only `Duration?`: Departure time from this stop.

This is the value of the `departure_time` property of the entity. All other remarks applicable to `ArrivalTime` also apply here.


## `DropoffType`
Read-only `PickupDropoffType`: Indicates drop-off method.

This is the value of the `drop_off_type` property of the entity, and defaults to `PickupDropoffType.Available`.


## `FirstKey`
Read-only `string`: The ID of the entity.

This is the value of the `trip_id` property of the entity.


## `Headsign`
Read-only `string`: Text that appears on signage identifying the trip's destination to riders.

This is the value of the <c>stop_headsign</c> property of the entity.

This field overrides the default <see cref="Trip.Headsign" /> when the headsign changes between stops. If the headsign is displayed for an entire trip, use <c>Trip.Headsign</c> instead.

A <c>Headsign</c> value specified for one <c>StopTime</c> does not apply to subsequent <c>StopTime</c>s in the same trip. If you want to override the <c>Trip.Headsign</c> for multiple <c>StopTime</c>s in the same trip, the <c>Headsign</c> value must be repeated in each <c>StopTime</c>.


## `ID`
Read-only `string`: The ID of the entity.

This is the value of the `trip_id` property of the entity.


## `Index`
Read-only `int`: The index of the entity.

This is the value of the `stop_sequence` property of the entity.


## `PickupType`
Read-only `PickupDropoffType`: Indicates pickup method.

This is the value of the `pickup_type` property of the entity, and defaults to `PickupDropoffType.Available`.


## `SecondKey`
Read-only `int`: The index of the entity.

This is the value of the `stop_sequence` property of the entity.


## `ShapeDistTraveled`
Read-only `decimal?`: Actual distance traveled along the associated shape, from the start of the shape to the stop specified in this record.

This is the value of the <c>shape_dist_traveled</c> property of the entity. This field specifies how much of the shape to draw between any two stops during a trip. Must be in the same units used in <c>Shapes</c>. Values used for <c>ShapeDistTraveled</c> must increase along with <c>StopSequence</c>; they cannot be used to show reverse travel along a route.

For example, if this <c>StopTime</c> is 5.25 km from the start of the shape, and the shape's distances are in kilometers, this property would have a value of <c>5.25</c>.


## `StopID`
Read-only `string`: The stop that is served at this point along the route.

This is the value of the `stop_id` property of the entity.

All stops serviced during a trip must have a <c>StopTime</c> record. Referenced locations must be stops (`Stop.LocationType == StopLocationType.StopPlatform`), not stations or station entrances. A stop may be serviced multiple times in the same trip, and multiple trips and routes may service the same stop.


## `StopSequence`
Read-only `int`: The order in which this stop is served along the trip.

This is the value of the `stop_sequence` property of the entity, and is its `SecondKey` and `Index`. The values must increase aong the trip but do not need to be consecutive.

The first location on the trip could have a `StopSequence` of `1`, the second location `23`, the third location `40`, and so on.


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `Timepoint`
Read-only `bool`: Indicates if arrival and departure times for a stop are strictly adhered to by the vehicle or if they are instead approximate and/or interpolated times.

This is the value of the <c>timepoint</c> field of the entity, specifically whether or not it has a value of `1`. This field allows a GTFS producer to provide interpolated stop-times, while indicating that the times are approximate. 


## `TripID`
Read-only `string`: The ID of the trip of which this stop is a part.

This is the value of the `trip_id` property of the entity, and is its `FirstKey` and `ID`.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.



# Methods


## `Factory(IEnumerable<(string, string)>)` (static)
`StopTime`: Creates a new `StopTime`.

### Parameters
* `IEnumerable<(string, string)>` **`properties`**: The property collection.