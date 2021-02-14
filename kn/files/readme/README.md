# Knowledge Node Directory Structure

Each knowledge node is a directory (sometimes called a "folder") that
must contain a [`README.md`](#readme-md) file, may contain a
[`data.yml`](#data-yml-data-json) or [`data.json`](#data-yml-data-json)
file, and may contain a [`generate`](#generate-generate) or
[`generate.go`](#generate-generate) file along with any other static content. 

Knowledge nodes may contain one or more other knowledge node directories
but each is unique and independent from its parent unless it contains
relative links to them within its content.

A [*root knowledge node*](#root-knowledge-node) is a node specified
primarily to contain other subnodes and usually contains one or more
[special node types](types).

## Files

Name|Summary|Required
-|-|-
`README.md`|Simplified Semantic Pandoc Markdown|Required
`data.yml`,`data.json`|Simplified Structured Data|Optional
`generate`,`generate.*`|Content Generator Executable|Optional

Knowledge nodes may contain any additional files but consideration
should be given to the fact that others will be replicating them if
shared. Therefore, large files (including video and audio) should be
avoided and emphasis should be on textual content and reasonably sized
images.

The file types will usually be:

* Simplified Pandoc Markdown (`.md`)
* Simplified YAML Structured Data (`.yml`)
* Compressed Raster Image Formats (`.jpg`, `.png`, `.gif`, `.webp`)
* Scalable Vector Images (`.svg`)
* Generator Script (`.sh`, `.py`, `.pl`, `.go`)

> **Avoid bloat.** While nothing in the specification strictly >
> prevents the inclusion of any file within any node, knowledge nodes
> should contain nothing but knowledge source and one optional script
> that generates it. Tool specific files unnecessarily bloat the node
> and are therefore strongly discouraged. Detection of such files
> (including "hidden" files and unrelated binaries) may result in a node
> being black-listed by the KEG community or even blocked by some tools.

### `README.md`

The `README.md` file contains free-form [Simplified Pandoc
Markdown](#simplified-pandoc-markdown).

### `data.yml`, `data.json`

A single knowledge node may contain a special reserved `data.yml` or
`data.json` file (but not both). 

If YAML, the file should not begin with `---` and must be in [KEG
simplified YAML format](#simplified-yaml-format). Use of YAML files is
designed to allow content maintainers the greatest flexibility and
readability without losing specificity in order to organize files in the
most convenient manner to be maintained "by hand."

> Note that other YAML asset files may be included in any knowledge node
but must never involved directly in `keg` and `kn` queries to maintain
performance across an entire root knowledge node. Consider adding an
additional node (with its own `data.yml` file) when the YAML data is
needed for such queries.

If JSON, the file is assumed to be generated somehow (although such is
not required) and can be either in indented form, or compressed without
indentation. 

Files may and should contain extensive use of visual whitespace and
comments with the expectation and promise that these files will *only*
be changed through the use of text editors used by humans. (JSON should
be used for everything else.)

### `generate`, `generate.*`

By convention an optional executable may be placed in each knowledge
node. It's purpose is to generate static content from dynamic sources
but it must never be automatically executed by anyone but the content
author or maintainer. It's purpose is only to convey how the
`data.json`, or `README.md` files were generated (`data.yml` should
generally never be generated due to difficulties maintaining YAML
comments and white space).

While `generate` will usually never be executed by anyone but the node
maintainer it does provide localized insight into the origin and
rendering of all data within the node. For this reason it must always be
human readable (never compiled). Generally, this means it will written
in one of the standard scripting languages. It may just contain a
comment indicating how the content is generated if such is not possible
to include as code.

There are several practical uses for such scripts:

* Generate portions `README.md` file from the contained YAML data
* Generate `data.json` data from external data sources
* Produce CSV and other views of data queries
* Leverage powerful text template systems (such as Go's `text/template`)
* Generate `index.html` pages to accompany the `README.md`

> Creating an `index.html` as well as `README.md` is particularly useful
when publishing to GitHub Pages since the HTML file allows more
flexibility when needed with regard to styles and progressive
enhancements such as interactive components that supplement the data but
do not replace it. In this way, knowledge nodes can double as
document-oriented web sites as well (at the slight cost of redundant
data in the index.html file since the `README.md` is always required).

## Special Nodes

The use of all capital ASCII letters for any node name is reserved for
special node types as specified [here](types).

The following optional special node names are reserved and must not be
used by node creators for anything other than their specified purpose
according to the specified format:

Name|Summary
|:-:|-
[DEX](dex)|Minimal index of all sibling nodes
[META](meta)|Searchable meta data from all sibling nodes
[WORDS](words)|Words map from all sibling nodes
[TYPES](types)|Type definitions for sibling node types (JSON Schema)
[KEG](keg)|Information related to sharing on KEG

### Specification

The specification of special nodes is maintained by AFKWorks along with
others ([specs.afk.works](https://specs.afk.works).

### Recommended Version

Because special node types conform to a specification that may vary over
time it is strongly recommended to include a Version field within the `data.json`
field indicating the version of specification being used. 

### Only `data.json`

Due to the high-performance reads required by tools that use these
special node types only `data.json` is allowed (not `data.yaml`). In all
cases the data may still be easily maintained by hand without additional
tooling.

