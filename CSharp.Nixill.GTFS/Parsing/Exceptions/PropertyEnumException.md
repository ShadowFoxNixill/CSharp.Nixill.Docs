```csharp
public class PropertyEnumException : PropertyException
```

# Summary
Exception thrown when a property is a number that doesn't map to a valid enum value.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`PropertyEnumException([string, string, exception])`](#propertyenumexceptionstring-string-exception)
- [Properties](#properties)
  - [`PropertyName`](#propertyname)



# Constructors


## `PropertyEnumException([string, string, exception])`
Creates a `PropertyEnumException`.

### Parameters
* `string` **`property`** (optional): The name of the property that caused the exception.
* `string` **`message`** (optional): The message to be displayed in the stack trace.
* `Exception` **`inner`** (optional): The inner exception that caused this exception.



# Properties


## `PropertyName`
Read-only `string`: The name of the property that caused the exception.