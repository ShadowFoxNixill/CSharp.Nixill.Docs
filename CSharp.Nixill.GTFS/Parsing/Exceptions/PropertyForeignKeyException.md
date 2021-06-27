```csharp
public class PropertyNullException : PropertyException
```

# Summary
Exception thrown when a property is a foreign key mapped to a nonexistent entity.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`PropertyNullException([string, string, exception])`](#propertynullexceptionstring-string-exception)
- [Properties](#properties)
  - [`PropertyName`](#propertyname)



# Constructors


## `PropertyNullException([string, string, exception])`
Creates a `PropertyNullException`.

### Parameters
* `string` **`property`** (optional): The name of the property that caused the exception.
* `string` **`message`** (optional): The message to be displayed in the stack trace.
* `Exception` **`inner`** (optional): The inner exception that caused this exception.



# Properties


## `PropertyName`
Read-only `string`: The name of the property that caused the exception.