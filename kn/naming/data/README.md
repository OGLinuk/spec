# KN Data Field Names

The field names within the [KN data files](../../files/data) must follow
a strict specification in order to provide for consistent query grammar
development and maximize database compatibility. Names also indicate
scope.

## Unicode Letters Only

Names must only contain Unicode letter code points (L). This greatly
restricts the possible field names allowed in YAML simplifying the
resulting structured data and ensuring it is compatible with most other
systems and databases.

## Initial Upper for Exported

Fields that are named with an initial upper letter (Lu) must be
considered *exported* by all tools and editors.

## Initial Lower for Exported

Fields that are named with an initial lower letter (Ll) must be
considered *internal* by all tools and editors. This is not the same as
"private" or "hidden." Indeed, all data will be very much public unless
steps are taken to prevent nodes from being released.

## Frequently Asked Questions (FAQ)

### Why not allow underscore or dash?

Because they create ugly and unreadable identifiers, complicate KEG
queries, and cannot be trusted to work in all scenarios.
