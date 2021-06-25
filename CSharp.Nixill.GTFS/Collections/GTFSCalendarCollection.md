```csharp
public class GTFSCalendarCollection : IReadOnlyCollection<(Calendar, IEnumerable<CalendarDate>)>
```



# Summary
A collection of all the `Calendar`s and `CalendarDate`s from within a GTFS feed.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`GTFSCalendarCollection(IGTFSDataSource, string, string)`](#gtfscalendarcollectionigtfsdatasource-string-string)
- [Properties](#properties)
  - [`CalendarDates`](#calendardates)
  - [`Calendars`](#calendars)
  - [`Count`](#count)
  - [`ServiceIds`](#serviceids)
  - [`this[string]`](#thisstring)
- [Methods](#methods)
  - [`GetEnumerator()`](#getenumerator)
- [Explicit Interface Implementations](#explicit-interface-implementations)
  - [`IEnumerable.GetEnumerator()`](#ienumerablegetenumerator)



# Constructors


## `GTFSCalendarCollection(IGTFSDataSource, string, string)`
Creates a `GTFSCalendarCollection` from a given `IGTFSDataSource` and the given table names.

### Parameters
* `IGTFSDataSource` **`source`**: The GTFS data source to use for this collection.
* `string` **`calendarTable`** (default `"calendar"`): The name of the calendar table from this source.
* `string` **`calendarDatesTable`** (default `"calendar_dates"`): The name of the calendar dates table from this source.



# Properties


## `CalendarDates`
Read-only `TwoKeyEntityCollection<string, LocalDate, CalendarDate>`: The collection of `CalendarDate`s within the feed data.


## `Calendars`
Read-only `IDEntityCollection<Calendar>`: The collection of `Calendar`s within the feed data.


## `Count`
Read-only `int`: The count of `ServiceIds`.


## `ServiceIds`
Read-only `IReadOnlyList<string>`: The collection of `service_id`s across both the `calendar` and `calendar_dates` tables.


## `this[string]`
Read-only `(Calendar, IEnumerable<CalendarDate>)`: Returns both the `Calendar` (possibly `null`) and set of `CalendarDate`s corresponding to the given service ID.



# Methods


## `GetEnumerator()`
`IEnumerator<(Calendar, IEnumerable<CalendarDate>)>`: Returns an enumerator that iterates through a collection.



# Explicit Interface Implementations


## `IEnumerable.GetEnumerator()`
`IEnumerator`: Returns an enumerator that iterates through a collection.