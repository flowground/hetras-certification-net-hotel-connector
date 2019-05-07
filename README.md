# ![LOGO](logo.png) hetras Hotel API Version 0 **flow**ground Connector

## Description

A generated **flow**ground connector for the hetras Hotel API Version 0 API (version v0).

Generated from: https://api.apis.guru/v2/specs/hetras-certification.net/hotel/v0/swagger.json<br/>
Generated at: 2019-05-07T17:42:18+03:00

## API Description



## Authorization

This API does not require authorization.

## Actions

### Get a list of all the hotels of a chain your application has access to.

> Load the details about all the hotels your application has access to.

*Tags:* `Hotels`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.

### Get the details of the hotel with the speccified hotel id.

> Load the details about the specified hotel.

*Tags:* `Hotels`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_

### Get a list of codes for the specified hotel either filtered by type or code.

> With this call you can find codes for a hotel by type or code. By default and without any filter criteria<br/>
>             defined it will return you all available codes.

*Tags:* `Codes`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id you are trying to find codes for.
* `code` - _optional_ - Return all results matching the specified code. A code is unique in combination with the type
            which means when you query for a code you could get multiple results each for a different type
* `type` - _optional_ - Return all codes for the specified type
    Possible values: GuestRequest, RequestDietary, VIPStatus, ReasonForRateChange, Regrets, MarketSegments, SourceOfBusiness, LoyaltyProgram, CancellationReason, AccountType, AccountRank, VIPLevel, Title, ContactFunction, Territory, CorrespondenceType, ExternalProgramType, RevenueBucket, AdditionalRevenueBucket, AdditionalStatisticsBuckets, MealPeriod, BillingCycle, ReminderCycle, MajorMarketSegments, DocumentType, ActivityType, ReservationLabels.

### Get all the details for a specific code available for the hotel.

> Read the details about a specific code available for the defined hotel.

*Tags:* `Codes`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id the code available for.
* `id` - _required_ - The code identifier you want to see details for.

### Get a list of rateplans for the specified hotel id matching the filter criteria.

> With this call you can find rateplans for a hotel by different filters. By default and without any filter criteria<br/>
>             defined it will return you all active rateplans.

*Tags:* `RatePlans`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id you are trying to find rateplans for.
* `sellingStatus` - _optional_ - Specify which rateplans to return. If you do not specify a value you will by default get active
            rateplans.
    Possible values: Active, Inactive, All.
* `commissionable` - _optional_ - Return all rateplans having commisionable status
* `group` - _optional_ - Return all rateplans belonging to the specified rateplan group
* `baseRateplan` - _optional_ - Return all rateplans having the specified rateplan as base rateplan
* `channelGroup` - _optional_ - Return all rateplans that are sold through at least one channel out of the specified channel group
* `channelCode` - _optional_ - Return all rateplans sold through the specified channel
* `marketCodes` - _optional_ - Return all rateplans having one of the specified values as a market code
* `roomTypes` - _optional_ - Return all rateplans by which at least one of the specified room types are sold
* `includedServices` - _optional_ - Return all rateplans having at least one of the specified services included
* `skip` - _optional_ - Amount of items to skip.
* `top` - _optional_ - Amount of items to select.
* `inlinecount` - _optional_ - Return total number of items for a given filter criteria.
    Possible values: None, AllPages.

### Get the count of all rateplans in the hotel matching the given filter criteria.

*Tags:* `RatePlans`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel you are counting the rateplans for.
* `sellingStatus` - _optional_ - Specify which rateplans to return. If you do not specify a value you will by default get active
            rateplans.
    Possible values: Active, Inactive, All.
* `commissionable` - _optional_ - Return all rateplans having commisionable status
* `group` - _optional_ - Return all rateplans belonging to the specified rateplan group
* `baseRateplan` - _optional_ - Return all rateplans having the specified rateplan as base rateplan
* `channelGroup` - _optional_ - Return all rateplans that are sold through at least one channel out of the specified channel group
* `channelCode` - _optional_ - Return all rateplans sold through the specified channel
* `marketCodes` - _optional_ - Return all rateplans having one of the specified values as a market code
* `roomTypes` - _optional_ - Return all rateplans by which at least one of the specified room types are sold
* `includedServices` - _optional_ - Return all rateplans having at least one of the specified services included

### Update a list of base rateplans for a given period and a given base price for single occupancy.

> Currently this call only allows to set the base price for non-derived rateplans if the rateplan<br/>
>             is active and already loaded for the specified time period.<br/>
>             <br /><br /><br/>
>             A request example:<br /><pre><br/>
>             [<br/>
>               {<br/>
>                 "rateplan": "STDN01", "from": "2018-01-01", "to": "2018-01-30", "base_price": 120.00<br/>
>               }<br/>
>             ]<br/>
>             </pre><br /><br/>
>             For more details on how the API responds to errors please check our documentation on <br/>
>             <a href="https://developer.hetras.com/docs/errors/" onfocus="this.blur()">Error Handling</a>.<br />

*Tags:* `RatePlans`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id the rateplan belongs to.

### Get all the details for a specific rateplan in the hotel.

> Read the details about a specific rateplan for the defined hotel.

*Tags:* `RatePlans`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id the rateplan belongs to.
* `rateplanCode` - _required_ - The code of the rateplan you want to see details for.

### Get the setup of the daily rates for a specific rateplan and a defined timeperiod.

> With this call you can read the daily rates setup including the cancellation policy and minimum guarantee per day for the<br/>
>             specified rateplan. You can specify a timeperiod to read the daily rates for. The rateplan needs to be active for at least<br/>
>             one business day in the defined time period and have rates loaded.

*Tags:* `RatePlans`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id the rateplan belongs to.
* `rateplanCode` - _required_ - The code of the rateplan you want to see details for.
* `expand` - _optional_ - You can expand the supplements per room type on demand. By default they are not shown.
    Possible values: RoomTypeSupplements.
* `from` - _required_ - Defines the last business day you would like to get rates for. The maximum time span between <i>from</i>'and <i>to</i>
            is limited to 365 days.
* `to` - _required_ - Defines the first business day you would like to get rates for.
* `skip` - _optional_ - Amount of items to skip.
* `top` - _optional_ - Amount of items to select.
* `inlinecount` - _optional_ - Return total number of items for a given filter criteria.
    Possible values: None, AllPages.

### Partially update a rate of the specified rateplan for the defined time period.

> The hetras API is using this <a href="https://developer.hetras.com/docs/patch" onfocus="this.blur()" target="_blank">Patch Specification</a><br/>
>             to partially update an existing resource. Currently this call only allows to set the base price for non-derived rateplans if the rateplan<br/>
>             is active and already loaded for the specified time period.<br/>
>             <br /><br /><br/>
>             A request example:<br /><pre><br/>
>             [<br/>
>               {<br/>
>                 "op": "replace", "path": "/base_price", "value": 120.00<br/>
>               }<br/>
>             ]<br/>
>             </pre><br /><br/>
>             For more details on how the API responds to errors please check our documentation on <br/>
>             <a href="https://developer.hetras.com/docs/errors/" onfocus="this.blur()">Error Handling</a>.<br />

*Tags:* `RatePlans`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id the rateplan belongs to.
* `rateplanCode` - _required_ - The code of the rateplan you want to update the daily rate details for.
* `from` - _required_ - Defines the last business day you would like to get rates for. The maximum time span between <i>from</i>'and <i>to</i>
            is limited to 365 days.
* `to` - _required_ - Defines the first business day you would like to get rates for.

### Get the count of all active and loaded daily rates for the defined rateplan in a specified time period.

*Tags:* `RatePlans`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id the rateplan belongs to.
* `rateplanCode` - _required_ - The code of the rateplan you want to count daily rates for.
* `from` - _required_ - Defines the last business day you would like to get rates for. The maximum time span between <i>from</i>'and <i>to</i>
            is limited to 365 days.
* `to` - _required_ - Defines the first business day you would like to get rates for.

### Get the setup of a daily rate for a specific business day and rateplan.

> Read the setup of the daily rate for the defined rateplan for that specific business day.

*Tags:* `RatePlans`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id the rateplan belongs to.
* `rateplanCode` - _required_ - The code of the rateplan you want to see details for.
* `businessDay` - _required_ - The business day you want to get the rate setup for.

### Partially update a rate of the specified rateplan for a defined business day.

> The hetras API is using this <a href="https://developer.hetras.com/docs/patch" onfocus="this.blur()" target="_blank">Patch Specification</a><br/>
>             to partially update an existing resource. Currently this call only allows to set the base price for non-derived rateplans if the rateplan<br/>
>             is active and already loaded for the specified business day.<br/>
>             <br /><br /><br/>
>             A request example:<br /><pre><br/>
>             [<br/>
>               {<br/>
>                 "op": "replace", "path": "/base_price", "value": 120.00<br/>
>               }<br/>
>             ]<br/>
>             </pre><br /><br/>
>             For more details on how the API responds to errors please check our documentation on <br/>
>             <a href="https://developer.hetras.com/docs/errors/" onfocus="this.blur()">Error Handling</a>.<br />

*Tags:* `RatePlans`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id the rateplan belongs to.
* `rateplanCode` - _required_ - The code of the rateplan you want to update the daily rate details for.
* `businessDay` - _required_ - The business day of the daily rate you want to update.

### Get a list with the details of all room types for for the specified hotel id.

> With this call you can load the details about a all available room types for the specified hotel.

*Tags:* `RoomTypes`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id the room type belongs to.

### Get all the details for a specific room type in the hotel.

> With this call you can load the details about a specific room type in the hotel.

*Tags:* `RoomTypes`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id the room type belongs to.
* `code` - _required_ - The code of the room type you want to see details for.

### Get a list of rooms using the provided filtering and pagination criteria.

> Find all rooms for the hotel that match the specified filter criteria. The filtering will be done based on the current state of<br/>
>             the rooms.

*Tags:* `Rooms`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel you are trying to find rooms for.
* `occupancy` - _optional_ - Return results only for rooms that have the given frontdesk ocuppancy status.
    Possible values: Occupied, Vacant.
* `conditions` - _optional_ - Return results only for rooms that have the given room condition status.
* `maintenances` - _optional_ - Return results only for rooms that have the given maintenance status.
* `roomTypes` - _optional_ - Return result only for rooms for the given room types. Allows to pass a comma-separated list of room types.
* `amenities` - _optional_ - Return result only for rooms having all of the given amenities. You can provide a comma seperated list of 
            amenity codes.
* `views` - _optional_ - Return result only for rooms having at least one of the specified views. You can provide a comma seperated list of 
            view codes.
* `locations` - _optional_ - Return result only for rooms having at least one of the specified locations. You can provide a comma seperated list of 
            location codes.
* `skip` - _optional_ - Amount of items to skip.
* `top` - _optional_ - Amount of items to select.
* `inlinecount` - _optional_ - Return total number of items for a given filter criteria.
    Possible values: None, AllPages.

### Get the count of all rooms in the hotel matching the given filter criteria.

*Tags:* `Rooms`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel you are counting the rooms for.
* `occupancy` - _optional_ - Return results only for rooms that have the given frontdesk ocuppancy status.
    Possible values: Occupied, Vacant.
* `conditions` - _optional_ - Return results only for rooms that have the given room condition status.
* `maintenances` - _optional_ - Return results only for rooms that have the given maintenance status.
* `roomTypes` - _optional_ - Return result only for rooms for the given room types. Allows to pass a comma-separated list of room types.
* `amenities` - _optional_ - Return result only for rooms having all of the given amenities. You can provide a comma seperated list of 
            amenity codes.
* `views` - _optional_ - Return result only for rooms having at least one of the specified views. You can provide a comma seperated list of 
            view codes.
* `locations` - _optional_ - Return result only for rooms having at least one of the specified locations. You can provide a comma seperated list of 
            location codes.

### Request available rooms using a given criteria.

*Tags:* `Rooms`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel you are looking for available rooms.
* `from` - _required_ - Rooms returned will not be assigned to a reservation or be under maintenance between this date
            and the specified to date. Still there could be departing reservations or ending maintenances
            for this date.
* `to` - _required_ - Rooms returned will not be assigned to a reservation or be under maintenance between the specified
            from date and this date. Still there could be arriving reservations or beginning maintenances
            for this date.
* `adults` - _optional_ - Specifies number of adults the returned rooms will have to be able to house. The default value is 1.
* `includeOutOfService` - _optional_ - Should rooms that are set OutOfService in the defined time period be returned as available. By default
            they are not.
* `roomTypes` - _optional_ - Return result only for rooms for the given room types. Allows to pass a comma-separated list of room types.
* `amenities` - _optional_ - Return result only for rooms having all of the given amenities. You can provide a comma seperated list of 
            amenity codes.
* `views` - _optional_ - Return result only for rooms having at least one of the specified views. You can provide a comma seperated list of 
            view codes.
* `locations` - _optional_ - Return result only for rooms having at least one of the specified locations. You can provide a comma seperated list of 
            location codes.
* `skip` - _optional_ - Amount of items to skip.
* `top` - _optional_ - Amount of items to select.
* `inlinecount` - _optional_ - Return total number of items for a given filter criteria.
    Possible values: None, AllPages.

### Get all the details for a specific room in the hotel.

> With this call you can load the details about a specific room in the hotel. It will show you the current status of the room.

*Tags:* `Rooms`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id the room belongs to.
* `roomNumber` - _required_ - The room number you want to see details for.

### Partially updates a room.

> The hetras API is using this <a href="https://developer.hetras.com/docs/patch" onfocus="this.blur()" target="_blank">Patch Specification</a><br/>
>             to partially update an existing resource. Currently this call only allows to modify condition and housekeeping occupancy status of the room.<br/>
>             <br /><br /><br/>
>             A request example:<br /><pre><br/>
>             [<br/>
>               {<br/>
>                 "op": "replace", "path": "/status/condition", "value": "CleanNotInspected"<br/>
>               }, {<br/>
>                 "op": "replace", "path": "/status/housekeeping_occupancy", "value": "Vacant"<br/>
>               }<br/>
>             ]<br/>
>             </pre><br /><br/>
>             For more details on how the API responds to errors please check our documentation on <br/>
>             <a href="https://developer.hetras.com/docs/errors/" onfocus="this.blur()">Error Handling</a>.<br />

*Tags:* `Rooms`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - The hotel id the room belongs to.
* `roomNumber` - _required_ - The room number of the room you would like to update.

### Saves Yieldable Rate Prices for existing Yieldable Rateplan.

> Saves Yieldable Rate Prices for existing Yieldable Rateplan. The rateplan has been created before and with this End Point we <br/>
>             create or update the rate prices. If the Yieldable rateplan prices exist it updates them with the new price if not it creates new price entries.<br /><br/>
>             For more details on how the API responds to errors please check our documentation on <br/>
>             <a href="https://developer.hetras.com/docs/errors/" onfocus="this.blur()">Error Handling</a>.

*Tags:* `YieldableRates`

#### Input Parameters
* `App-Id` - _required_ - Application identifier
* `App-Key` - _required_ - Application key.
* `hotelId` - _required_ - Specifies the hotelId which identifies Hotel for which the operation will be performed.
* `rateplanCode` - _required_ - Specifies the rateplanCode for which the operation will be performed.

## License

**flow**ground :- Telekom iPaaS / hetras-certification-net-hotel-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
