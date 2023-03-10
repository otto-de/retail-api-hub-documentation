---
type: MUST
id: R100021
---

# use HAL format for collection resources

This rule applies to APIs that have to comply with [REST maturity level 3](@guidelines/R000033).

The list of resources is embedded under `_embedded` with the key representing the link-relation type.
This is the same as the one used in the `_links` section.

The [Embedded resources](../010_Embedded-resources/000_index.md) section provides more information on embedding documents.

References:
- [MUST implement REST maturity level 2](@guidelines/R000032)
- [MUST implement REST maturity level 3 for transitional APIs](@guidelines/R000033)
