```csharp
public abstract class FareAttribute : GTFSIdentifiedEntity
```

# Summary
A single fare class for riders. Can stand alone if it's the fare paid for all trips, or used in conjunction with `FareRule`s if there are more rules applied.

- [Summary](#summary)
- [Constructors](#constructors)
  - [`FareAttribute(GTFSPropertyCollection)`](#fareattributegtfspropertycollection)
- [Properties](#properties)
  - [`AgencyID`](#agencyid)
  - [`CurrencyType`](#currencytype)
  - [`ID`](#id)
  - [`this[string]`](#thisstring)
  - [`PaymentMethod`](#paymentmethod)
  - [`Price`](#price)
  - [`TransferDuration`](#transferduration)
  - [`Transfers`](#transfers)
  - [`Properties` (protected)](#properties-protected)



# Constructors


## `FareAttribute(GTFSPropertyCollection)`
Creates a new `FareAttribute` from the given properties.

### Parameters
* `GTFSPropertyCollection` **`properties`**: The properties to use.



# Properties


## `AgencyID`
Read-only `string`: The ID of the agency with which the fare is associated.

This is the value of the `agency_id` property of the entity.


## `CurrencyType`
Read-only `string`: The currency used to pay the fare.

Tihs is the value of the `currency_type` property of the entity.


## `ID`
Read-only `string`: The ID of the entity.

Identifies a fare class.

This is the value of the `fare_id` property of the entity.


## `this[string]`
Read-only `string`: Returns the given property of this entty, or `null` if no such property exists.


## `PaymentMethod`
Read-only `FarePaymentMethod`: Indicates when fare must be paid.

This is the value of the `payment_method` property of the entity.


## `Price`
Read-only `decimal`: Fare price.

This is the value of the `price` property of the entity, and is given in the unit specified by `CurrencyType`.


## `TransferDuration`
Read-only `Duration?`: Length of time before a transfer expires.

When `Transfers` == `0`, this field can be used to indicate how long a ticket is valid, or it can be left empty.

This is the value of the `transfer_duration` property of the entity.


## `Transfers`
Read-only `int?`: The number of times you may transfer on this fare.

This is the value of the `transfers` propety of the entity. `null` means that unlimited transfers are allowed.

The GTFS spec calls this property an enum with only the values of `null`, 0, 1, or 2; however, this library treats this property as an open-ended int that may cap at any value.


## `Properties` (protected)
`GTFSPropertyCollection`: The raw view of the properties of this entity.