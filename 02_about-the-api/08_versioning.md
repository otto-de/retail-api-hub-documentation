## Versioning

We version each resource representation independently by its media type instead of maintaining a single global version number for the entire OTTO Retail-API landscape.
We use the [`profile`](https://datatracker.ietf.org/doc/html/rfc6906) parameter to further describe the resource representation in the media type.
This allows us to keep different versions of the same REST resource, and make them identifiable with a version suffix `+v{version}` in the profile path:

`/products/product+v1`

In case we change a resource representation in a non-compatible way, we iterate the version number:

`/products/product+v2`

You can specify the resource version on a request by using a `profile` parameter in the `Accept` header.

We try to maintain backwards compatibilty, but in some cases, changes to a resource require the introduction of a new version.
These cases might include, but are not limited to:

- Addition or removal of enumerated fields
- Change of mandatory properties
- Change the name of request/response properties
- Change the datatype of a property

You can find an overview of all available profiles and more detailed information about the usage of profiles in your requests in the [Profiles](10_profiles.md) section.
