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
  - [`AssertBool(string, string)`](#assertboolstring-string)
  - [`AssertColor(string, string)`](#assertcolorstring-string)
  - [`AssertDate(string, string)`](#assertdatestring-string)
  - [`AssertDecimal(string, string)`](#assertdecimalstring-string)
  - [`AssertDouble(string, string)`](#assertdoublestring-string)
  - [`AssertDuration(string, string)`](#assertdurationstring-string)
  - [`AssertExists(string, string)`](#assertexistsstring-string)
  - [`AssertForeignKey<T>(string, string, GTFSOrderedEntityCollection<T>)`](#assertforeignkeytstring-string-gtfsorderedentitycollectiont)
  - [`AssertForeignKey<T>(string, string, IDEntityCollection<T>)`](#assertforeignkeytstring-string-identitycollectiont)
  - [`AssertInt(string, string)`](#assertintstring-string)
  - [`AssertNonNegativeDecimal(string, string)`](#assertnonnegativedecimalstring-string)
  - [`AssertNonNegativeDouble(string, string)`](#assertnonnegativedoublestring-string)
  - [`AssertNonNegativeInt(string, string)`](#assertnonnegativeintstring-string)
  - [`AssertTime(string, string)`](#asserttimestring-string)
  - [`AssertTimeZone(string, string)`](#asserttimezonestring-string)
  - [`GetBool(string)`](#getboolstring)
  - [`GetColor(string, [Color?])`](#getcolorstring-color)
  - [`GetDate(string, [LocalDate?])`](#getdatestring-localdate)
  - [`GetDuration(string, [Duration?])`](#getdurationstring-duration)
  - [`GetNullableBool(string)`](#getnullableboolstring)
  - [`GetNullableColor(string)`](#getnullablecolorstring)
  - [`GetNullableDate(string)`](#getnullabledatestring)
  - [`GetNullableDecimal(string)`](#getnullabledecimalstring)
  - [`GetNullableDouble(string)`](#getnullabledoublestring)
  - [`GetNullableDuration(string)`](#getnullabledurationstring)
  - [`GetNullableInt(string)`](#getnullableintstring)
  - [`GetNullableNonNegativeDecimal(string)`](#getnullablenonnegativedecimalstring)
  - [`GetNullableNonNegativeDouble(string)`](#getnullablenonnegativedoublestring)
  - [`GetNullableNonNegativeInt(string)`](#getnullablenonnegativeintstring)
  - [`GetNullableTime(string)`](#getnullabletimestring)
  - [`GetTime(string, [Duration?])`](#gettimestring-duration)
  - [`GetTimeZone(string)`](#gettimezonestring)
  - [`IsBool(string)`](#isboolstring)
  - [`IsColor(string)`](#iscolorstring)
  - [`IsDate(string)`](#isdatestring)
  - [`IsDecimal(string)`](#isdecimalstring)
  - [`IsDouble(string)`](#isdoublestring)
  - [`IsDuration(string)`](#isdurationstring)
  - [`IsInt(string)`](#isintstring)
  - [`IsNonNegativeDecimal(string)`](#isnonnegativedecimalstring)
  - [`IsNonNegativeDouble(string)`](#isnonnegativedoublestring)
  - [`IsNonNegativeInt(string)`](#isnonnegativeintstring)
  - [`IsTime(string)`](#istimestring)
- [Extension methods to `GTFSPropertyCollection`](#extension-methods-to-gtfspropertycollection)
  - [`GTFSPropertyCollection.AssertBool(string)`](#gtfspropertycollectionassertboolstring)
  - [`GTFSPropertyCollection.AssertColor(string)`](#gtfspropertycollectionassertcolorstring)
  - [`GTFSPropertyCollection.AssertDate(string)`](#gtfspropertycollectionassertdatestring)
  - [`GTFSPropertyCollection.AssertDecimal(string)`](#gtfspropertycollectionassertdecimalstring)
  - [`GTFSPropertyCollection.AssertDouble(string)`](#gtfspropertycollectionassertdoublestring)
  - [`GTFSPropertyCollection.AssertDuration(string)`](#gtfspropertycollectionassertdurationstring)
  - [`GTFSPropertyCollection.AssertExists(string)`](#gtfspropertycollectionassertexistsstring)
  - [`GTFSPropertyCollection.AssertForeignKey<T>(string, GTFSOrderedEntityCollection<T>)`](#gtfspropertycollectionassertforeignkeytstring-gtfsorderedentitycollectiont)
  - [`GTFSPropertyCollection.AssertForeignKey<T>(string, IDEntityCollection<T>)`](#gtfspropertycollectionassertforeignkeytstring-identitycollectiont)
  - [`GTFSPropertyCollection.AssertInt(string)`](#gtfspropertycollectionassertintstring)
  - [`GTFSPropertyCollection.AssertNonNegativeDecimal(string)`](#gtfspropertycollectionassertnonnegativedecimalstring)
  - [`GTFSPropertyCollection.AssertNonNegativeDouble(string)`](#gtfspropertycollectionassertnonnegativedoublestring)
  - [`GTFSPropertyCollection.AssertNonNegativeInt(string)`](#gtfspropertycollectionassertnonnegativeintstring)
  - [`GTFSPropertyCollection.AssertTime(string)`](#gtfspropertycollectionasserttimestring)
  - [`GTFSPropertyCollection.AssertTimeZone(string)`](#gtfspropertycollectionasserttimezonestring)
  - [`GTFSPropertyCollection.GetBool(string)`](#gtfspropertycollectiongetboolstring)
  - [`GTFSPropertyCollection.GetColor(string, [Color?])`](#gtfspropertycollectiongetcolorstring-color)
  - [`GTFSPropertyCollection.GetDate(string, [LocalDate?])`](#gtfspropertycollectiongetdatestring-localdate)
  - [`GTFSPropertyCollection.GetDecimal(string, [decimal?])`](#gtfspropertycollectiongetdecimalstring-decimal)
  - [`GTFSPropertyCollection.GetDouble(string, [double?])`](#gtfspropertycollectiongetdoublestring-double)
  - [`GTFSPropertyCollection.GetDuration(string, [Duration?])`](#gtfspropertycollectiongetdurationstring-duration)
  - [`GTFSPropertyCollection.GetInt(string, [int?])`](#gtfspropertycollectiongetintstring-int)
  - [`GTFSPropertyCollection.GetNullableBool(string)`](#gtfspropertycollectiongetnullableboolstring)
  - [`GTFSPropertyCollection.GetNullableColor(string)`](#gtfspropertycollectiongetnullablecolorstring)
  - [`GTFSPropertyCollection.GetNullableDate(string)`](#gtfspropertycollectiongetnullabledatestring)
  - [`GTFSPropertyCollection.GetNullableDecimal(string)`](#gtfspropertycollectiongetnullabledecimalstring)
  - [`GTFSPropertyCollection.GetNullableDouble(string)`](#gtfspropertycollectiongetnullabledoublestring)
  - [`GTFSPropertyCollection.GetNullableDuration(string)`](#gtfspropertycollectiongetnullabledurationstring)
  - [`GTFSPropertyCollection.GetNullableInt(string)`](#gtfspropertycollectiongetnullableintstring)
  - [`GTFSPropertyCollection.GetNullableNonNegativeDecimal(string)`](#gtfspropertycollectiongetnullablenonnegativedecimalstring)
  - [`GTFSPropertyCollection.GetNullableNonNegativeDouble(string)`](#gtfspropertycollectiongetnullablenonnegativedoublestring)
  - [`GTFSPropertyCollection.GetNullableNonNegativeInt(string)`](#gtfspropertycollectiongetnullablenonnegativeintstring)
  - [`GTFSPropertyCollection.GetNullableTime(string)`](#gtfspropertycollectiongetnullabletimestring)
  - [`GTFSPropertyCollection.GetTime(string, [Duration?])`](#gtfspropertycollectiongettimestring-duration)
  - [`GTFSPropertyCollection.GetTimeZone(string)`](#gtfspropertycollectiongettimezonestring)
  - [`GTFSPropertyCollection.IsBool(string)`](#gtfspropertycollectionisboolstring)
  - [`GTFSPropertyCollection.IsColor(string)`](#gtfspropertycollectioniscolorstring)
  - [`GTFSPropertyCollection.IsDate(string)`](#gtfspropertycollectionisdatestring)
  - [`GTFSPropertyCollection.IsDecimal(string)`](#gtfspropertycollectionisdecimalstring)
  - [`GTFSPropertyCollection.IsDouble(string)`](#gtfspropertycollectionisdoublestring)
  - [`GTFSPropertyCollection.IsDuration(string)`](#gtfspropertycollectionisdurationstring)
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


## `AssertBool(string, string)`
`void`: Asserts that the input is a valid boolean (only `0` or `1`).

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid boolean.


## `AssertColor(string, string)`
`void`: Asserts that the input is a valid color.

To be a valid color, the input must be a six-hex digit code, *without* the leading `#` sign.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid color.


## `AssertDate(string, string)`
`void`: Asserts that the input is a valid date.

To be a valid date, the input must be in `YYYYMMDD` format, with no separators between the components.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid date.


## `AssertDecimal(string, string)`
`void`: Asserts that the input is a valid decimal.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid decimal.


## `AssertDouble(string, string)`
`void`: Asserts that the input is a valid double.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid double.


## `AssertDuration(string, string)`
`void`: Asserts that the input is a valid duration.

To be a valid duration, the input must be a non-negative number of seconds.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyRangeException`: `input` is a negative integer.
* `PropertyTypeException`: `input` isn't a valid duration.


## `AssertExists(string, string)`
`void`: Asserts that the input exists.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.


## `AssertForeignKey<T>(string, string, GTFSOrderedEntityCollection<T>)`
`void`: Asserts that a collection contains a given ID.

### Type parameters
* **`T`** (: `GTFSIdentifiedEntity`): The type of entity contained by the collection.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.
* `GTFSOrderedEntityCollection<T>` **`collection`**: The collection the ID should be within.

### Exceptions
* `PropertyNullException`: `input` is null. (Not thrown if `input` is an empty string and the collection has an empty string ID.)
* `PropertyForeignKeyException`: `input` doesn't match an ID in `collection`.


## `AssertForeignKey<T>(string, string, IDEntityCollection<T>)`
`void`: Asserts that a collection contains a given ID.

### Type parameters
* **`T`** (: `GTFSIdentifiedEntity`): The type of entity contained by the collection.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.
* `IDEntityCollection<T>` **`collection`**: The collection the ID should be within.

### Exceptions
* `PropertyNullException`: `input` is null. (Not thrown if `input` is an empty string and the collection has an empty string ID.)
* `PropertyForeignKeyException`: `input` doesn't match an ID in `collection`.


## `AssertInt(string, string)`
`void`: Asserts that the input is a valid integer.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid integer.


## `AssertNonNegativeDecimal(string, string)`
`void`: Asserts that the input is a valid non-negative decimal.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid decimal.
* `PropertyRangeException`: `input` is negative.


## `AssertNonNegativeDouble(string, string)`
`void`: Asserts that the input is a valid non-negative double.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid double.
* `PropertyRangeException`: `input` is negative.


## `AssertNonNegativeInt(string, string)`
`void`: Asserts that the input is a valid non-negative integer.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid integer.
* `PropertyRangeException`: `input` is negative.


## `AssertTime(string, string)`
`void`: Asserts that the input is a valid time.

To be a valid time, the input must be in `H:mm:ss` format.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid time.


## `AssertTimeZone(string, string)`
`void`: Asserts that the input is a valid time zone.

### Parameters
* `string` **`input`**: The input to check.
* `string` **`key`**: The property from which the input came.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid time zone.


## `GetBool(string)`
`bool`: Returns whether or not the input is `1`.

Returns `false` for any other input, even `null`.

### Parameters
* `string` **`input`**: The input to check.


## `GetColor(string, [Color?])`
`Color`: Returns a `Color`.

To be a valid color, the input must be a six-hex digit code, *without* the leading `#` sign.

### Parameters
* `string` **`input`**: The input to parse.
* `Color?` **`def`** (optional): Default to use if the input isn't a valid color.

### Exceptions
* `ArgumentException`: `input` is not a valid color, and no default is provided.


## `GetDate(string, [LocalDate?])`
`LocalDate`: Returns a `LocalDate`.

To be a valid date, the input must be in `YYYYMMDD` format, with no separators between the components.

### Parameters
* `string` **`input`**: The input to parse.
* `LocalDate?` **`def`** (optional): Default to use if the input isn't a valid date.

### Exceptions
* `Exception`: `input` is not a valid date, and no default is provided.


## `GetDuration(string, [Duration?])`
`Duration`: Converts the input (as a duration given in integer seconds) to a `Duration`.

### Parameters
* `string` **`input`**: The input to parse.
* `Duration?` **`def`** (optional): Default to use if the input isn't a valid duration.

### Excceptions
* `ArgumentException`: `input` is not a valid duration, and no default is provided.


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


## `GetNullableDuration(string)`
`Duration?`: Converts the input (as a duration given in integer seconds) to a `Duration`, if it's valid. Otherwise, returns `null`.

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


## `GetTime(string, [Duration?])`
`Duration`: Returns a `Duration`.

To be a valid time, the input must be in `H:mm:ss` or `HH:mm:ss` format.

### Parameters
* `string` **`input`**: The input to parse.
* `Duration?` **`def`** (optional): The default to use if the input isn't a valid time.

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


## `IsDuration(string)`
`bool`: Returns whether or not the input is a valid `Duration` (as given in integer seconds).

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


## `GTFSPropertyCollection.AssertBool(string)`
`void`: Asserts that the input is a valid boolean (only `0` or `1`).

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid boolean.


## `GTFSPropertyCollection.AssertColor(string)`
`void`: Asserts that the input is a valid color.

To be a valid color, the input must be a six-hex digit code, *without* the leading `#` sign.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid color.


## `GTFSPropertyCollection.AssertDate(string)`
`void`: Asserts that the input is a valid date.

To be a valid date, the input must be in `YYYYMMDD` format, with no separators between the components.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid date.


## `GTFSPropertyCollection.AssertDecimal(string)`
`void`: Asserts that the input is a valid decimal.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid decimal.


## `GTFSPropertyCollection.AssertDouble(string)`
`void`: Asserts that the input is a valid double.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid double.


## `GTFSPropertyCollection.AssertDuration(string)`
`void`: Asserts that the input is a valid duration.

To be a valid duration, the input must be a non-negative number of seconds.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyRangeException`: `input` is a negative integer.
* `PropertyTypeException`: `input` isn't a valid duration.


## `GTFSPropertyCollection.AssertExists(string)`
`void`: Asserts that the input exists.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.


## `GTFSPropertyCollection.AssertForeignKey<T>(string, GTFSOrderedEntityCollection<T>)`
`void`: Asserts that a collection contains a given ID.

### Type parameters
* **`T`** (: `GTFSIdentifiedEntity`): The type of entity contained by the collection.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.
* `GTFSOrderedEntityCollection<T>` **`collection`**: The collection the ID should be within.

### Exceptions
* `PropertyNullException`: `input` is null. (Not thrown if `input` is an empty string and the collection has an empty string ID.)
* `PropertyForeignKeyException`: `input` doesn't match an ID in `collection`.


## `GTFSPropertyCollection.AssertForeignKey<T>(string, IDEntityCollection<T>)`
`void`: Asserts that a collection contains a given ID.

### Type parameters
* **`T`** (: `GTFSIdentifiedEntity`): The type of entity contained by the collection.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.
* `IDEntityCollection<T>` **`collection`**: The collection the ID should be within.

### Exceptions
* `PropertyNullException`: `input` is null. (Not thrown if `input` is an empty string and the collection has an empty string ID.)
* `PropertyForeignKeyException`: `input` doesn't match an ID in `collection`.


## `GTFSPropertyCollection.AssertInt(string)`
`void`: Asserts that the input is a valid integer.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid integer.


## `GTFSPropertyCollection.AssertNonNegativeDecimal(string)`
`void`: Asserts that the input is a valid non-negative decimal.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid decimal.
* `PropertyRangeException`: `input` is negative.


## `GTFSPropertyCollection.AssertNonNegativeDouble(string)`
`void`: Asserts that the input is a valid non-negative double.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid double.
* `PropertyRangeException`: `input` is negative.


## `GTFSPropertyCollection.AssertNonNegativeInt(string)`
`void`: Asserts that the input is a valid non-negative integer.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid integer.
* `PropertyRangeException`: `input` is negative.


## `GTFSPropertyCollection.AssertTime(string)`
`void`: Asserts that the input is a valid time.

To be a valid time, the input must be in `H:mm:ss` format.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid time.


## `GTFSPropertyCollection.AssertTimeZone(string)`
`void`: Asserts that the input is a valid time zone.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to check from.
* `string` **`key`**: The key of the property to check.

### Exceptions
* `PropertyNullException`: `input` is null.
* `PropertyTypeException`: `input` isn't a valid time zone.


## `GTFSPropertyCollection.GetBool(string)`
`bool`: Returns whether or not the input is `1`.

Returns `false` for any other input, even `null`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.


## `GTFSPropertyCollection.GetColor(string, [Color?])`
`Color`: Returns a `Color`.

To be a valid color, the input must be a six-hex digit code, *without* the leading `#` sign.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `Color?` **`def`** (optional): Default to use if the input isn't a valid color.

### Exceptions
* `ArgumentException`: `input` is not a valid color, and no default is provided.


## `GTFSPropertyCollection.GetDate(string, [LocalDate?])`
`LocalDate`: Returns a `LocalDate`.

To be a valid date, the input must be in `YYYYMMDD` format, with no separators between the components.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `LocalDate?` **`def`** (optional): Default to use if the input isn't a valid date.

### Exceptions
* `Exception`: `input` is not a valid date, and no default is provided.


## `GTFSPropertyCollection.GetDecimal(string, [decimal?])`
`decimal`: Returns a `decimal`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `decimal?` **`def`** (optional): Default to use if the input isn't a valid number.

### Exceptions
* `ArgumentException`: `input` is not a valid number, and no default is provided.


## `GTFSPropertyCollection.GetDouble(string, [double?])`
`double`: Returns a `double`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `double?` **`def`** (optional): Default to use if the input isn't a valid number.

### Exceptions
* `ArgumentException`: `input` is not a valid number, and no default is provided.


## `GTFSPropertyCollection.GetDuration(string, [Duration?])`
`Duration`: Returns a `Duration`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `Duration?` **`def`** (optional): Default to use if the input isn't a valid duration.

### Exceptions
* `ArgumentException`: `input` is not a valid duration, and no default is provided.


## `GTFSPropertyCollection.GetInt(string, [int?])`
`int`: Returns an `int`.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `int?` **`def`** (optional): Default to use if the input isn't a valid number.

### Exceptions
* `ArgumentException`: `input` is not a valid number, and no default is provided.


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


## `GTFSPropertyCollection.GetNullableDuration(string)`
`Duration?`: Returns a `Duration` if the input is a valid integer number of seconds; otherwise, returns `null`.

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


## `GTFSPropertyCollection.GetTime(string, [Duration?])`
`Duration`: Returns a `Duration`.

To be a valid time, the input must be in `H:mm:ss` or `HH:mm:ss` format.

### Parameters
* this `GTFSPropertyCollection` **`properties`**: The property collection to parse from.
* `string` **`key`**: The key of the property to parse.
* `Duration?` **`def`** (optional): The default to use if the input isn't a valid time.

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


## `GTFSPropertyCollection.IsDuration(string)`
`bool`: Returns whether or not the input is a valid `Duration` (as given in integer seconds).

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
