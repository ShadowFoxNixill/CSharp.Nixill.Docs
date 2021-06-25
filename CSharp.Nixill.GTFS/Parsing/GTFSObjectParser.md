```csharp
public static class GTFSObjectParser
```

# Summary
Utility class to convert string values to other data types.



# Properties (static)


## `ColorRegex`
Read-only `Regex`: Regex used to validate and parse colors: `^[0-9a-f]{6}$` (case-insensitive)


## `DatePattern`
Read-only `LocalDatePattern`: Pattern used to parse dates: `uuuuMMdd`


## `DateRegex`
Read-only `Regex`: Regex used to validate dates: `^\d{8}$`


## `TimePattern`
Read-only `DurationPattern`: Pattern used to parse times: `H:mm:ss`


## `TimeRegex`
Read-only `Regex`: Regex used to validate times: `^\d+:\d\d:\d\d$`



# Methods (static)


## `GetBool(string)`
`bool`: Returns whether or not the input is `1`.

Returns `false` for any other input, even `null`.

### Parameters
* `string` **`input`**: The input to check.


## `GetColor(string, Color?)`
`Color`: Returns a `Color`.

To be a valid color, the input must be a six-hex digit code, *without* the leading `#` sign.

### Parameters
* `string` **`input`**: The input to parse.
* `Color?` **`def`** (default `null`): Default to use if the input isn't a valid color.

### Exceptions
* `ArgumentException`: `input` is not a valid color, and no default is provided.


## `GetDate(string, LocalDate?)`
`LocalDate`: Returns a `LocalDate`.

To be a valid date, the input must be in `YYYYMMDD` format, with no separators between the components.

### Parameters
* `string` **`input`**: The input to parse.
* `LocalDate?` **`def`** (default `null`): Default to use if the input isn't a valid date.

### Exceptions
* `Exception`: `input` is not a valid date, and no default is provided.


## `GetNullableColor(string)`
`Color?`: Returns a `Color` if the input is a valid color; otherwise, returns `null`.

To be a valid color, the input must be a six-hex digit code, *without* the leading `#` sign.

### Parameters
* `string` **`input`**: The input to parse.


## `GetNullableDate(string)`
`LocalDate?`: Returns a `LocalDate` if the input is a valid date; otherwise, returns `null`.

To be a valid date, the input must be in `YYYYMMDD` format, with no separators between the components.

### Parameters
* `string` **`input`**: The input to parse.


## `GetNullableTime(string)`
`Duration?`: Returns a `Duration` if the input is a valid time; otherwise, returns `null`.

To be a valid time, the input must be in `H:mm:ss` or `HH:mm:ss` format.

### Parameters
* `string` **`input`**: The input to parse.


## `GetTime(string, Duration?)`
`Duration`: Returns a `Duration`.

To be a valid time, the input must be in `H:mm:ss` or `HH:mm:ss` format.

### Parameters
* `string` **`input`**: The input to parse.
* `Duration?` **`def`** (default `null`): The default to use if the input isn't a valid time.

## Exceptions
* `Exception`: `input` is not a valid time.


## `GetTimeZone(string)`
`DateTimeZone`: Returns the identified `DateTimeZone`, or `null` if there is no such zone.

As `DateTimeZone` is a nullable type, this method does not have a "Nullable" variant, nor can it throw an exception.


## `IsColor(string)`
`bool`: Returns whether or not the input is a valid color.

To be a valid color, the input must be a six-hex digit code, *without* the leading `#` sign.

### Parameters
* `string` **`input`**: The input to check.


## `IsDate(string)`
`bool`: Returns whether or not the input is a valid date.

To be a valid date, the input must be in `YYYYMMDD` format, with no separators between the components.

### Parameters
* `string` **`input`**: The input to check.


## `IsDecimal(string)`
`bool`: Returns whether or not the input is a valid `decimal`.

### Parameters
* `string` **`input`**: The input to check.


## `IsDouble(string)`
`bool`: Returns whether or not the input is a valid `double`.

### Parameters
* `string` **`input`**: The input to check.


## `IsInt(string)`
`bool`: Returns whether or not the input is a valid `int`.

### Parameters
* `string` **`input`**: The input to check.


## `IsTime(string)`
`bool`: Returns whether or not the input is a valid time.

To be a valid time, the input must be in `H:mm:ss` or `HH:mm:ss` format.



# Extension methods to `GTFSPropertyCollection`


## `GTFSPropertyCollection.GetBool(string)`
`bool`: Returns whether or not the input is `1`.

Returns `false` for any other input, even `null`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.


## `GTFSPropertyCollection.GetColor(string, Color?)`
`Color`: Returns a `Color`.

To be a valid color, the input must be a six-hex digit code, *without* the leading `#` sign.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `Color?` **`def`** (default `null`): Default to use if the input isn't a valid color.

### Exceptions
* `ArgumentException`: `input` is not a valid color, and no default is provided.


## `GTFSPropertyCollection.GetDecimal(string, decimal?)`
`decimal`: Returns a `decimal`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `decimal?` **`def`** (default `null`): Default to use if the input isn't a valid number.


## `GTFSPropertyCollection.GetDouble(string, double?)`
`double`: Returns a `double`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `double?` **`def`** (default `null`): Default to use if the input isn't a valid number.


## `GTFSPropertyCollection.GetInt(string, Int?)`
`int`: Returns an `int`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `int?` **`def`** (default `null`): Default to use if the input isn't a valid number.


## `GTFSPropertyCollection.GetDate(string, LocalDate?)`
`LocalDate`: Returns a `LocalDate`.

To be a valid date, the input must be in `YYYYMMDD` format, with no separators between the components.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `LocalDate?` **`def`** (default `null`): Default to use if the input isn't a valid date.

### Exceptions
* `Exception`: `input` is not a valid date, and no default is provided.


## `GTFSPropertyCollection.GetNullableColor(string)`
`Color?`: Returns a `Color` if the input is a valid color; otherwise, returns `null`.

To be a valid color, the input must be a six-hex digit code, *without* the leading `#` sign.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.


## `GTFSPropertyCollection.GetNullableDate(string)`
`LocalDate?`: Returns a `LocalDate` if the input is a valid date; otherwise, returns `null`.

To be a valid date, the input must be in `YYYYMMDD` format, with no separators between the components.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.


## `GTFSPropertyCollection.GetNullableTime(string)`
`Duration?`: Returns a `Duration` if the input is a valid time; otherwise, returns `null`.

To be a valid time, the input must be in `H:mm:ss` or `HH:mm:ss` format.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.


## `GTFSPropertyCollection.GetTime(string, Duration?)`
`Duration`: Returns a `Duration`.

To be a valid time, the input must be in `H:mm:ss` or `HH:mm:ss` format.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `Duration?` **`def`** (default `null`): The default to use if the input isn't a valid time.

## Exceptions
* `Exception`: `input` is not a valid time.


## `GTFSPropertyCollection.GetTimeZone(string)`
`DateTimeZone`: Returns the identified `DateTimeZone`, or `null` if there is no such zone.

As `DateTimeZone` is a nullable type, this method does not have a "Nullable" variant, nor can it throw an exception.


## `GTFSPropertyCollection.IsColor(string)`
`bool`: Returns whether or not the input is a valid color.

To be a valid color, the input must be a six-hex digit code, *without* the leading `#` sign.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to check.


## `GTFSPropertyCollection.IsDate(string)`
`bool`: Returns whether or not the input is a valid date.

To be a valid date, the input must be in `YYYYMMDD` format, with no separators between the components.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to check.


## `GTFSPropertyCollection.IsDecimal(string)`
`bool`: Returns whether or not the input is a valid `decimal`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to check.


## `GTFSPropertyCollection.IsDouble(string)`
`bool`: Returns whether or not the input is a valid `double`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to check.


## `GTFSPropertyCollection.IsInt(string)`
`bool`: Returns whether or not the input is a valid `int`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to check.


## `GTFSPropertyCollection.IsTime(string)`
`bool`: Returns whether or not the input is a valid time.

To be a valid time, the input must be in `H:mm:ss` or `HH:mm:ss` format.
