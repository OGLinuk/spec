## Reserved Names

**All upper case identifiers** are reserved for use in identifying items
from this specification including (but not limited to) node, directory,
and type names. This includes files with lowercase suffixes and all
[static asset files](../../assets) contained within any node.

## Defined Elsewhere

The following are specifically defined elsewhere in the spec:

```pegn
'README.md'                              # unstructured prose 
'DATA' ('.yml' | '.json' | '.tsv')?      # structured data
'.GEN' ('.sh' | '.pl' | '.py' | '.go')?  # generator scripts
'META'                                   # META peer node
'WORDS'                                  # WORDS peer node
```

## Conflicting Common Names

The following names are commonly used in software and other projects and
repositories but are automatically included in this specified reserved
list but are defined flexibly enough (based on their legacy usage) so as
to not be problematic:

* CONTRIBUTORS
* CONTRIBUTING
* CONTRIBUTING.md
* DCO
* LICENSE

