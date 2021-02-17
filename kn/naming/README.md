# KN Naming

Proper semantic naming is essential to the most flexible, accessible,
ans sustainable knowledge structure and management. Here is a summary of
the naming specifications collected from other parts of the spec.



* Title and name are primary node identifiers
* Unicode Lower Letters (Ll), numbers, and dashes only for URI and directory names
* CSS-like translation between dashes and mixed case when needed
* Titles should stand alone without implied context 
* Only one title per node (`# Title`)
* Titles may contain any valid Unicode
* Headers and internal node linking unrelated
* All numeric node names are allowed (filesystems universally permit)
* By convention, when representing a node name in code prefix it with an
  upper `N` or lower `n`.





## 

Given the following file contained within a `/lang/md` normal node
subdirectory of a root knowledge node:

```md
# Markdown

Markdown is ....
```

Produces the following entry within a `/DEX/data.tsv` file:

```tsv
2021-02-14T08:43:31-05:00	lang.md	Markdown
```


