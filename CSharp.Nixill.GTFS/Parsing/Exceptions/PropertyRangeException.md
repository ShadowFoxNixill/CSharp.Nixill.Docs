```csharp
public class PropertyRangeException : PropertyException
```

# Summary
Exception thrown when a property is a value outside the valid range.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`PropertyRangeException([string, string, exception])`](#PropertyRangeExceptionstring-string-exception)
- [Properties](#properties)
  - [`PropertyName`](#propertyname)



# Constructors


## `PropertyRangeException([string, string, exception])`
Creates a `PropertyRangeException`.

### Parameters
* `string` **`property`** (optional): The name of the property that caused the exception.
* `string` **`message`** (optional): The message to be displayed in the stack trace.
* `Exception` **`inner`** (optional): The inner exception that caused this exception.



# Properties


## `PropertyName`
Read-only `string`: The name of the property that caused the exception.