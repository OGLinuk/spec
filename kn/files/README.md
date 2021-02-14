# KN File Directory Structure

Each knowledge node is a directory (which some call a "folder") that
may contain the following files but must always contain either a `README.md`
file or one of the `data` file types. The `generate` file is always
optional.

Name|Summary
|:-:|-
[`README.md`](readme)|Simplified Semantic Pandoc Markdown
[`data.*`](data)|Simplified Structured Data
[`generate.*`](generate)|Content Generator Executable

The file types will usually be:

* Simplified Pandoc Markdown (`.md`)
* Simplified YAML Structured Data (`.yml`)
* Compressed Raster Image Formats (`.jpg`, `.png`, `.gif`, `.webp`)
* Scalable Vector Images (`.svg`)
* Generator Script (`.sh`, `.py`, `.pl`, `.go`)

Knowledge nodes may contain any additional files but consideration
should be given to the fact that others will be replicating them if
shared. Therefore, large files (including video and audio) should be
avoided and emphasis should be on textual content and reasonably sized
images.

> **Avoid bloat.** While nothing in the specification strictly >
> prevents the inclusion of any file within any node, knowledge nodes
> should contain nothing but knowledge source and one optional script
> that generates it. Tool specific files unnecessarily bloat the node
> and are therefore strongly discouraged. Detection of such files
> (including "hidden" files and unrelated binaries) may result in a node
> being black-listed by the KEG community or even blocked by some tools.

## Directories

Knowledge nodes may contain any number of directories that may simply
be for better file organization or that are actual knowledge node
directories themselves. 

### Beware of Inflexible Interlink Dependencies

While the structure and content of any node is entirely up to the
creators and maintainers, caution should be used when creating any
relative links between nodes since this creates tight dependency
couplings to specific directory structures (and the resulting node IDs). 
This preventing easy reorganization later. 

Therefore, it is generally preferable to create flattened directory
structures within an [*entry node*](#entry-node) wherever possible.

> The single greatest administrative task is usually resolving links and
> orphans when things move (as they inevitably do).

### Entry Nodes

An *entry node* is a point of entry into the knowledge, a jumping off
point.

Consider entry nodes the hubs through which content consumers will pass on
their way to the rest of the content contained therein. Entry node URIs
are frequently passed, saved, and used as external links from other KEG
content. This provides greater stability over linking to individual
subnodes.

Entry nodes always contain subnodes for which [special node
types](../types) usually provide catalog-like information.

All entry node subdirectories must not contain any relative links to
anything not contained within the entry node. Otherwise, they lose
their portability.

### Root Nodes

A *root node* corresponds to a full cluster/collection of knowledge
nodes that can be transported together in bulk (as a compressed tar
ball, Git repo, concurrent network crawl, etc.)

> Remember that the method of content transfer is unspecified allowing
> the greatest flexibility and sustainability when dealing with how to
> transport knowledge nodes between systems. It is perfectly acceptable
> --- even encouraged --- to transport root nodes by "sneaker net" on
> foot when circumstances require.
