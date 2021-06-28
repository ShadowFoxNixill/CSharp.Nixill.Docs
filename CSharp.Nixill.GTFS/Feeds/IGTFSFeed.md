```csharp
public interface IGTFSFeed
```

# Summary
Interface containing the bare minimum required tables of a GTFS feed.



# Properties


## `Agencies`
Readable `IDEntityCollection<Agency>`: A collection of the agencies in a feed.


## `Calendars`
Readable `GTFSCalendarCollection`: A collection of the calendars and calendar dates in a feed.


## `Routes`
Readable `IDEntityCollection<Route>`: A collection of the routes in a feed.


## `Stops`
Readable `IDEntityCollection<Stop>`: A collection of the stops in a feed.


## `StopTimes`
Readable `IDEntityCollection<StopTime>>`: A collection of the stop times in a feed.


## `Trips`
Readable `IDEntityCollection<Trip>`: A collection of the trips in a feed.