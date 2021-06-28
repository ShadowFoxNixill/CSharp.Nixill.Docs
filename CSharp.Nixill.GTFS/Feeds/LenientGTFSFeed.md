```csharp
public class LenientGTFSFeed : IStandardGTFSFeed
```

# Summary
Represents a single GTFS feed. This feed doesn't check data and creates entities blindly.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`GTFSFeed(IGTFSDataSource)`](#gtfsfeedigtfsdatasource)
- [Properties](#properties)
  - [`DefaultAgencyID`](#defaultagencyid)



# Constructors


## `GTFSFeed(IGTFSDataSource)`
Creates a GTFS feed with a given `IGTFSDataSource`.



# Properties


## `DefaultAgencyID`
Read-only `string`: The feed's default `agency_id`. If there are multiple agencies, this default shouldn't be used, but will return an arbitrarily selected ID.