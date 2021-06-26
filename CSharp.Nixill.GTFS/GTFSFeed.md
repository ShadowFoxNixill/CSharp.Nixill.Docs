```csharp
public class GTFSFeed
```

# Summary
Represents a single GTFS feed. This class provides access to all of the data within the feed.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`GTFSFeed(IGTFSDataSource)`](#gtfsfeedigtfsdatasource)
- [Properties](#properties)
  - [`Agencies`](#agencies)
  - [`Calendars`](#calendars)
  - [`DataSource`](#datasource)
  - [`DefaultAgencyID`](#defaultagencyid)
  - [`Routes`](#routes)
  - [`Stops`](#stops)
  - [`StopTimes`](#stoptimes)
  - [`Trips`](#trips)
- [Methods](#methods)



# Constructors


## `GTFSFeed(IGTFSDataSource)`
Creates a GTFS feed with a given `IGTFSDataSource`.



# Properties


## `Agencies`
Read-only `IDEntityCollection<Agency>`: The collection of `Agency`s within the feed.


## `Calendars`
Read-only `GTFSCalendarCollection`: The collection of `Calendar`s and `CalendarDate`s within the feed.


## `DataSource`
Read-only `IGTFSDataSource`: The data source and parser of the GTFS feed. It can be used directly to parse custom tables that this library may not be expecting to see.


## `DefaultAgencyID`
Read-only `string`: The feed's default `agency_id`. If there are multiple agencies, this default shouldn't be used, but will return an arbitrarily selected ID.


## `Routes`
Read-only `IDEntityCollection<Route>`: The collection of `Route`s within the feed.


## `Stops`
Read-only `IDEntityCollection<Stop>`: The collection of `Stop`s within the feed.


## `StopTimes`
Read-only `GTFSOrderedEntityCollection<StopTime>`: The collection of `StopTime`s within the feed.


## `Trips`
Read-only `IDEntityCollection<Trip>`: The collection of `Trip`s within the feed.



# Methods