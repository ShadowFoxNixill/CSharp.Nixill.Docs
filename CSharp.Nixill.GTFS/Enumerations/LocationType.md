```csharp
public enum StopLocationType
```

The type of location in the `Stops` table.

* **`StopPlatform`** (`0`): Stop (or Platform). A location where passengers board or disembark from a transit vehicle. Is called a platform when defined with a `ParentStation`.
* **`Station`** (`1`): Station. A physical structure or area that contains one or more platforms.
* **`EntranceExit`** (`2`): Entrance/Exit. A location where passengers can enter or exit a station from the street. If an entrance/exit belongs to multiple stations, it can be linked by pathways to both, but the data provider must pick one of them as parent.
* **`GenericNode`** (`3`): Generic Node. A location within a station, not matching any other `StopLocationType`, which can be used to link together `Pathway`s.
* **`BoardingArea`** (`4`): Boarding Area. A specific location on a platform, where passengers can board and/or alight vehicles.
