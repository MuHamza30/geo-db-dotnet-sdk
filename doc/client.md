
# Client Class Documentation

The following parameters are configurable for the API Client:

| Parameter | Type | Description |
|  --- | --- | --- |
| Timeout | `TimeSpan` | Http client timeout.<br>*Default*: `TimeSpan.FromSeconds(100)` |
| HttpClientConfiguration | [`Action<HttpClientConfiguration.Builder>`](../doc/http-client-configuration-builder.md) | Action delegate that configures the HTTP client by using the HttpClientConfiguration.Builder for customizing API call settings.<br>*Default*: `new HttpClient()` |
| CustomHeaderAuthenticationCredentials | [`CustomHeaderAuthenticationCredentials`](auth/custom-header-signature.md) | The Credentials Setter for Custom Header Signature |

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

## GeoDB Cities APIClient Class

The gateway for the SDK. This class acts as a factory for the Controllers and also holds the configuration of the SDK.

### Controllers

| Name | Description |
|  --- | --- |
| GeoController | Gets GeoController controller. |
| LocaleController | Gets LocaleController controller. |

### Properties

| Name | Description | Type |
|  --- | --- | --- |
| HttpClientConfiguration | Gets the configuration of the Http Client associated with this client. | [`IHttpClientConfiguration`](../doc/http-client-configuration.md) |
| Timeout | Http client timeout. | `TimeSpan` |
| Environment | Current API environment. | `Environment` |
| CustomHeaderAuthenticationCredentials | Gets the credentials to use with CustomHeaderAuthentication. | [`ICustomHeaderAuthenticationCredentials`](auth/custom-header-signature.md) |

### Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `GetBaseUri(Server alias = Server.Default)` | Gets the URL for a particular alias in the current environment and appends it with template parameters. | `string` |
| `ToBuilder()` | Creates an object of the GeoDB Cities APIClient using the values provided for the builder. | `Builder` |

## GeoDB Cities APIClient Builder Class

Class to build instances of GeoDB Cities APIClient.

### Methods

| Name | Description | Return Type |
|  --- | --- | --- |
| `HttpClientConfiguration(Action<`[`HttpClientConfiguration.Builder`](../doc/http-client-configuration-builder.md)`> action)` | Gets the configuration of the Http Client associated with this client. | `Builder` |
| `Timeout(TimeSpan timeout)` | Http client timeout. | `Builder` |
| `Environment(Environment environment)` | Current API environment. | `Builder` |
| `CustomHeaderAuthenticationCredentials(Action<CustomHeaderAuthenticationModel.Builder> action)` | Sets credentials for CustomHeaderAuthentication. | `Builder` |

