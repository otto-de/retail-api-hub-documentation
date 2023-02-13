## Deprecation

As part of the API lifecycle it might be necessary to phase out an API element, such as a resource [profile](10_profiles.md), a query parameter, or an API endpoint.
This can happen for a variety of reasons, including outdated resource properties, security issues, or when a business case is no longer supported.

Along with the deprecation of a resource profile, if we do not remove it completely, we also introduce a new version of it.
For each endpoint operation, the OTTO Retail-API reference also displays the currently active profile version URL.
We only maintain the latest version of a profile and strongly encourage new API users to _not_ implement outdated versions.
Continue for [more information about versioning](08_versioning.md).

After deprecation announcement, we will work together with our API consumers to discover a migration strategy, and to agree on deprecation and sunset schedules.
During the deprecation phase we will further maintain the deprecated API element and monitor its usage.
We may shutdown the deprecated API element after all API consumers have successfully migrated, but no later than the sunset date.

During the deprecation phase you can determine if an API element is deprecated, by actively monitoring the HTTP response headers that your API client receives:

|    Header     | Description                                                                                                                                                                                                                                                                                                                                                     |
| :-----------: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Deprecation` | The `Deprecation` header (see draft: [RFC Deprecation HTTP Header](https://datatracker.ietf.org/doc/html/draft-dalal-deprecation-header)) indicates if the accessed API element is or will be deprecated. If the API element is deprecated, the header contains the value `true`, otherwise it contains a timestamp marking the start of the deprecation phase. |
|   `Sunset`    | The optional `Sunset` header (see: [RFC 8594](https://datatracker.ietf.org/doc/html/rfc8594#section-3)) contains a single timestamp, indicating the date after which consumers may no longer use the deprecated API element. After the sunset date, the API element may be removed without further notice.                                                      |

Example responses:

```http
Deprecation: Sun, 31 Dec 2024 23:59:59 GMT
Sunset: Sun, 31 Dez 2025 23:59:59 GMT
```
