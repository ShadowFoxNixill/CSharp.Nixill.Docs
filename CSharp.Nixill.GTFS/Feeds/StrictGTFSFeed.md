```csharp
public class StrictGTFSFeed : IStandardGTFSFeed
```

# Summary
Represents a standards-compliant GTFS feed. Objects which aren't compatible with the standards on GTFS.org are rejected.

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
