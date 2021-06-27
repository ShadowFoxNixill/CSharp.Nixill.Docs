```csharp
public abstract class Route : GTFSIdentifiedEntity
```

# Summary
Represents a single transit route within a GTFS feed.

- [Summary](#summary)
- [Properties](#properties)
  - [`AgencyID`](#agencyid)
  - [`ContinuousDropoff`](#continuousdropoff)
  - [`ContinuousPickup`](#continuouspickup)
  - [`Description`](#description)
  - [`ID`](#id)
  - [`LongName`](#longname)
  - [`RouteColor`](#routecolor)
  - [`SortOrder`](#sortorder)
  - [`ShortName`](#shortname)
  - [`TextColor`](#textcolor)
  - [`this[string]`](#thisstring)
  - [`Type`](#type)
  - [`Url`](#url)
  - [`Properties` (protected)](#properties-protected)
- [Methods](#methods)
  - [`GetFactory(string)` (static)](#getfactorystring-static)



# Properties


## `AgencyID`
Read-only `string`: The ID of the agency for the route.

This is the value of the `agency_id` property of the entity. If it's never specified within the feed, this property will be equal to the empty string.


## `ContinuousDropoff`
Read-only `PickupDropoffType`: Indicates whether a rider can alight from the transit vehicle anywhere along the vehicle's travel path.

This is the value of the `continuous_drop_off` property of the entity. The path is described by `ShapePoint`s on every trip of the route. The default continuous drop-off behavior is `PickupDropoffType.Unavailable`, and the behavior defined in `Route`s can be overridden in `StopTime`s.


## `ContinuousPickup`
Read-only `PickupDropoffType`: Indicates whether a rider can board the transit vehicle anywhere along the vehicle's travel path.

This is the value of the `continuous_pickup` property of the entity. The path is described by `ShapePoint`s on every trip of the route. The default continuous pickup behavior is `PickupDropoffType.Unavailable`, and the behavior defined in `Route`s can be overridden in `StopTime`s.


## `Description`
Read-only `string`: Description of a route that provides useful, quality information.

This is the value of the `route_desc` property of the entity. It shouldn't just duplicate a name of the route. For example:

> "A" trains operate between Inwood-207 St, Manhattan and Far Rockaway-Mott Avenue, Queens at all times. Also from about 6AM until about midnight, additional "A" trains operate between Inwood-207 St and Lefferts Boulevard (trains typically alternate between Lefferts Blvd and Far Rockaway).


## `ID`
Read-only `string`: The ID of the entity.

This is the value of the `route_id` property of the entity.


## `LongName`
Read-only `string`: The full name of a route.

This is the value of the `route_long_name` property of the entity. This name is generally more descriptive than the `ShortName` and often includes the route's destination or stop. Either `ShortName` or `LongName` must be specified; potentially both if appropriate.


## `RouteColor`
Read-only `Color`: Route color designation that matches public facing material.

This is the value of the `route_color` property of the entity. It defaults to `Color.White` when empty. The color difference between `RouteColor` and `TextColor` should provide sufficient contrast when viewed on a black and white screen.


## `SortOrder`
Read-only `int?`: Orders the routes in a way which is ideal for presentation to customers.

This is the value of the `route_sort_order` property of the entity. Routes with smaller `SortOrder` values should be displayed first.


## `ShortName`
Read-only `string`: The short name of a route.

This is the value of the `route_short_name` property of the entity. It will often be a short, abstract identifier like "32", "100X", or "Green" that riders use to identify a route, but which doesn't give any indication of what places the route serves. Either `ShortName` or `LongName` must be specified; potentially both if appropriate.


## `TextColor`
Read-only `Color`: Legible color to use for text drawn against a background of `RouteColor`.

This is the value of the `route_text_color` property of the entity. It defaults to `Color.Black` when empty. The color difference between `RouteColor` and `TextColor` should provide sufficient contrast when viewed on a black and white screen.


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `Type`
Read-only `RouteType`: Indicates the type of transportation used on a route.

This is the value of the `route_type` property of the entity.


## `Url`
Read-only `string`: URL of a web page about the particular route.

This is the value of the `route_url` property of the entity. It should be different from the `Agency.Url` value.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.



# Methods


## `GetFactory(string)` (static)
`GTFSEntityFactory<Route>`: Gets the factory to create a new `Route`.

### Parameters
* `string` **`defaultAgency`**: The `agency_id` to use by default.