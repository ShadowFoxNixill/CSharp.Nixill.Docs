```csharp
public class PropertyTypeException : PropertyException
```

# Summary
Exception thrown when a property exists, but cannot be parsed as the right type of data.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`PropertyTypeException([string, string, exception])`](#propertytypeexceptionstring-string-exception)
- [Properties](#properties)
  - [`PropertyName`](#propertyname)



# Constructors


## `PropertyTypeException([string, string, exception])`
Creates a `PropertyTypeException`.

### Parameters
* `string` **`property`** (optional): The name of the property that caused the exception.
* `string` **`message`** (optional): The message to be displayed in the stack trace.
* `Exception` **`inner`** (optional): The inner exception that caused this exception.



# Properties


## `PropertyName`
Read-only `string`: The name of the property that caused the exception.