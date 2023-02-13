## Pagination

When querying a collection resource, you receive multiple resources at once instead of a single resource item.
A page-based pagination approach divides the result set of a request into pages of a certain size.
Each API sets their default values for `pageSize`, `minimum` and `maximum` independently.

You can either use the default values, or adjust the values of the query parameters that are described below to tailor the result to your custom processing patterns.
See the "Parameters" section of each operation in the API Reference for endpoint-specific default values.

Parameter set for pagination:

| Parameter  | Example values | Example        | Description                                                                                                                         |
| :--------- | :------------- | :------------- | :---------------------------------------------------------------------------------------------------------------------------------- |
| `page`     | `0..n`         | `?page=0`      | The page that should be returned. The example returns the first page. Note that page counting starts at value 0 for the first page. |
| `pageSize` | `1..n`         | `?pageSize=10` | The number of items a returned page should contain. The example returns 10 elements.                                                |

Every response body of a collection resource includes the object `_page`, which contains the values of the used parameters with property names that differ from the query parameter names.

Hypermedia APIs return collection resources with an additional object `_links`.
This object contains a map of links using the pagination parameters and `prev` and `next`, pointing to the previous and next page of the collection.
Using these links, the values of your request are automatically applied to the subsequent requests.

### Example request

This request combines the query parameters `page` and `pageSize` and requests page one of the collection resource /products to include two items:

```http
GET /products?page=1&pageSize=2 HTTP/1.1
Host: retail-api.otto.de
Authorization: Bearer <Access token>
otto-ecuuid: string
Accept: application/hal+json;profile="/products/product+v1"
```

### Example response body

The response body to the request above embeds two resource objects inside the array `item`.
The pagination parameters and values are applied to the link relations inside the object `_links`, and are reflected in the object `_page`.

```json
{
  "_embedded": {
    "item": [
      {
        "id": "393693-121040",
        "salesId": "927793906233",
        "quantity": 2,
        "delivery": {...}
      },
      {
        "id": "393693-121041",
        "salesId": "927793906233",
        "quantity": 1,
        "delivery": {...}
      }
    ]
  },
  "_links": {
    "self": {
      "href": "https://retail-api.otto.de/products?page=1&pageSize=2"
    },
    "prev": {
      "href": "https://retail-api.otto.de/products?page=0&pageSize=2"
    },
    "next": {
      "href": "https://retail-api.otto.de/products?page=2&pageSize=2"
    }
  },
  "_page": {
    "size": 2,
    "number": 1
  }
}
```
