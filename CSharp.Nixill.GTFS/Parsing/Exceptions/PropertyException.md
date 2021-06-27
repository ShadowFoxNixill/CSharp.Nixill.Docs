```csharp
public class PropertyException : SystemException
```

# Summary
An exception relating to a GTFS entity's properties.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`PropertyException([string, string, Exception])`](#propertyexceptionstring-string-exception)
- [Properties](#properties)
  - [`PropertyName`](#propertyname)



# Constructors


## `PropertyException([string, string, Exception])`
Creates a `PropertyException`.

### Parameters
* `string` **`property`** (optional): The name of the property that caused the exception.
* `string` **`message`** (optional): The message to be displayed in the stack trace.
* `Exception` **`inner`** (optional): The inner exception that caused this exception.



# Properties


## `PropertyName`
Read-only `string`: The name of the property that caused the exception.



