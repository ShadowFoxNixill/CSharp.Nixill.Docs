```csharp
public interface IStandardGTFSFeed : IGTFSFeed
```

# Summary
Interface for the standard tables of a GTFS feed.

- [Summary](#summary)
- [Properties](#properties)
  - [`FareAttributes`](#fareattributes)
  - [`FareRules`](#farerules)



# Properties


## `FareAttributes`
Readable `IDEntityCollection<FareAttribute>`: The collection of fare attributes within the GTFS feed.


## `FareRules`
Readable `GTFSGenericCollection<FareRule>`: A collection of the fare rules in a feed.

