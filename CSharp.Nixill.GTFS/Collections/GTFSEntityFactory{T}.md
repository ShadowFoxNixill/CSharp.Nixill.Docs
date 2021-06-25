```csharp
public delegate T GTFSEntityFactory<T>(IEnumerable<(string, string)> props) where T : GTFSEntity;
```

# Summary
A method that takes the properties of an entity and outputs the entity with those properties.

- [Summary](#summary)
- [Type parameters](#type-parameters)
- [Parameters](#parameters)
- [Return value](#return-value)

# Type parameters
* **`T`** : `GTFSEntity`: The type of output entity.

# Parameters
* `IEnumerable<(string, string)>` **`props`**: The property collection to use.

# Return value
`T`: The entity created with those properties.
