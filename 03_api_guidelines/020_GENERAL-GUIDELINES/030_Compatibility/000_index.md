# Compatibility

As long as applications are used, they are subject to change. As applications change, it is likely that the APIs they use or provide will also change occasionally. So that in a distributed system landscape not all applications involved in a communication via an API have to be updated at the same time, it is important to keep changes to the API as transparent as possible for all parties involved in the communication. _Transparency_ in this context means that despite the change, the existing communication parties can continue to communicate without any problems even with the partners who have already implemented the change.

According to this definition, the term _compatibility_ refers solely to the exchange of messages _on the wire_. Further interpretations, such as the API's specification file itself and its possible processing on the tool side (e.g. code generators), are explicitly excluded. However, API providers are of course free to give their consumers further guarantees that go beyond compatibility _on the wire_.

This section deals with topics, such as [compatible API evolution](./010_Compatible-changes/000_index.md), introduction of [new API components](./020_Preview/000_index.md) and finally retiring [obsoleted API components](./030_Deprecation/000_index.md).

The general rules for compatibility included in this section are independent of the API type.
Versioning and other compatibility rules specific to REST and Event APIs are documented in their respective sections:

- [Compatibility for REST APIs](../../030_REST-GUIDELINES/050_Compatibility/000_index.md)
- [Compatibility for Event APIs](../../040_EVENT-GUIDELINES/050_Compatibility/index.md)
