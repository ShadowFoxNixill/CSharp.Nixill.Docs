```csharp
public class CalendarDate : GTFSTwoPartEntity<string, LocalDate>
```

# Summary
Represents a single exception to a `Calendar`'s defined service days.

- [Summary](#summary)
- [Properties](#properties)
  - [`Date`](#date)
  - [`ExceptionType`](#exceptiontype)
  - [`FirstKey`](#firstkey)
  - [`IsAdded`](#isadded)
  - [`IsRemoved`](#isremoved)
  - [`SecondKey`](#secondkey)
  - [`ServiceID`](#serviceid)
  - [`this[string]`](#thisstring)
  - [`Properties` (protected)](#properties-protected)
- [Methods](#methods)
  - [`Factory(IEnumerable<(string, string)>)` (static)](#factoryienumerablestring-string-static)



# Properties


## `Date`
Read-only `LocalDate`: Identifies the date on which this exception occurs.

This is the value of the `date` property of the entity, and is its `SecondKey`.


## `ExceptionType`
Read-only `ExceptionType`: Identifies whether service is available on `Date`.

This is the value of the `exception_type` property of the entity.


## `FirstKey`
Read-only `string`: The first key of the entity.

This is the value of the `service_id` property of the entity.


## `IsAdded`
Read-only `bool`: Whether or not this record adds service to `ServiceID` on `Date`.

This is whether or not the `exception_type` property equals `1`.


## `IsRemoved`
Read-only `bool`: Whether or not this record removes service from `ServiceID` on `Date`.

This is whether or not the `exception_type` property equals `2`.


## `SecondKey`
Read-only `LocalDate`: The second key of the entity.

This is the value of the `date` property of the entity.


## `ServiceID`
Read-only `string`: Identifies the set of dates to which this record adds an exception.

This is the value of the `service_id` property of the entity, and is its `FirstKey`.


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.



# Methods


## `Factory(IEnumerable<(string, string)>)` (static)
`CalendarDate`: Creates a new `CalendarDate`.

### Parameters
* `IEnumerable<(string, string)>` **`properties`**: The property collection.