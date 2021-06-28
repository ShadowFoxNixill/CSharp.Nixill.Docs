```csharp
public class Agency : GTFSIdentifiedEntity
```

# Summary
Represents a transit agency from the feed.

- [Summary](#summary)
- [Remarks](#remarks)
- [Constructors](#constructors)
  - [`Agency(GTFSPropertyCollection)`](#agencygtfspropertycollection)
- [Properties](#properties)
  - [`Email`](#email)
  - [`FareUrl`](#fareurl)
  - [`ID`](#id)
  - [`Language`](#language)
  - [`Name`](#name)
  - [`PhoneNumber`](#phonenumber)
  - [`this[string]`](#thisstring)
  - [`TimeZone`](#timezone)
  - [`Url`](#url)
  - [`Properties` (protected)](#properties-protected)
- [Methods](#methods)
  - [`Factory(IEnumerable<(string, string)>)` (static)](#factoryienumerablestring-string-static)



# Remarks
The ID of an <c>Agency</c> is its <c>agency_id</c>. As stated in the [GTFS documentation](gtfs.org/reference/static#agencytxt) (slightly modified for grammar):

> Identifies a transit brand, which is often synonymous with a transit agency. Note that in some cases, such as when a single agency operates multiple separate services, agencies and brands are distinct. This document uses the term "agency" in place of "brand". A dataset may contain data from multiple agencies. This field is required when the dataset contains data for multiple transit agencies, otherwise it is optional.



# Constructors


## `Agency(GTFSPropertyCollection)`
Creates a new `Agency` from the given properties.

### Parameters
* `GTFSPropertyCollection` **`properties`**: The properties to use.



# Properties


## `Email`
Read-only `string`: Email address actively monitored by the agency's customer service department.

This is the value of the `agency_email` property of the entity. This email address should be a direct contact point where transit riders can reach a customer service representative at the agency.


## `FareUrl`
Read-only `string`: URL of a web page that allows a rider to purchase tickets or other fare instruments for that agency online.

This is the value of the `agency_fare_url` property of the entity.


## `ID`
Read-only `string`: The ID of the entity.

This is the value of the `agency_id` property of the entity.


## `Language`
Read-only string: Primary language used by this transit agency.

This is the value of the `agency_lang` property of the entity. This field helps GTFS consumers choose capitalization rules and other language-specific settings for the dataset.


## `Name`
Read-only `string`: The full name of the agency.

This is the value of the `agency_name` property of the entity.


## `PhoneNumber`
Read-only `string`: A voice telephone number for the specified agency.

This is the value of the `agency_phone` property of the entity. This field is a string value that presents the telephone number as typical for the agency's service area. It can and should contain punctuation marks to group the digits of the number. Dialable text (for example, TriMet's `503-238-RIDE`) is permitted, but the field must not contain any other descriptive text.


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `TimeZone`
Read-only `DateTimeZone`: Timezone where the transit agency is located.

This is the value of the `agency_timezone` property of the entity. If multiple agencies are specified in the dataset, each must have the same TimeZone.


## `Url`
Read-only `string`: The URL of the agency's website.

This is the value of the `agency_url` property of the entity.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.



# Methods


## `Factory(IEnumerable<(string, string)>)` (static)
`Agency`: Creates a new `Agency`.

### Parameters
* `IEnumerable<(string, string)>` **`properties`**: The property collection.