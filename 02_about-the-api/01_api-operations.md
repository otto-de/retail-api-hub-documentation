# About the API

## API operations

To build a REST request, combine the respective HTTP method with the following information:

- OTTO Retail-API base URL
- Resource URI with replaced path parameters
- Valid access token
- Request headers (operation-specific)
- Request body (operation-specific)

For example:

```http
POST /products/<product-id:string> HTTP/1.1
Host: https://retail-api.otto.de
Authorization: Bearer <access token>
Content-Type: application/hal+json;profile="/product/product+v1""
Accept: application/hal+json;profile="/product/product+v1""
```
