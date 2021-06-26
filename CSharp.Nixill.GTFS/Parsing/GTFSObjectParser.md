```csharp
public static class GTFSObjectParser
```

# Summary
Utility class to convert string values to other data types.

- [Summary](#summary)
- [Properties (static)](#properties-static)
  - [`ColorRegex`](#colorregex)
  - [`DatePattern`](#datepattern)
  - [`DateRegex`](#dateregex)
  - [`TimePattern`](#timepattern)
  - [`TimeRegex`](#timeregex)
- [Methods (static)](#methods-static)
  - [`GetBool(string)`](#getboolstring)
  - [`GetColor(string, Color?)`](#getcolorstring-color)
  - [`GetDate(string, LocalDate?)`](#getdatestring-localdate)
  - [`GetNullableBool(string)`](#getnullableboolstring)
  - [`GetNullableColor(string)`](#getnullablecolorstring)
  - [`GetNullableDate(string)`](#getnullabledatestring)
  - [`GetNullableDecimal(string)`](#getnullabledecimalstring)
  - [`GetNullableDouble(string)`](#getnullabledoublestring)
  - [`GetNullableInt(string)`](#getnullableintstring)
  - [`GetNullableNonNegativeDecimal(string)`](#getnullablenonnegativedecimalstring)
  - [`GetNullableNonNegativeDouble(string)`](#getnullablenonnegativedoublestring)
  - [`GetNullableNonNegativeInt(string)`](#getnullablenonnegativeintstring)
  - [`GetNullableTime(string)`](#getnullabletimestring)
  - [`GetTime(string, Duration?)`](#gettimestring-duration)
  - [`GetTimeZone(string)`](#gettimezonestring)
  - [`IsBool(string)`](#isboolstring)
  - [`IsColor(string)`](#iscolorstring)
  - [`IsDate(string)`](#isdatestring)
  - [`IsDecimal(string)`](#isdecimalstring)
  - [`IsDouble(string)`](#isdoublestring)
  - [`IsInt(string)`](#isintstring)
  - [`IsNonNegativeDecimal(string)`](#isnonnegativedecimalstring)
  - [`IsNonNegativeDouble(string)`](#isnonnegativedoublestring)
  - [`IsNonNegativeInt(string)`](#isnonnegativeintstring)
  - [`IsTime(string)`](#istimestring)
- [Extension methods to `GTFSPropertyCollection`](#extension-methods-to-gtfspropertycollection)
  - [`GTFSPropertyCollection.GetBool(string)`](#gtfspropertycollectiongetboolstring)
  - [`GTFSPropertyCollection.GetColor(string, Color?)`](#gtfspropertycollectiongetcolorstring-color)
  - [`GTFSPropertyCollection.GetDate(string, LocalDate?)`](#gtfspropertycollectiongetdatestring-localdate)
  - [`GTFSPropertyCollection.GetDecimal(string, decimal?)`](#gtfspropertycollectiongetdecimalstring-decimal)
  - [`GTFSPropertyCollection.GetDouble(string, double?)`](#gtfspropertycollectiongetdoublestring-double)
  - [`GTFSPropertyCollection.GetInt(string, Int?)`](#gtfspropertycollectiongetintstring-int)
  - [`GTFSPropertyCollection.GetNullableBool(string)`](#gtfspropertycollectiongetnullableboolstring)
  - [`GTFSPropertyCollection.GetNullableColor(string)`](#gtfspropertycollectiongetnullablecolorstring)
  - [`GTFSPropertyCollection.GetNullableDate(string)`](#gtfspropertycollectiongetnullabledatestring)
  - [`GTFSPropertyCollection.GetNullableDecimal(string)`](#gtfspropertycollectiongetnullabledecimalstring)
  - [`GTFSPropertyCollection.GetNullableDouble(string)`](#gtfspropertycollectiongetnullabledoublestring)
  - [`GTFSPropertyCollection.GetNullableInt(string)`](#gtfspropertycollectiongetnullableintstring)
  - [`GTFSPropertyCollection.GetNullableNonNegativeDecimal(string)`](#gtfspropertycollectiongetnullablenonnegativedecimalstring)
  - [`GTFSPropertyCollection.GetNullableNonNegativeDouble(string)`](#gtfspropertycollectiongetnullablenonnegativedoublestring)
  - [`GTFSPropertyCollection.GetNullableNonNegativeInt(string)`](#gtfspropertycollectiongetnullablenonnegativeintstring)
  - [`GTFSPropertyCollection.GetNullableTime(string)`](#gtfspropertycollectiongetnullabletimestring)
  - [`GTFSPropertyCollection.GetTime(string, Duration?)`](#gtfspropertycollectiongettimestring-duration)
  - [`GTFSPropertyCollection.GetTimeZone(string)`](#gtfspropertycollectiongettimezonestring)
  - [`GTFSPropertyCollection.IsBool(string)`](#gtfspropertycollectionisboolstring)
  - [`GTFSPropertyCollection.IsColor(string)`](#gtfspropertycollectioniscolorstring)
  - [`GTFSPropertyCollection.IsDate(string)`](#gtfspropertycollectionisdatestring)
  - [`GTFSPropertyCollection.IsDecimal(string)`](#gtfspropertycollectionisdecimalstring)
  - [`GTFSPropertyCollection.IsDouble(string)`](#gtfspropertycollectionisdoublestring)
  - [`GTFSPropertyCollection.IsInt(string)`](#gtfspropertycollectionisintstring)
  - [`GTFSPropertyCollection.IsNonNegativeDecimal(string)`](#gtfspropertycollectionisnonnegativedecimalstring)
  - [`GTFSPropertyCollection.IsNonNegativeDouble(string)`](#gtfspropertycollectionisnonnegativedoublestring)
  - [`GTFSPropertyCollection.IsNonNegativeInt(string)`](#gtfspropertycollectionisnonnegativeintstring)
  - [`GTFSPropertyCollection.IsTime(string)`](#gtfspropertycollectionistimestring)



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


## `GetNullableBool(string)`
`bool?`: Returns whether the input is `0` (`false`) or `1` (`true`).

Returns `null` for any other input.

### Parameters
* `string` **`input`**: The input to parse.


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


## `GetNullableDecimal(string)`
`decimal?`: Returns a `decimal` if the input is a valid decimal; otherwise, returns `null`.

### Parameters
* `string` **`input`**: The input to parse.


## `GetNullableDouble(string)`
`double?`: Returns a `double` if the input is a valid double; otherwise, returns `null`.

### Parameters
* `string` **`input`**: The input to parse.


## `GetNullableInt(string)`
`int?`: Returns a `int` if the input is a valid integer; otherwise, returns `null`.

### Parameters
* `string` **`input`**: The input to parse.


## `GetNullableNonNegativeDecimal(string)`
`decimal?`: Returns a `decimal` if the input is a valid, non-negative decimal; otherwise, returns `null`.

### Parameters
* `string` **`input`**: The input to parse.


## `GetNullableNonNegativeDouble(string)`
`double?`: Returns a `double` if the input is a valid, non-negative double; otherwise, returns `null`.

### Parameters
* `string` **`input`**: The input to parse.


## `GetNullableNonNegativeInt(string)`
`int?`: Returns a `int` if the input is a valid, non-negative integer; otherwise, returns `null`.

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

### Exceptions
* `Exception`: `input` is not a valid time.


## `GetTimeZone(string)`
`DateTimeZone`: Returns the identified `DateTimeZone`, or `null` if there is no such zone.

As `DateTimeZone` is a nullable type, this method does not have a "Nullable" variant, nor can it throw an exception.


## `IsBool(string)`
`bool`: Returns whether the input is `0` or `1` (`true`), or something else (`false`).

### Parameters
* `string` **`input`**: The input to check.


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


## `IsNonNegativeDecimal(string)`
`bool`: Returns whether or not the input is a valid, non-negative `decimal`.

### Parameters
* `string` **`input`**: The input to check.


## `IsNonNegativeDouble(string)`
`bool`: Returns whether or not the input is a valid, non-negative `double`.

### Parameters
* `string` **`input`**: The input to check.


## `IsNonNegativeInt(string)`
`bool`: Returns whether or not the input is a valid, non-negative `int`.

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


## `GTFSPropertyCollection.GetDate(string, LocalDate?)`
`LocalDate`: Returns a `LocalDate`.

To be a valid date, the input must be in `YYYYMMDD` format, with no separators between the components.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `LocalDate?` **`def`** (default `null`): Default to use if the input isn't a valid date.

### Exceptions
* `Exception`: `input` is not a valid date, and no default is provided.


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


## `GTFSPropertyCollection.GetNullableBool(string)`
`bool?`: Returns whether the input is `0` (`false`) or `1` (`true`).

Returns `null` for any other input.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.


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


## `GTFSPropertyCollection.GetNullableDecimal(string)`
`decimal?`: Returns a `decimal` if the input is a valid decimal; otherwise, returns `null`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.


## `GTFSPropertyCollection.GetNullableDouble(string)`
`double?`: Returns a `double` if the input is a valid double; otherwise, returns `null`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.


## `GTFSPropertyCollection.GetNullableInt(string)`
`int?`: Returns a `int` if the input is a valid int; otherwise, returns `null`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.


## `GTFSPropertyCollection.GetNullableNonNegativeDecimal(string)`
`decimal?`: Returns a `decimal` if the input is a valid, non-negative decimal; otherwise, returns `null`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.


## `GTFSPropertyCollection.GetNullableNonNegativeDouble(string)`
`double?`: Returns a `double` if the input is a valid, non-negative double; otherwise, returns `null`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.


## `GTFSPropertyCollection.GetNullableNonNegativeInt(string)`
`int?`: Returns a `int` if the input is a valid, non-negative int; otherwise, returns `null`.

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

### Exceptions
* `Exception`: `input` is not a valid time.


## `GTFSPropertyCollection.GetTimeZone(string)`
`DateTimeZone`: Returns the identified `DateTimeZone`, or `null` if there is no such zone.

As `DateTimeZone` is a nullable type, this method does not have a "Nullable" variant, nor can it throw an exception.


## `GTFSPropertyCollection.IsBool(string)`
`bool`: Returns whether the input is `0` or `1` (`true`) or anything else (`false`).

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to check.


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


## `GTFSPropertyCollection.IsNonNegativeDecimal(string)`
`bool`: Returns whether or not the input is a valid, non-negative `decimal`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to check.


## `GTFSPropertyCollection.IsNonNegativeDouble(string)`
`bool`: Returns whether or not the input is a valid, non-negative `double`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to check.


## `GTFSPropertyCollection.IsNonNegativeInt(string)`
`bool`: Returns whether or not the input is a valid, non-negative `int`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to check.


## `GTFSPropertyCollection.IsTime(string)`
`bool`: Returns whether or not the input is a valid time.

To be a valid time, the input must be in `H:mm:ss` or `HH:mm:ss` format.
