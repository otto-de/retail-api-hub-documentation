## Hypermedia

We use [JSON Hypertext Application Language (HAL)](https://datatracker.ietf.org/doc/html/draft-kelly-json-hal) to represent our API resources with additional hypermedia information, and to connect them in a consistent way using [links](https://datatracker.ietf.org/doc/html/rfc5988).

A HAL resource object returned by our API has:

- a `_links` property, containing a map of links that allows you to navigate from the returned resource object to its related API resources.
- an optional `_embedded` property, containing additional resource objects, for example, when querying a collection resource.

You can use the `_links` map instead of composing URIs yourself, or speculating if further related resources exist.
The links inside this map are each identified by a link relation type (rel), that defines the semantics of the relation between two resources.

Example of a `_links` map:

```json
{
  "_links": {
    "self": {
      "href": "https://retail-api.otto.de/products/S0P0509Y",
      "type": "application/hal+json",
      "profile": "/products/product+v1"
    }
  }
}
```

A rel such as `self` points to the current resource.

When you query a collection resource, the API returns a resource object with the `_embedded` property, containing additional resource objects besides the one you requested.
Apart from collection resources, some other resources also support the embedding of related resources via the request parameter `embedded`.
For each resource, our API reference provides documentation of the supported request parameters and example responses.

Example of embedded resource objects:

```json
{
  "links": {...},
  "_embedded": {
    "item": [
      {
        "id": "3538941240",
        "salesOrderId": "929906233",
        "fulfillmentStatus": "DELIVERED",
        "orderDate": "2021-01-15T00:00:00.000Z",
        "product": {...}
      },
      {...}
    ]
  }
}
```
