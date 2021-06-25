```csharp
public enum PickupDropoffType
```

Whether or not boardings or alightings are allowed at or between stops.

* **`Available`** (`0`): Regularly scheduled pickup or drop off.
* **`Unavailable`** (`1`): Pickup or drop off is unavailable.
* **`PhoneAgency`** (`2`): Must phone agency to arrange pickup or drop off.
* **`AskTheDriver`** (`3`): Must coordinate with a driver to arrange pickup or drop off.