# KN IDs, Names, and Title

* Title and name are primary node identifiers
* All caps reserved for special use
* Unicode Lower Letters (Ll) and numbers required for URI and directory names
* Titles should stand alone without implied context 
* Only one title per node (`# Title`)
* Titles may contain any valid Unicode
* Headers and internal node linking unrelated

## Examples

Given the following file contained within a `/lang/md` normal node
subdirectory of a root knowledge node:

```md
# Markdown

Markdown is ....
```

Produces the following entry within a `/DEX/data.tsv` file:

```tsv
2021-02-14T08:43:30-05:00	lang.md	Markdown
```


