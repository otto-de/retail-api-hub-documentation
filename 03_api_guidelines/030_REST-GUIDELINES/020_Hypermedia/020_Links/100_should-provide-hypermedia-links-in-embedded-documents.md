---
type: SHOULD
id: R100028
---

# provide hypermedia links in embedded documents

The list resource items should provide the same links as the single resource representation as described in [Hypermedia](../000_index.md).

Links may be omitted to prevent performance degradation or response bloat.
Keep the client's use cases in mind.
You should not omit information if most use cases need those and would be forced to do `n` additional calls.
