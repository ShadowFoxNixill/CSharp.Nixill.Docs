```csharp
public class Calendar : GTFSIdentifiedEntity
```

# Summary
A `Calendar` is a set of dates when service is available for one or more routes.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`Calendar(GTFSPropertyCollection)`](#calendargtfspropertycollection)
- [Properties](#properties)
  - [`EndDate`](#enddate)
  - [`Friday`](#friday)
  - [`ID`](#id)
  - [`Mask`](#mask)
  - [`Monday`](#monday)
  - [`Saturday`](#saturday)
  - [`StartDate`](#startdate)
  - [`Sunday`](#sunday)
  - [`this[string]`](#thisstring)
  - [`Thursday`](#thursday)
  - [`Tuesday`](#tuesday)
  - [`Wednesday`](#wednesday)
  - [`Properties` (protected)](#properties-protected)
- [Methods](#methods)
  - [`DateInRange(LocalDate)`](#dateinrangelocaldate)
  - [`ServiceOn(LocalDate)`](#serviceonlocaldate)
  - [`ServiceOnDayOfWeek(IsoDayOfWeek)`](#serviceondayofweekisodayofweek)
  - [`Factory(IEnumerable<(string, string)>)` (static)](#factoryienumerablestring-string-static)



# Constructors


## `Calendar(GTFSPropertyCollection)`
Creates a new `Calendar` from the given properties.

### Parameters
* `GTFSPropertyCollection` **`properties`**: The properties to use.



# Properties


## `EndDate`
Read-only `LocalDate`: Final service day for the service interval.

This is the value of the `end_date` property of the entity. This service day is included in the inverval.


## `Friday`
Read-only `bool`: Indicates whether the service operates on all Fridays in the date range specified by `StartDate` and `EndDate`.

Exceptions on individual dates may be listed as `CalendarDate`s.

This is the value of the `friday` property of the entity, specifically returning whether or not that property has a value of `1`.


## `ID`
Read-only `string`: The ID of the entity.

This is the value of the `service_id` property of the entity.


## `Mask`
Read-only `byte`: Returns the days-of-week of service as a bitfield.

`0x1` is the value of `Monday`, `0x2` to `Tuesday`, etc. to `0x40` for `Sunday`.


## `Monday`
Read-only `bool`: Indicates whether the service operates on all Mondays in the date range specified by `StartDate` and `EndDate`.

Exceptions on individual dates may be listed as `CalendarDate`s.

This is the value of the `monday` property of the entity, specifically returning whether or not that property has a value of `1`.


## `Saturday`
Read-only `bool`: Indicates whether the service operates on all Saturdays in the date range specified by `StartDate` and `EndDate`.

Exceptions on individual dates may be listed as `CalendarDate`s.

This is the value of the `saturday` property of the entity, specifically returning whether or not that property has a value of `1`.


## `StartDate`
Read-only `LocalDate`: First service day for the service interval.

This is the value of the `start_date` property of the entity.


## `Sunday`
Read-only `bool`: Indicates whether the service operates on all Sundays in the date range specified by `StartDate` and `EndDate`.

Exceptions on individual dates may be listed as `CalendarDate`s.

This is the value of the `sunday` property of the entity, specifically returning whether or not that property has a value of `1`.


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `Thursday`
Read-only `bool`: Indicates whether the service operates on all Thursdays in the date range specified by `StartDate` and `EndDate`.

Exceptions on individual dates may be listed as `CalendarDate`s.

This is the value of the `thursday` property of the entity, specifically returning whether or not that property has a value of `1`.


## `Tuesday`
Read-only `bool`: Indicates whether the service operates on all Tuesdays in the date range specified by `StartDate` and `EndDate`.

Exceptions on individual dates may be listed as `CalendarDate`s.

This is the value of the `tuesday` property of the entity, specifically returning whether or not that property has a value of `1`.


## `Wednesday`
Read-only `bool`: Indicates whether the service operates on all Wednesdays in the date range specified by `StartDate` and `EndDate`.

Exceptions on individual dates may be listed as `CalendarDate`s.

This is the value of the `wednesday` property of the entity, specifically returning whether or not that property has a value of `1`.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.



# Methods


## `DateInRange(LocalDate)`
`bool`: Whether or not a given date is between the `StartDate` and `EndDate` of the `Calendar`.

### Parameters
* `LocalDate` **`date`**: The date to check for.


## `ServiceOn(LocalDate)`
`bool`: Whether or not there is service on the given date (`ServiceOnDayOfWeek` &amp;&amp; `DateInRange`).

This method only considers this `Calendar` entity without regard to any `CalendarDate`s that may change the result.

### Parameters
* `LocalDate` **`date`**: The date to check for.


## `ServiceOnDayOfWeek(IsoDayOfWeek)`
`bool`: Whether or not there exists service on a given day of the week.

### Parameters
* `IsoDayOfWeek` **`day`**: The day-of-week to check for.


## `Factory(IEnumerable<(string, string)>)` (static)
`Calendar`: Creates a new `Calendar`.

### Parameters
* `IEnumerable<(string, string)>` **`properties`**: The property collection