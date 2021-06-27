```csharp
public class Stop : GTFSIdentifiedEntity
```

# Summary
A key location in a GTFS feed, such as a transit stop, station or station entrance/exit.

- [Summary](#summary)
- [Remarks](#remarks)
- [Properties](#properties)
  - [`Description`](#description)
  - [`ID`](#id)
  - [`Latitude`](#latitude)
  - [`LevelID`](#levelid)
  - [`LocationType`](#locationtype)
  - [`Longitude`](#longitude)
  - [`Name`](#name)
  - [`ParentStationID`](#parentstationid)
  - [`PlatformCode`](#platformcode)
  - [`StopCode`](#stopcode)
  - [`StopUrl`](#stopurl)
  - [`this[string]`](#thisstring)
  - [`TimeZone`](#timezone)
  - [`WheelchairBoarding`](#wheelchairboarding)
  - [`ZoneID`](#zoneid)
  - [`Properties` (protected)](#properties-protected)
- [Methods](#methods)
  - [`Factory(IEnumerable<(string, string)>)` (static)](#factoryienumerablestring-string-static)



# Remarks
The term "station entrance" refers to both station entrances and station exits. Stops, station or station entrances are collectively referred to as locations. Multiple routes may use the same stop.



# Properties


## `Description`
Read-only `string`: Description of the location that provides useful, quality information.

This is the value of the `stop_name` property of the entity. It should not simply duplicate the name of the location.


## `ID`
Read-only `string`: The ID of the entity.

This is the value of the `stop_id` property of the entity.


## `Latitude`
Read-only `double?`: The latitude of the location.

This is the value of the `stop_lat` property of the entity. It is not required on `StopLocationType.GenericNode`s or `StopLocationType.BoardingArea`s.


## `LevelID`
Read-only `string`: Level of the location.

This is the value of `level_id` property of the entity. The same level can be used by multiple unlinked stations.


## `LocationType`
Read-only `StopLocationType`: Type of the location.

This is the value of the `location_type` property of the entity and defaults to `StopLocationType.StopPlatform`.


## `Longitude`
Read-only `double?`: The longitude of the location.

This is the value of the `stop_lon` property of the entity. It is not required on `StopLocationType.GenericNode`s or `StopLocationType.BoardingArea`s.


## `Name`
Read-only `string`: The name of the location.

This is the value of the `stop_name` property of the entity. It should be a name that people will understand in the local and tourist vernacular.

When the location is a boarding area (`LocationType == StopLocationType.BoardingArea`), the `Name` should contains the name of the boarding area as displayed by the agency. It could be just one letter (like on some European intercity railway stations), or text like “Wheelchair boarding area” (NYC’s Subway) or “Head of short trains” (Paris’ RER).


## `ParentStationID`
Read-only `string`: Defines hierarchy between the different locations.

This is the value of the `parent_station` property of the entity. It contains the ID of the parent location, as follows:

* For `StopLocationType.StopPlatform`s, it may contain a `StopLocationType.Station` or be empty.
* For `StopLocationType.Station`s, it must be empty.
* For `StopLocationType.EntranceExit`s or `StopLocationType.GenericNode`s, it must contain a `StopLocationType.Station`.
* For `StopLocationType.BoardingArea`s, it must contain a `StopLocationType.StopPlatform`.


## `PlatformCode`
Read-only `string`: Platform identifier for a platform stop (a stop belonging to a station).

This is the value of the `platform_code` property of the entity. This should be just the platform identifier (eg. G or 3). Words like "platform" or "track" (or the feed’s language-specific equivalent) should not be included. This allows feed consumers to more easily internationalize and localize the platform identifier into other languages.


## `StopCode`
Read-only `string`: Short text or a number that identifies the location for riders.

This is the value of the `stop_code` property of the entity. These codes are often used in phone-based transit information systems or printed on signage to make it easier for riders to get information for a particular location. The `StopCode` can be the same as `ID` if it is public facing. This field should be left empty for locations without a code presented to riders.


## `StopUrl`
Read-only `string`: URL of a web page about the location.

This is the value of the `stop_url` property of the entity. It should be different from the `Agency.Url` and `Route.Url` field values.


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `TimeZone`
Read-only `DateTimeZone`: Timezone of the location.

This is the value of the `stop_timezone` property of the entity. If the location has a `ParentStation`, it inherits the parent station's `TimeZone` instead of applying its own. Stations and parentless stops with empty `TimeZone`s inherit the timezone specified by `Agency.TimeZone`.

Regardless of the value of `TimeZone`, `StopTimes` should have times entered relative to the `Agency.TimeZone`, ensuring that time values always increase during a trip regardless of which timezones the trip crosses.


## `WheelchairBoarding`
Read-only `Tristate`: Indicates whether wheelchair boardings are possible from this location.

This is the value of the `wheelchair_boarding` property of the entity, and defaults to `Tristate.Unknown`.


## `ZoneID`
Read-only `string`: Identifies the fare zone for a stop.

This is the value of the `zone_id` property of the entity. This field is required if providing fare information using `FareRule`s, otherwise it is optional. If this record represents a station or station entrance, the `ZoneID` is ignored.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.



# Methods


## `Factory(IEnumerable<(string, string)>)` (static)
`Stop`: Creates a new `Stop`.

### Parameters
* `IEnumerable<(string, string)>` **`properties`**: The property collection.