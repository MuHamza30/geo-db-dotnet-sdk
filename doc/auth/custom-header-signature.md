
# Custom Header Signature



Documentation for accessing and setting credentials for UserSecurity.

## Auth Credentials

| Name | Type | Description | Setter | Getter |
|  --- | --- | --- | --- | --- |
| x-rapidapi-key | `string` | - | `XRapidapiKey` | `XRapidapiKey` |



**Note:** Auth credentials can be set using `CustomHeaderAuthenticationCredentials` in the client builder and accessed through `CustomHeaderAuthenticationCredentials` method in the client instance.

## Usage Example

### Client Initialization

You must provide credentials in the client as shown in the following code snippet.

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


