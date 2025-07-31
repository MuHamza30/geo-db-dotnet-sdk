# Geo

Geo Endpoints

```csharp
GeoController geoController = client.GeoController;
```

## Class Name

`GeoController`

## Methods

* [Find Admin Divisions Using GET](../../doc/controllers/geo.md#find-admin-divisions-using-get)
* [Get Admin Division Using GET](../../doc/controllers/geo.md#get-admin-division-using-get)
* [Find Cities Near Admin Division Using GET](../../doc/controllers/geo.md#find-cities-near-admin-division-using-get)
* [Find Divisions Near Admin Division Using GET](../../doc/controllers/geo.md#find-divisions-near-admin-division-using-get)
* [Find Cities Using GET](../../doc/controllers/geo.md#find-cities-using-get)
* [Get City Using GET](../../doc/controllers/geo.md#get-city-using-get)
* [Get City Date Time Using GET](../../doc/controllers/geo.md#get-city-date-time-using-get)
* [Get City Distance Using GET](../../doc/controllers/geo.md#get-city-distance-using-get)
* [Get City Located in Using GET](../../doc/controllers/geo.md#get-city-located-in-using-get)
* [Find Cities Near City Using GET](../../doc/controllers/geo.md#find-cities-near-city-using-get)
* [Get City Time Using GET](../../doc/controllers/geo.md#get-city-time-using-get)
* [Get Countries Using GET](../../doc/controllers/geo.md#get-countries-using-get)
* [Get Country Using GET](../../doc/controllers/geo.md#get-country-using-get)
* [Get Regions Using GET](../../doc/controllers/geo.md#get-regions-using-get)
* [Get Region Using GET](../../doc/controllers/geo.md#get-region-using-get)
* [Find Region Divisions Using GET](../../doc/controllers/geo.md#find-region-divisions-using-get)
* [Find Region Cities Using GET](../../doc/controllers/geo.md#find-region-cities-using-get)
* [Find Cities Near Location Using GET](../../doc/controllers/geo.md#find-cities-near-location-using-get)
* [Find Divisions Near Location Using GET](../../doc/controllers/geo.md#find-divisions-near-location-using-get)


# Find Admin Divisions Using GET

Find administrative divisions, filtering by optional criteria. If no criteria are set, you will get back all
known divisions.

```csharp
FindAdminDivisionsUsingGETAsync(
    string location = null,
    int? radius = null,
    string distanceUnit = "MI",
    string countryIds = null,
    string excludedCountryIds = null,
    int? minPopulation = null,
    int? maxPopulation = null,
    string namePrefix = null,
    bool? namePrefixDefaultLangResults = true,
    string timeZoneIds = null,
    bool? asciiMode = false,
    bool? hateoasMode = true,
    string languageCode = null,
    int? limit = 10,
    int? offset = 0,
    string sort = null,
    string includeDeleted = "NONE")
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `location` | `string` | Query, Optional | Only places near this location. Latitude/longitude in ISO-6709 format: ±DD.DDDD±DDD.DDDD |
| `radius` | `int?` | Query, Optional | The location radius within which to find places |
| `distanceUnit` | `string` | Query, Optional | The unit of distance: MI \| KM<br><br>**Default**: `"MI"` |
| `countryIds` | `string` | Query, Optional | Only places in these countries (comma-delimited country codes or WikiData ids) |
| `excludedCountryIds` | `string` | Query, Optional | Only places NOT in these countries (comma-delimited country codes or WikiData ids) |
| `minPopulation` | `int?` | Query, Optional | Only places having at least this population |
| `maxPopulation` | `int?` | Query, Optional | Only places having no more than this population |
| `namePrefix` | `string` | Query, Optional | Only entities whose names start with this prefix. If languageCode is set, the prefix will be matched on the name<br>as it appears in that language. |
| `namePrefixDefaultLangResults` | `bool?` | Query, Optional | When name-prefix matching, whether or not to match on names in the default language if a non-default languageCode is set.<br><br>**Default**: `true` |
| `timeZoneIds` | `string` | Query, Optional | Only places in these time-zones (comma-delimited) |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `languageCode` | `string` | Query, Optional | Display results in this language |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |
| `sort` | `string` | Query, Optional | How to sort places.<br>Format: ±SORT_FIELD,±SORT_FIELD<br>where SORT_FIELD = countryCode \| elevation \| name \| population |
| `includeDeleted` | `string` | Query, Optional | Whether to include any divisions marked deleted: ALL \| SINCE_YESTERDAY \| SINCE_LAST_WEEK \| NONE<br><br>**Default**: `"NONE"` |

## Response Type

[`Task<Models.PopulatedPlacesResponse>`](../../doc/models/populated-places-response.md)

## Example Usage

```csharp
string distanceUnit = "MI";
bool? namePrefixDefaultLangResults = true;
bool? asciiMode = false;
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
string includeDeleted = "NONE";
try
{
    PopulatedPlacesResponse result = await geoController.FindAdminDivisionsUsingGETAsync(
        null,
        null,
        distanceUnit,
        null,
        null,
        null,
        null,
        null,
        namePrefixDefaultLangResults,
        null,
        asciiMode,
        hateoasMode,
        null,
        limit,
        offset,
        null,
        includeDeleted
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Get Admin Division Using GET

Get the details for a specific administrative division, including location coordinates, population, and
elevation above sea-level (if available).

```csharp
GetAdminDivisionUsingGETAsync(
    string divisionId,
    bool? asciiMode = false,
    string languageCode = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `divisionId` | `string` | Template, Required | An admin-division id (either native 'id' or 'wikiDataId') |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `languageCode` | `string` | Query, Optional | Display results in this language |

## Response Type

[`Task<Models.PopulatedPlaceResponse>`](../../doc/models/populated-place-response.md)

## Example Usage

```csharp
string divisionId = "divisionId2";
bool? asciiMode = false;
try
{
    PopulatedPlaceResponse result = await geoController.GetAdminDivisionUsingGETAsync(
        divisionId,
        asciiMode
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Find Cities Near Admin Division Using GET

Find cities near the given administrative division, filtering by optional criteria. If no criteria are set, you
will get back all known cities.

```csharp
FindCitiesNearAdminDivisionUsingGETAsync(
    string divisionId,
    int? radius = null,
    string distanceUnit = "MI",
    string countryIds = null,
    string excludedCountryIds = null,
    int? minPopulation = null,
    int? maxPopulation = null,
    string namePrefix = null,
    bool? namePrefixDefaultLangResults = true,
    string timeZoneIds = null,
    string types = null,
    bool? asciiMode = false,
    bool? hateoasMode = true,
    string languageCode = null,
    int? limit = 10,
    int? offset = 0,
    string sort = null,
    string includeDeleted = "NONE")
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `divisionId` | `string` | Template, Required | An admin-division id (either native 'id' or 'wikiDataId') |
| `radius` | `int?` | Query, Optional | The location radius within which to find places |
| `distanceUnit` | `string` | Query, Optional | The unit of distance: MI \| KM<br><br>**Default**: `"MI"` |
| `countryIds` | `string` | Query, Optional | Only places in these countries (comma-delimited country codes or WikiData ids) |
| `excludedCountryIds` | `string` | Query, Optional | Only places NOT in these countries (comma-delimited country codes or WikiData ids) |
| `minPopulation` | `int?` | Query, Optional | Only places having at least this population |
| `maxPopulation` | `int?` | Query, Optional | Only places having no more than this population |
| `namePrefix` | `string` | Query, Optional | Only entities whose names start with this prefix. If languageCode is set, the prefix will be matched on the name<br>as it appears in that language. |
| `namePrefixDefaultLangResults` | `bool?` | Query, Optional | When name-prefix matching, whether or not to match on names in the default language if a non-default languageCode is set.<br><br>**Default**: `true` |
| `timeZoneIds` | `string` | Query, Optional | Only places in these time-zones (comma-delimited) |
| `types` | `string` | Query, Optional | Only places for these types (comma-delimited): CITY \| ADM2 |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `languageCode` | `string` | Query, Optional | Display results in this language |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |
| `sort` | `string` | Query, Optional | How to sort places.<br>Format: ±SORT_FIELD,±SORT_FIELD<br>where SORT_FIELD = countryCode \| elevation \| name \| population |
| `includeDeleted` | `string` | Query, Optional | Whether to include any divisions marked deleted: ALL \| SINCE_YESTERDAY \| SINCE_LAST_WEEK \| NONE<br><br>**Default**: `"NONE"` |

## Response Type

[`Task<Models.PopulatedPlacesResponse>`](../../doc/models/populated-places-response.md)

## Example Usage

```csharp
string divisionId = "divisionId2";
string distanceUnit = "MI";
bool? namePrefixDefaultLangResults = true;
bool? asciiMode = false;
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
string includeDeleted = "NONE";
try
{
    PopulatedPlacesResponse result = await geoController.FindCitiesNearAdminDivisionUsingGETAsync(
        divisionId,
        null,
        distanceUnit,
        null,
        null,
        null,
        null,
        null,
        namePrefixDefaultLangResults,
        null,
        null,
        asciiMode,
        hateoasMode,
        null,
        limit,
        offset,
        null,
        includeDeleted
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Find Divisions Near Admin Division Using GET

Find administrative divisions near the given origin division, filtering by optional criteria. If no criteria
are set, you will get back all known divisions.

```csharp
FindDivisionsNearAdminDivisionUsingGETAsync(
    string divisionId,
    int? radius = null,
    string distanceUnit = "MI",
    string countryIds = null,
    string excludedCountryIds = null,
    int? minPopulation = null,
    int? maxPopulation = null,
    string namePrefix = null,
    bool? namePrefixDefaultLangResults = true,
    string timeZoneIds = null,
    bool? asciiMode = false,
    bool? hateoasMode = true,
    string languageCode = null,
    int? limit = 10,
    int? offset = 0,
    string sort = null,
    string includeDeleted = "NONE")
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `divisionId` | `string` | Template, Required | An admin-division id (either native 'id' or 'wikiDataId') |
| `radius` | `int?` | Query, Optional | The location radius within which to find places |
| `distanceUnit` | `string` | Query, Optional | The unit of distance: MI \| KM<br><br>**Default**: `"MI"` |
| `countryIds` | `string` | Query, Optional | Only places in these countries (comma-delimited country codes or WikiData ids) |
| `excludedCountryIds` | `string` | Query, Optional | Only places NOT in these countries (comma-delimited country codes or WikiData ids) |
| `minPopulation` | `int?` | Query, Optional | Only places having at least this population |
| `maxPopulation` | `int?` | Query, Optional | Only places having no more than this population |
| `namePrefix` | `string` | Query, Optional | Only entities whose names start with this prefix. If languageCode is set, the prefix will be matched on the name<br>as it appears in that language. |
| `namePrefixDefaultLangResults` | `bool?` | Query, Optional | When name-prefix matching, whether or not to match on names in the default language if a non-default languageCode is set.<br><br>**Default**: `true` |
| `timeZoneIds` | `string` | Query, Optional | Only places in these time-zones (comma-delimited) |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `languageCode` | `string` | Query, Optional | Display results in this language |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |
| `sort` | `string` | Query, Optional | How to sort places.<br>Format: ±SORT_FIELD,±SORT_FIELD<br>where SORT_FIELD = countryCode \| elevation \| name \| population |
| `includeDeleted` | `string` | Query, Optional | Whether to include any divisions marked deleted: ALL \| SINCE_YESTERDAY \| SINCE_LAST_WEEK \| NONE<br><br>**Default**: `"NONE"` |

## Response Type

[`Task<Models.PopulatedPlacesResponse>`](../../doc/models/populated-places-response.md)

## Example Usage

```csharp
string divisionId = "divisionId2";
string distanceUnit = "MI";
bool? namePrefixDefaultLangResults = true;
bool? asciiMode = false;
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
string includeDeleted = "NONE";
try
{
    PopulatedPlacesResponse result = await geoController.FindDivisionsNearAdminDivisionUsingGETAsync(
        divisionId,
        null,
        distanceUnit,
        null,
        null,
        null,
        null,
        null,
        namePrefixDefaultLangResults,
        null,
        asciiMode,
        hateoasMode,
        null,
        limit,
        offset,
        null,
        includeDeleted
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Find Cities Using GET

Find cities, filtering by optional criteria. If no criteria are set, you will get back all known cities.

```csharp
FindCitiesUsingGETAsync(
    string location = null,
    int? radius = null,
    string distanceUnit = "MI",
    string countryIds = null,
    string excludedCountryIds = null,
    int? minPopulation = null,
    int? maxPopulation = null,
    string namePrefix = null,
    bool? namePrefixDefaultLangResults = true,
    string timeZoneIds = null,
    string types = null,
    bool? asciiMode = false,
    bool? hateoasMode = true,
    string languageCode = null,
    int? limit = 10,
    int? offset = 0,
    string sort = null,
    string includeDeleted = "NONE")
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `location` | `string` | Query, Optional | Only places near this location. Latitude/longitude in ISO-6709 format: ±DD.DDDD±DDD.DDDD |
| `radius` | `int?` | Query, Optional | The location radius within which to find places |
| `distanceUnit` | `string` | Query, Optional | The unit of distance: MI \| KM<br><br>**Default**: `"MI"` |
| `countryIds` | `string` | Query, Optional | Only places in these countries (comma-delimited country codes or WikiData ids) |
| `excludedCountryIds` | `string` | Query, Optional | Only places NOT in these countries (comma-delimited country codes or WikiData ids) |
| `minPopulation` | `int?` | Query, Optional | Only places having at least this population |
| `maxPopulation` | `int?` | Query, Optional | Only places having no more than this population |
| `namePrefix` | `string` | Query, Optional | Only entities whose names start with this prefix. If languageCode is set, the prefix will be matched on the name<br>as it appears in that language. |
| `namePrefixDefaultLangResults` | `bool?` | Query, Optional | When name-prefix matching, whether or not to match on names in the default language if a non-default languageCode is set.<br><br>**Default**: `true` |
| `timeZoneIds` | `string` | Query, Optional | Only places in these time-zones (comma-delimited) |
| `types` | `string` | Query, Optional | Only places for these types (comma-delimited): CITY \| ADM2 |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `languageCode` | `string` | Query, Optional | Display results in this language |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |
| `sort` | `string` | Query, Optional | How to sort places.<br>Format: ±SORT_FIELD,±SORT_FIELD<br>where SORT_FIELD = countryCode \| elevation \| name \| population |
| `includeDeleted` | `string` | Query, Optional | Whether to include any divisions marked deleted: ALL \| SINCE_YESTERDAY \| SINCE_LAST_WEEK \| NONE<br><br>**Default**: `"NONE"` |

## Response Type

[`Task<Models.PopulatedPlacesResponse>`](../../doc/models/populated-places-response.md)

## Example Usage

```csharp
string distanceUnit = "MI";
bool? namePrefixDefaultLangResults = true;
bool? asciiMode = false;
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
string includeDeleted = "NONE";
try
{
    PopulatedPlacesResponse result = await geoController.FindCitiesUsingGETAsync(
        null,
        null,
        distanceUnit,
        null,
        null,
        null,
        null,
        null,
        namePrefixDefaultLangResults,
        null,
        null,
        asciiMode,
        hateoasMode,
        null,
        limit,
        offset,
        null,
        includeDeleted
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Get City Using GET

Get the details for a specific city, including location coordinates, population, and elevation above sea-level
(if available).

```csharp
GetCityUsingGETAsync(
    string cityId,
    bool? asciiMode = false,
    string languageCode = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cityId` | `string` | Template, Required | A city id (either native 'id' or 'wikiDataId') |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `languageCode` | `string` | Query, Optional | Display results in this language |

## Response Type

[`Task<Models.PopulatedPlaceResponse>`](../../doc/models/populated-place-response.md)

## Example Usage

```csharp
string cityId = "cityId4";
bool? asciiMode = false;
try
{
    PopulatedPlaceResponse result = await geoController.GetCityUsingGETAsync(
        cityId,
        asciiMode
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Get City Date Time Using GET

Get city date-time

```csharp
GetCityDateTimeUsingGETAsync(
    string cityId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cityId` | `string` | Template, Required | A city id (either native 'id' or 'wikiDataId') |

## Response Type

[`Task<Models.DateTimeResponse>`](../../doc/models/date-time-response.md)

## Example Usage

```csharp
string cityId = "cityId4";
try
{
    DateTimeResponse result = await geoController.GetCityDateTimeUsingGETAsync(cityId);
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Get City Distance Using GET

Get distance from the given city

```csharp
GetCityDistanceUsingGETAsync(
    string cityId,
    string toCityId,
    string distanceUnit = "MI")
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cityId` | `string` | Template, Required | A city id (either native 'id' or 'wikiDataId') |
| `toCityId` | `string` | Query, Required | Distance to this city |
| `distanceUnit` | `string` | Query, Optional | The unit of distance: MI \| KM<br><br>**Default**: `"MI"` |

## Response Type

[`Task<Models.DistanceResponse>`](../../doc/models/distance-response.md)

## Example Usage

```csharp
string cityId = "cityId4";
string toCityId = "toCityId8";
string distanceUnit = "MI";
try
{
    DistanceResponse result = await geoController.GetCityDistanceUsingGETAsync(
        cityId,
        toCityId,
        distanceUnit
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Get City Located in Using GET

Get the details for the containing populated place (e.g., its county or other administrative division), including location coordinates, population, and elevation above sea-level
(if available).

```csharp
GetCityLocatedInUsingGETAsync(
    string cityId,
    bool? asciiMode = false,
    string languageCode = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cityId` | `string` | Template, Required | A city id (either native 'id' or 'wikiDataId') |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `languageCode` | `string` | Query, Optional | Display results in this language |

## Response Type

[`Task<Models.PopulatedPlaceResponse>`](../../doc/models/populated-place-response.md)

## Example Usage

```csharp
string cityId = "cityId4";
bool? asciiMode = false;
try
{
    PopulatedPlaceResponse result = await geoController.GetCityLocatedInUsingGETAsync(
        cityId,
        asciiMode
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Find Cities Near City Using GET

Find cities near the given origin city, filtering by optional criteria. If no criteria are set, you will get
back all known cities.

```csharp
FindCitiesNearCityUsingGETAsync(
    string cityId,
    int? radius = null,
    string distanceUnit = "MI",
    string countryIds = null,
    string excludedCountryIds = null,
    int? minPopulation = null,
    int? maxPopulation = null,
    string namePrefix = null,
    bool? namePrefixDefaultLangResults = true,
    string timeZoneIds = null,
    string types = null,
    bool? asciiMode = false,
    bool? hateoasMode = true,
    string languageCode = null,
    int? limit = 10,
    int? offset = 0,
    string sort = null,
    string includeDeleted = "NONE")
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cityId` | `string` | Template, Required | A city id (either native 'id' or 'wikiDataId') |
| `radius` | `int?` | Query, Optional | The location radius within which to find places |
| `distanceUnit` | `string` | Query, Optional | The unit of distance: MI \| KM<br><br>**Default**: `"MI"` |
| `countryIds` | `string` | Query, Optional | Only places in these countries (comma-delimited country codes or WikiData ids) |
| `excludedCountryIds` | `string` | Query, Optional | Only places NOT in these countries (comma-delimited country codes or WikiData ids) |
| `minPopulation` | `int?` | Query, Optional | Only places having at least this population |
| `maxPopulation` | `int?` | Query, Optional | Only places having no more than this population |
| `namePrefix` | `string` | Query, Optional | Only entities whose names start with this prefix. If languageCode is set, the prefix will be matched on the name<br>as it appears in that language. |
| `namePrefixDefaultLangResults` | `bool?` | Query, Optional | When name-prefix matching, whether or not to match on names in the default language if a non-default languageCode is set.<br><br>**Default**: `true` |
| `timeZoneIds` | `string` | Query, Optional | Only places in these time-zones (comma-delimited) |
| `types` | `string` | Query, Optional | Only places for these types (comma-delimited): CITY \| ADM2 |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `languageCode` | `string` | Query, Optional | Display results in this language |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |
| `sort` | `string` | Query, Optional | How to sort places.<br>Format: ±SORT_FIELD,±SORT_FIELD<br>where SORT_FIELD = countryCode \| elevation \| name \| population |
| `includeDeleted` | `string` | Query, Optional | Whether to include any divisions marked deleted: ALL \| SINCE_YESTERDAY \| SINCE_LAST_WEEK \| NONE<br><br>**Default**: `"NONE"` |

## Response Type

[`Task<Models.PopulatedPlacesResponse>`](../../doc/models/populated-places-response.md)

## Example Usage

```csharp
string cityId = "cityId4";
string distanceUnit = "MI";
bool? namePrefixDefaultLangResults = true;
bool? asciiMode = false;
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
string includeDeleted = "NONE";
try
{
    PopulatedPlacesResponse result = await geoController.FindCitiesNearCityUsingGETAsync(
        cityId,
        null,
        distanceUnit,
        null,
        null,
        null,
        null,
        null,
        namePrefixDefaultLangResults,
        null,
        null,
        asciiMode,
        hateoasMode,
        null,
        limit,
        offset,
        null,
        includeDeleted
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Get City Time Using GET

Get city time

```csharp
GetCityTimeUsingGETAsync(
    string cityId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `cityId` | `string` | Template, Required | A city id (either native 'id' or 'wikiDataId') |

## Response Type

[`Task<Models.TimeResponse>`](../../doc/models/time-response.md)

## Example Usage

```csharp
string cityId = "cityId4";
try
{
    TimeResponse result = await geoController.GetCityTimeUsingGETAsync(cityId);
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Get Countries Using GET

Find countries, filtering by optional criteria. If no criteria are set, you will get back all known countries.

```csharp
GetCountriesUsingGETAsync(
    string currencyCode = null,
    string namePrefix = null,
    bool? namePrefixDefaultLangResults = true,
    bool? asciiMode = false,
    bool? hateoasMode = true,
    string languageCode = null,
    int? limit = 10,
    int? offset = 0,
    string sort = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `currencyCode` | `string` | Query, Optional | Only countries supporting this currency |
| `namePrefix` | `string` | Query, Optional | Only entities whose names start with this prefix. If languageCode is set, the prefix will be matched on the name<br>as it appears in that language. |
| `namePrefixDefaultLangResults` | `bool?` | Query, Optional | When name-prefix matching, whether or not to match on names in the default language if a non-default languageCode is set.<br><br>**Default**: `true` |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `languageCode` | `string` | Query, Optional | Display results in this language |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |
| `sort` | `string` | Query, Optional | How to sort countries.<br>Format: ±SORT_FIELD<br>where SORT_FIELD = code \| name |

## Response Type

[`Task<Models.CountriesResponse>`](../../doc/models/countries-response.md)

## Example Usage

```csharp
bool? namePrefixDefaultLangResults = true;
bool? asciiMode = false;
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
try
{
    CountriesResponse result = await geoController.GetCountriesUsingGETAsync(
        null,
        null,
        namePrefixDefaultLangResults,
        asciiMode,
        hateoasMode,
        null,
        limit,
        offset
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Get Country Using GET

Get the details for a specific country, including number of regions.

```csharp
GetCountryUsingGETAsync(
    string countryId,
    bool? asciiMode = false,
    string languageCode = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `countryId` | `string` | Template, Required | An ISO-3166 country code or WikiData id |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `languageCode` | `string` | Query, Optional | Display results in this language |

## Response Type

[`Task<Models.CountryResponse>`](../../doc/models/country-response.md)

## Example Usage

```csharp
string countryId = "countryId6";
bool? asciiMode = false;
try
{
    CountryResponse result = await geoController.GetCountryUsingGETAsync(
        countryId,
        asciiMode
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Get Regions Using GET

Get all regions in a specific country. These could be states, provinces, districts, or otherwise major
political divisions.

```csharp
GetRegionsUsingGETAsync(
    string countryId,
    string namePrefix = null,
    bool? namePrefixDefaultLangResults = true,
    bool? asciiMode = false,
    bool? hateoasMode = true,
    string languageCode = null,
    int? limit = 10,
    int? offset = 0,
    string sort = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `countryId` | `string` | Template, Required | An ISO-3166 country code or WikiData id |
| `namePrefix` | `string` | Query, Optional | Only entities whose names start with this prefix. If languageCode is set, the prefix will be matched on the name<br>as it appears in that language. |
| `namePrefixDefaultLangResults` | `bool?` | Query, Optional | When name-prefix matching, whether or not to match on names in the default language if a non-default languageCode is set.<br><br>**Default**: `true` |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `languageCode` | `string` | Query, Optional | Display results in this language |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |
| `sort` | `string` | Query, Optional | How to sort regions.<br>Format: ±SORT_FIELD<br>where SORT_FIELD = fipsCode \| isoCode \| name |

## Response Type

[`Task<Models.CountryRegionsResponse>`](../../doc/models/country-regions-response.md)

## Example Usage

```csharp
string countryId = "countryId6";
bool? namePrefixDefaultLangResults = true;
bool? asciiMode = false;
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
try
{
    CountryRegionsResponse result = await geoController.GetRegionsUsingGETAsync(
        countryId,
        null,
        namePrefixDefaultLangResults,
        asciiMode,
        hateoasMode,
        null,
        limit,
        offset
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Get Region Using GET

Get the details of a specific country region, including number of cities.

```csharp
GetRegionUsingGETAsync(
    string countryId,
    string regionCode,
    bool? asciiMode = false,
    string languageCode = null)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `countryId` | `string` | Template, Required | An ISO-3166 country code or WikiData id |
| `regionCode` | `string` | Template, Required | An ISO-3166 or FIPS region code |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `languageCode` | `string` | Query, Optional | Display results in this language |

## Response Type

[`Task<Models.CountryRegionResponse>`](../../doc/models/country-region-response.md)

## Example Usage

```csharp
string countryId = "countryId6";
string regionCode = "regionCode4";
bool? asciiMode = false;
try
{
    CountryRegionResponse result = await geoController.GetRegionUsingGETAsync(
        countryId,
        regionCode,
        asciiMode
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Find Region Divisions Using GET

Get the administrative divisions in a specific country region. The country and region info is omitted in the
response.

```csharp
FindRegionDivisionsUsingGETAsync(
    string countryId,
    string regionCode,
    int? minPopulation = null,
    int? maxPopulation = null,
    string namePrefix = null,
    bool? namePrefixDefaultLangResults = true,
    string timeZoneIds = null,
    bool? asciiMode = false,
    bool? hateoasMode = true,
    string languageCode = null,
    int? limit = 10,
    int? offset = 0,
    string sort = null,
    string includeDeleted = "NONE")
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `countryId` | `string` | Template, Required | An ISO-3166 country code or WikiData id |
| `regionCode` | `string` | Template, Required | An ISO-3166 or FIPS region code |
| `minPopulation` | `int?` | Query, Optional | Only places having at least this population |
| `maxPopulation` | `int?` | Query, Optional | Only places having no more than this population |
| `namePrefix` | `string` | Query, Optional | Only entities whose names start with this prefix. If languageCode is set, the prefix will be matched on the name<br>as it appears in that language. |
| `namePrefixDefaultLangResults` | `bool?` | Query, Optional | When name-prefix matching, whether or not to match on names in the default language if a non-default languageCode is set.<br><br>**Default**: `true` |
| `timeZoneIds` | `string` | Query, Optional | Only places in these time-zones (comma-delimited) |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `languageCode` | `string` | Query, Optional | Display results in this language |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |
| `sort` | `string` | Query, Optional | How to sort place results.<br>'Format: ±SORT_FIELD,±SORT_FIELD'<br>where SORT_FIELD = elevation \| name \| population |
| `includeDeleted` | `string` | Query, Optional | Whether to include any divisions marked deleted: ALL \| SINCE_YESTERDAY \| SINCE_LAST_WEEK \| NONE<br><br>**Default**: `"NONE"` |

## Response Type

[`Task<Models.PopulatedPlacesResponse>`](../../doc/models/populated-places-response.md)

## Example Usage

```csharp
string countryId = "countryId6";
string regionCode = "regionCode4";
bool? namePrefixDefaultLangResults = true;
bool? asciiMode = false;
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
string includeDeleted = "NONE";
try
{
    PopulatedPlacesResponse result = await geoController.FindRegionDivisionsUsingGETAsync(
        countryId,
        regionCode,
        null,
        null,
        null,
        namePrefixDefaultLangResults,
        null,
        asciiMode,
        hateoasMode,
        null,
        limit,
        offset,
        null,
        includeDeleted
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Find Region Cities Using GET

Get the cities in a specific country region. The country and region info is omitted in the response.

```csharp
FindRegionCitiesUsingGETAsync(
    string countryId,
    string regionCode,
    int? minPopulation = null,
    int? maxPopulation = null,
    string namePrefix = null,
    bool? namePrefixDefaultLangResults = true,
    string timeZoneIds = null,
    string types = null,
    bool? asciiMode = false,
    bool? hateoasMode = true,
    string languageCode = null,
    int? limit = 10,
    int? offset = 0,
    string sort = null,
    string includeDeleted = "NONE")
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `countryId` | `string` | Template, Required | An ISO-3166 country code or WikiData id |
| `regionCode` | `string` | Template, Required | An ISO-3166 or FIPS region code |
| `minPopulation` | `int?` | Query, Optional | Only places having at least this population |
| `maxPopulation` | `int?` | Query, Optional | Only places having no more than this population |
| `namePrefix` | `string` | Query, Optional | Only entities whose names start with this prefix. If languageCode is set, the prefix will be matched on the name<br>as it appears in that language. |
| `namePrefixDefaultLangResults` | `bool?` | Query, Optional | When name-prefix matching, whether or not to match on names in the default language if a non-default languageCode is set.<br><br>**Default**: `true` |
| `timeZoneIds` | `string` | Query, Optional | Only places in these time-zones (comma-delimited) |
| `types` | `string` | Query, Optional | Only places for these types (comma-delimited): CITY \| ADM2 |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `languageCode` | `string` | Query, Optional | Display results in this language |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |
| `sort` | `string` | Query, Optional | How to sort place results.<br>'Format: ±SORT_FIELD,±SORT_FIELD'<br>where SORT_FIELD = elevation \| name \| population |
| `includeDeleted` | `string` | Query, Optional | Whether to include any divisions marked deleted: ALL \| SINCE_YESTERDAY \| SINCE_LAST_WEEK \| NONE<br><br>**Default**: `"NONE"` |

## Response Type

[`Task<Models.PopulatedPlacesResponse>`](../../doc/models/populated-places-response.md)

## Example Usage

```csharp
string countryId = "countryId6";
string regionCode = "regionCode4";
bool? namePrefixDefaultLangResults = true;
bool? asciiMode = false;
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
string includeDeleted = "NONE";
try
{
    PopulatedPlacesResponse result = await geoController.FindRegionCitiesUsingGETAsync(
        countryId,
        regionCode,
        null,
        null,
        null,
        namePrefixDefaultLangResults,
        null,
        null,
        asciiMode,
        hateoasMode,
        null,
        limit,
        offset,
        null,
        includeDeleted
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 404 | 404 - Not Found | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Find Cities Near Location Using GET

Find cities near the given location, filtering by optional criteria. If no criteria are set, you will get back
all known cities.

```csharp
FindCitiesNearLocationUsingGETAsync(
    string locationId,
    int? radius = null,
    string distanceUnit = "MI",
    string countryIds = null,
    string excludedCountryIds = null,
    int? minPopulation = null,
    int? maxPopulation = null,
    string namePrefix = null,
    bool? namePrefixDefaultLangResults = true,
    string timeZoneIds = null,
    string types = null,
    bool? asciiMode = false,
    bool? hateoasMode = true,
    string languageCode = null,
    int? limit = 10,
    int? offset = 0,
    string sort = null,
    string includeDeleted = "NONE")
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | A latitude/longitude in ISO-6709 format: ±DD.DDDD±DDD.DDDD |
| `radius` | `int?` | Query, Optional | The location radius within which to find places |
| `distanceUnit` | `string` | Query, Optional | The unit of distance: MI \| KM<br><br>**Default**: `"MI"` |
| `countryIds` | `string` | Query, Optional | Only places in these countries (comma-delimited country codes or WikiData ids) |
| `excludedCountryIds` | `string` | Query, Optional | Only places NOT in these countries (comma-delimited country codes or WikiData ids) |
| `minPopulation` | `int?` | Query, Optional | Only places having at least this population |
| `maxPopulation` | `int?` | Query, Optional | Only places having no more than this population |
| `namePrefix` | `string` | Query, Optional | Only entities whose names start with this prefix. If languageCode is set, the prefix will be matched on the name<br>as it appears in that language. |
| `namePrefixDefaultLangResults` | `bool?` | Query, Optional | When name-prefix matching, whether or not to match on names in the default language if a non-default languageCode is set.<br><br>**Default**: `true` |
| `timeZoneIds` | `string` | Query, Optional | Only places in these time-zones (comma-delimited) |
| `types` | `string` | Query, Optional | Only places for these types (comma-delimited): CITY \| ADM2 |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `languageCode` | `string` | Query, Optional | Display results in this language |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |
| `sort` | `string` | Query, Optional | How to sort places.<br>Format: ±SORT_FIELD,±SORT_FIELD<br>where SORT_FIELD = countryCode \| elevation \| name \| population |
| `includeDeleted` | `string` | Query, Optional | Whether to include any divisions marked deleted: ALL \| SINCE_YESTERDAY \| SINCE_LAST_WEEK \| NONE<br><br>**Default**: `"NONE"` |

## Response Type

[`Task<Models.PopulatedPlacesResponse>`](../../doc/models/populated-places-response.md)

## Example Usage

```csharp
string locationId = "locationId2";
string distanceUnit = "MI";
bool? namePrefixDefaultLangResults = true;
bool? asciiMode = false;
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
string includeDeleted = "NONE";
try
{
    PopulatedPlacesResponse result = await geoController.FindCitiesNearLocationUsingGETAsync(
        locationId,
        null,
        distanceUnit,
        null,
        null,
        null,
        null,
        null,
        namePrefixDefaultLangResults,
        null,
        null,
        asciiMode,
        hateoasMode,
        null,
        limit,
        offset,
        null,
        includeDeleted
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |


# Find Divisions Near Location Using GET

Find administrative divisions near the given location, filtering by optional criteria. If no criteria are set,
you will get back all known divisions.

```csharp
FindDivisionsNearLocationUsingGETAsync(
    string locationId,
    int? radius = null,
    string distanceUnit = "MI",
    string countryIds = null,
    string excludedCountryIds = null,
    int? minPopulation = null,
    int? maxPopulation = null,
    string namePrefix = null,
    bool? namePrefixDefaultLangResults = true,
    string timeZoneIds = null,
    bool? asciiMode = false,
    bool? hateoasMode = true,
    string languageCode = null,
    int? limit = 10,
    int? offset = 0,
    string sort = null,
    string includeDeleted = "NONE")
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `locationId` | `string` | Template, Required | A latitude/longitude in ISO-6709 format: ±DD.DDDD±DDD.DDDD |
| `radius` | `int?` | Query, Optional | The location radius within which to find places |
| `distanceUnit` | `string` | Query, Optional | The unit of distance: MI \| KM<br><br>**Default**: `"MI"` |
| `countryIds` | `string` | Query, Optional | Only places in these countries (comma-delimited country codes or WikiData ids) |
| `excludedCountryIds` | `string` | Query, Optional | Only places NOT in these countries (comma-delimited country codes or WikiData ids) |
| `minPopulation` | `int?` | Query, Optional | Only places having at least this population |
| `maxPopulation` | `int?` | Query, Optional | Only places having no more than this population |
| `namePrefix` | `string` | Query, Optional | Only entities whose names start with this prefix. If languageCode is set, the prefix will be matched on the name<br>as it appears in that language. |
| `namePrefixDefaultLangResults` | `bool?` | Query, Optional | When name-prefix matching, whether or not to match on names in the default language if a non-default languageCode is set.<br><br>**Default**: `true` |
| `timeZoneIds` | `string` | Query, Optional | Only places in these time-zones (comma-delimited) |
| `asciiMode` | `bool?` | Query, Optional | Display results using ASCII characters<br><br>**Default**: `false` |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `languageCode` | `string` | Query, Optional | Display results in this language |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |
| `sort` | `string` | Query, Optional | How to sort places.<br>Format: ±SORT_FIELD,±SORT_FIELD<br>where SORT_FIELD = countryCode \| elevation \| name \| population |
| `includeDeleted` | `string` | Query, Optional | Whether to include any divisions marked deleted: ALL \| SINCE_YESTERDAY \| SINCE_LAST_WEEK \| NONE<br><br>**Default**: `"NONE"` |

## Response Type

[`Task<Models.PopulatedPlacesResponse>`](../../doc/models/populated-places-response.md)

## Example Usage

```csharp
string locationId = "locationId2";
string distanceUnit = "MI";
bool? namePrefixDefaultLangResults = true;
bool? asciiMode = false;
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
string includeDeleted = "NONE";
try
{
    PopulatedPlacesResponse result = await geoController.FindDivisionsNearLocationUsingGETAsync(
        locationId,
        null,
        distanceUnit,
        null,
        null,
        null,
        null,
        null,
        namePrefixDefaultLangResults,
        null,
        asciiMode,
        hateoasMode,
        null,
        limit,
        offset,
        null,
        includeDeleted
    );
}
catch (ApiException e)
{
    // TODO: Handle exception here
    Console.WriteLine(e.Message);
}
```

## Errors

| HTTP Status Code | Error Description | Exception Class |
|  --- | --- | --- |
| 400 | 400 - Bad Request | [`BaseResponseException`](../../doc/models/base-response-exception.md) |
| 401 | 401 - Unauthorized | `ApiException` |
| 403 | 403 - Forbidden | [`BaseResponseException`](../../doc/models/base-response-exception.md) |

