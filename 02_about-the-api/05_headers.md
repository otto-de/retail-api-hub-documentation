## Headers

Our APIs require the use of certain HTTP headers.

### Request headers

To ensure that your API requests are processed successfully, we encourage you to always include the headers as listed in the table below.

Depending on the API, you may encounter different supported media types, such as `application/json`, `application/hal+json`, `application/merge-patch+json`, or `text/uri-list`.
See the "Request Headers" section of each operation in the API Reference for endpoint-specific request headers.

| Header          | Type   | Description                                                                                                                                                                                                                                                                                                                |
| :-------------- | :----- |:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Accept`        | String | The media type acceptable for the response body. Required for requests that have a response with a body. Can be one of the media types listed above in conjunction with a [profile parameter](10_profiles.md) including the profile URI of a resource. For example: `application/hal+json;profile="/products/product+v1"`. |
| `Authorization` | String | The OAuth 2.0 bearer token to authorize the request for accessing the API. Required for all requests.<br>For example: Bearer `<Access token>`.                                                                                                                                                                             |
| `Host`          | String | The target host of the request. Required for all requests. For the production environment use `retail-api.otto.de`, for the sandbox environment use `retail-api-sandbox.otto.de`.                                                                                                                                                 |
| `Content-Type`  | String | The media type of the request body. Required when a request body contains data. Can be one of the media types listed above in conjunction with a [profile parameter](10_profiles.md) including the profile URI of a resource. For example: `application/hal+json;profile="/products/product+v1"`.                          |

### Response headers

After processing a request, the OTTO Retail-API returns an HTTP response that uses standardized HTTP headers.
The table below summarizes the most common HTTP response headers that your client application may encounter when communicating with our REST API.

| Header           | Type   | Description                                                                                                                                                                                                                                                                                                             |
| :--------------- | :----- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Content-Length` | Number | The length of the returned response body content in bytes.                                                                                                                                                                                                                                                              |
| `Content-Type`   | String | The media type of the returned response body. Reflects the `Accept` header of the associated sent request, unless the server was not able to fulfill the client's demand. Can be a combination of `application/json` or `application/hal+json` and a [profile parameter](10_profiles.md) with the profile URI of a resource. |
| `Date`           | String | The timestamp of the response in [HTTP-date format](https://datatracker.ietf.org/doc/html/rfc9110#section-6.6.1). For example: `Thu, 7 Jul 2022 16:30:00 GMT`.                                                                                                                                                          |
| `Location`       | String | The URI of a resource. This response header is usually sent after creating a new resource.                                                                                                                                                                                                                              |
