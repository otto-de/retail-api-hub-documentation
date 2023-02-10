## Authentication

The OTTO Retail-API uses OAuth 2.0 for authentication and authorization on all endpoints and does not handle unauthenticated requests.
We only support the OAuth 2.0 flow **Client Credentials Grant**.

In order to make requests to the OTTO Retail-API, you first need to obtain an access token for your application.

As proposed in the [RFC 9068 - JSON Web Token (JWT) Profile for OAuth 2.0 Access Tokens](https://datatracker.ietf.org/doc/html/rfc9068), the access tokens used for the OTTO Retail-API are JWTs, as defined in [RFC 7797](https://tools.ietf.org/html/rfc7797).


> :warning:
The grant flow Client Credentials require your client secret. 
Make sure that your client secret is not included in your distributed code, compiled apps, or public JavaScript.

The OTTO Retail-API provides the following token endpoints:

| Endpoint                                                                                       | Description                                    |
|------------------------------------------------------------------------------------------------| ---------------------------------------------- |
| https://keycloak.apps.otto.de/sec-api/auth/realms/retailapi-prod/protocol/openid-connect/token | Endpoint for token retrieval.                  |
| https://keycloak.apps.otto.de/sec-api/auth/realms/retailapi-prod/protocol/openid-connect/auth  | Endpoint for authentication and authorization. |

Although you can expect that the tokens have the TTL (time to live) described below, we still recommend that you always check the actual expiry time by inspecting the `exp` claim of the JWT.

Access token TTL: 5 minutes

### Client Credentials Grant

With the Client Credentials Grant access token, your application receives direct access to all relevant resources that are not tied to specific users.
See [Client Credentials Grant](https://www.rfc-editor.org/rfc/rfc6749#section-4.4) for details.

#### Obtaining an access token

You receive an access token through a POST request containing your client ID and client secret in the request body.
Keep in mind that this information is set during the initial client registration process via the OTTO Supplier Connect.

The following table shows the required parameters for this request:

| Parameter     | Description                                                                |
| ------------- | -------------------------------------------------------------------------- |
| grant_type    | Use `client_credentials` for this request.                                 |
| scope         | A space-separated list of requested scopes.                                |
| client_id     | Your client ID. Mandatory if you do not use HTTP basic authentication.     |
| client_secret | Your client secret. Mandatory if you do not use HTTP basic authentication. |


Example request:

```http
POST https://keycloak.apps.otto.de/sec-api/auth/realms/retailapi-prod/protocol/openid-connect/token HTTP/1.1
Content-Type: application/x-www-form-urlencoded

grant_type=client_credentials
&scope=products orders
&client_id=<your_client_id>
&client_secret=<your_client_secret>
```

Example of a successful token response:

```http
HTTP/1.1 200 OK
Content-Type: application/json
Cache-Control: no-store

{
  "access_token": "<valid oauth2 access token>",
  "token_type": "bearer",
  "expires_in": 299,
  "scope": "products orders",
  "jti": "1e559445-21df-4f01-a9de-e55ab519b2c3"
}
```

Here's some info about the access token response properties:

| Property       | Description                                                                                                    |
|----------------|----------------------------------------------------------------------------------------------------------------|
| `access token` | Contains the access token, that you need to include in all further API requests in the `Authorization` header. |
| `token_type`   | Identifies the type of the token.                                                                              |
| `exp`          | Specifies the timestamp after which the access token expires.                                                  |
| `scope`        | Contains a space-separated list of all granted scopes.                                                         |
| `jti`          | Contains a unique identifier of the access token.                                                              |


#### Making authorized requests

To make an authorized request to the OTTO Retail-API, add the `Authorization` header containing your access token to the HTTP request.
You can only access the resources with the scopes for which you initially registered your client.

Example request:

```http
GET /products/<productId> HTTP/1.1
Authorization: Bearer <valid oauth2 access token>
Accept: application/hal+json;profile="/product/product+v1"
```

If a request fails, the API returns an error response with an HTTP status code, and an error object with `error` and `error_description` parameters:

```http
HTTP/1.1 401 Unauthorized
Content-Type: application/problem+json
Cache-Control: no-store

{
    "type": "about:blank",
    "title": "Unauthorized",
    "status": 401,
    "detail": "Authentication is required, but has failed or has not yet been provided."
}
```

The API responds as follows:

| Response                     | Possible cause and solution                                                                                                                             |
|------------------------------| ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Code**: 401 UNAUTHORIZED   | A possible cause might be a missing authorization header or incorrect credentials.                                                                      |
| **Code**: 403 FORBIDDEN      | Access to the requested resource is not allowed, because the access token is invalid or expired.<br>A possible solution is refreshing the access token. |

