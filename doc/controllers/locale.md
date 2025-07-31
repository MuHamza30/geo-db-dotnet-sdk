# Locale

Locale Endpoints

```csharp
LocaleController localeController = client.LocaleController;
```

## Class Name

`LocaleController`

## Methods

* [Get Currencies Using GET](../../doc/controllers/locale.md#get-currencies-using-get)
* [Get Languages Using GET](../../doc/controllers/locale.md#get-languages-using-get)
* [Get Locales Using GET](../../doc/controllers/locale.md#get-locales-using-get)
* [Get Timezones Using GET](../../doc/controllers/locale.md#get-timezones-using-get)
* [Get Time Zone Using GET](../../doc/controllers/locale.md#get-time-zone-using-get)
* [Get Time Zone Date Time Using GET](../../doc/controllers/locale.md#get-time-zone-date-time-using-get)
* [Get Time Zone Time Using GET](../../doc/controllers/locale.md#get-time-zone-time-using-get)


# Get Currencies Using GET

Find currencies, filtering by optional criteria. If no criteria are set, you will get back all known currencies.

```csharp
GetCurrenciesUsingGETAsync(
    string countryId,
    bool? hateoasMode = true,
    int? limit = 10,
    int? offset = 0)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `countryId` | `string` | Query, Required | Currencies for this country id |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |

## Response Type

[`Task<Models.CurrenciesResponse>`](../../doc/models/currencies-response.md)

## Example Usage

```csharp
string countryId = "countryId6";
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
try
{
    CurrenciesResponse result = await localeController.GetCurrenciesUsingGETAsync(
        countryId,
        hateoasMode,
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


# Get Languages Using GET

Get all supported languages

```csharp
GetLanguagesUsingGETAsync(
    bool? hateoasMode = true,
    int? limit = 10,
    int? offset = 0)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |

## Response Type

[`Task<Models.LanguagesResponse>`](../../doc/models/languages-response.md)

## Example Usage

```csharp
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
try
{
    LanguagesResponse result = await localeController.GetLanguagesUsingGETAsync(
        hateoasMode,
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


# Get Locales Using GET

Get all known locales

```csharp
GetLocalesUsingGETAsync(
    bool? hateoasMode = true,
    int? limit = 10,
    int? offset = 0)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |

## Response Type

[`Task<Models.LocalesResponse>`](../../doc/models/locales-response.md)

## Example Usage

```csharp
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
try
{
    LocalesResponse result = await localeController.GetLocalesUsingGETAsync(
        hateoasMode,
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


# Get Timezones Using GET

Get all known time-zones

```csharp
GetTimezonesUsingGETAsync(
    bool? hateoasMode = true,
    int? limit = 10,
    int? offset = 0)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `hateoasMode` | `bool?` | Query, Optional | Include HATEOAS-style links in results<br><br>**Default**: `true` |
| `limit` | `int?` | Query, Optional | The maximum number of results to retrieve<br><br>**Default**: `10` |
| `offset` | `int?` | Query, Optional | The zero-ary offset index into the results<br><br>**Default**: `0` |

## Response Type

[`Task<Models.TimeZonesResponse>`](../../doc/models/time-zones-response.md)

## Example Usage

```csharp
bool? hateoasMode = true;
int? limit = 10;
int? offset = 0;
try
{
    TimeZonesResponse result = await localeController.GetTimezonesUsingGETAsync(
        hateoasMode,
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


# Get Time Zone Using GET

Get time-zone

```csharp
GetTimeZoneUsingGETAsync(
    string zoneId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `zoneId` | `string` | Template, Required | A time-zone id |

## Response Type

[`Task<Models.TimeZoneResponse>`](../../doc/models/time-zone-response.md)

## Example Usage

```csharp
string zoneId = "zoneId8";
try
{
    TimeZoneResponse result = await localeController.GetTimeZoneUsingGETAsync(zoneId);
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


# Get Time Zone Date Time Using GET

Get time-zone date-time

```csharp
GetTimeZoneDateTimeUsingGETAsync(
    string zoneId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `zoneId` | `string` | Template, Required | A time-zone id |

## Response Type

[`Task<Models.DateTimeResponse>`](../../doc/models/date-time-response.md)

## Example Usage

```csharp
string zoneId = "zoneId8";
try
{
    DateTimeResponse result = await localeController.GetTimeZoneDateTimeUsingGETAsync(zoneId);
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


# Get Time Zone Time Using GET

Get time-zone time

```csharp
GetTimeZoneTimeUsingGETAsync(
    string zoneId)
```

## Parameters

| Parameter | Type | Tags | Description |
|  --- | --- | --- | --- |
| `zoneId` | `string` | Template, Required | A time-zone id |

## Response Type

[`Task<Models.TimeResponse>`](../../doc/models/time-response.md)

## Example Usage

```csharp
string zoneId = "zoneId8";
try
{
    TimeResponse result = await localeController.GetTimeZoneTimeUsingGETAsync(zoneId);
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

