# JSON Data Files

JSON is the lingua franca of modern data exchanges and the first-pick
for most data being pulled or otherwise generated from other external
sources. 

However, even though JSON is "readable" by humans, it is rather
difficult to maintain unless the field values are rather simple. In
particular, when values contain line returns, which must be escaped per
the JSON specification making for very messy editing sessions.

## Prefer Indented

Since readability is a higher priority than total storage and network
transfer times JSON should be indented and readable rather than
compressed into a single line. This design decision is entirely up to
the content creator however.

## Line-Centric

Multiple JSON objects and/or arrays, one to a line, is acceptable and common.
