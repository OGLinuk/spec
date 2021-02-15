# KN Node Types

Knowledge nodes may have a type. Types definitions are themselves
knowledge nodes with unique IDs and use the special [TYPES](types)
[entry node](entry) within a [root node](root).

The use of all capital letters (Lu) for any node name is reserved for
special node types as specified [here](types).

The following optional special node names are reserved and must not be
used by node creators for anything other than their specified purpose
according to the specified format:

Name|Summary
|:-:|-
[DEX](dex)|Minimal index of all sibling nodes
[META](meta)|Searchable meta data from all sibling nodes
[WORDS](words)|Words map from all sibling nodes
[URLS](urls)|Bookmarks to KEG URIs and Web URLs
[TYPES](types)|Type definitions for sibling node types (JSON Schema)
[KEG](keg)|Information related to sharing on KEG
[doc](doc)|Statically rendered HTML and other document formats

### Specification

The specification of special nodes is maintained by AFK.Works along with
others ([specs.afk.works](https://specs.afk.works).

### Recommended Version

Because special node types conform to a specification that may vary over
time it is strongly recommended to include a Version field within the
`data.json` field indicating the version of specification being used. 

### Prefer `data.json` and `data.tsv`

Due to the high-performance reads required by tools that use these
special node types the highly performant `data.tsv` and `data.json` are
strongly recommended over `data.yaml`.
