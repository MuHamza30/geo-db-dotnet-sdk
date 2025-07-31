
# Getting Started with GeoDB Cities API

## Introduction

The GeoDB API focuses on getting global city and region data. Easily obtain country, region, and city data for use
in your apps!

<ul>
  <li>Filter cities by name prefix, country, location, time-zone, and even minimum population.</li>
  <li>Sort cities by name, country code, elevation, and population - or any combination of these.</li> 
  <li>Get all country regions.</li> <li>Get all cities in a given region.</li>
  <li>
    Display results in multiple languages.</li> <li>RESTful API adheres to industry best-practices, including
    HATEOAS-style links to facilitate paging results.
  </li> 
  <li>Backed by cloud-based load-balanced infrastructure for resiliency and performance!</li>
  <li>Data is periodically refreshed from GeoNames and WikiData.</li>
</ul>
<p>Notes:
<ul>
  <li>
    Since the database is periodically updated, this may <strong>very rarely</strong> result in certain cities
    being marked deleted (e.g., duplicates removed). By default, endpoints returning city data will exclude
    cities marked deleted. However, in the unlikely event that this occurs while your app is paging through a set
    of affected results - and you care about the paged results suddenly changing underneath - specify 
    <tt>includeDeleted=SINCE_YESTERDAY</tt> (or <tt>SINCE_LAST_WEEK</tt> if you're really paranoid!).
  </li>
</ul>
<hr/>
<h3>Useful Resources</h3>
<ul>
  <li>
    SDKs
    <ul>
      <li>
        <a href='https://www.npmjs.com/package/wft-geodb-angular-client'>Angular</a>, 
        <a href='https://github.com/wirefreethought/geodb-sample-angular-app'>Sample App</a>
      </li>
      <li><a href='https://github.com/wirefreethought/geodb-java-client'>Java</a></li>
      <li><a href='https://www.npmjs.com/package/wft-geodb-js-client'>JavaScript</a></li>
    </ul>
    <li><a href='swagger.json'>Swagger Docs</a></li>
    <li><a href='http://creativecommons.org/licenses/by/3.0/'>Usage License</a></li>
  </li>      
</ul>


## Install the Package

If you are building with .NET CLI tools then you can also use the following command:

```bash
dotnet add package GeoDbSDK --version 1.0.0
```

You can also view the package at:
https://www.nuget.org/packages/GeoDbSDK/1.0.0

## Initialize the API Client

**_Note:_** Documentation for the client can be found [here.](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/client.md)

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| Timeout | `TimeSpan` | Http client timeout.<br>*Default*: `TimeSpan.FromSeconds(100)` |
| HttpClientConfiguration | [`Action<HttpClientConfiguration.Builder>`](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/http-client-configuration-builder.md) | Action delegate that configures the HTTP client by using the HttpClientConfiguration.Builder for customizing API call settings.<br>*Default*: `new HttpClient()` |
| CustomHeaderAuthenticationCredentials | [`CustomHeaderAuthenticationCredentials`](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |

The API client can be initialized as follows:

```csharp
using GeoDBCitiesAPI.Standard;
using GeoDBCitiesAPI.Standard.Authentication;

GeoDBCitiesAPIClient client = new GeoDBCitiesAPIClient.Builder()
    .CustomHeaderAuthenticationCredentials(
        new CustomHeaderAuthenticationModel.Builder(
            "x-rapidapi-key"
        )
        .Build())
    .Build();
```

## Authorization

This API uses the following authentication schemes.

* [`UserSecurity (Custom Header Signature)`](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/auth/custom-header-signature.md)

## List of APIs

* [Geo](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/controllers/geo.md)
* [Locale](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/controllers/locale.md)

## SDK Infrastructure

### Configuration

* [HttpClientConfiguration](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/http-client-configuration.md)
* [HttpClientConfigurationBuilder](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/http-client-configuration-builder.md)
* [ProxyConfigurationBuilder](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/proxy-configuration-builder.md)

### HTTP

* [HttpCallback](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/http-callback.md)
* [HttpContext](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/http-context.md)
* [HttpRequest](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/http-request.md)
* [HttpResponse](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/http-response.md)
* [HttpStringResponse](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/http-string-response.md)

### Utilities

* [ApiException](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/api-exception.md)
* [ApiHelper](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/api-helper.md)
* [CustomDateTimeConverter](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/custom-date-time-converter.md)
* [UnixDateTimeConverter](https://www.github.com/MuHamza30/geo-db-dotnet-sdk/tree/1.0.0/doc/unix-date-time-converter.md)

