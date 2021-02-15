# KEG Architectural Design

The design of KEG *must* be as simple as possible per the
[tenets](../tenet) of the KEG project. Engineers tend to over-engineer
things (and have, the ultimate demise of the WorldWideWeb as a useful
knowledge tool is proof).

* Everything is just a node
* Knowledge is source code and can be managed as such
* Knowledge "bases" are just local root node on KEG
* The `keg.yml` is just to show node is on KEG
* The conventional `data.yml` (and optionally other `yml` files) are
  just like any other node.
* KEG URIs are just domains 

## Universal Resource Identifiers

Since any network protocol --- or no protocol --- can be used to access
any KEG node the only unique identifier required is a domain name
(including subdomains) and the dotted Node identifier. It is expected
(but not required) that the KEG creator and/or maintainer will have
administrative access to the domain in order to add the required TXT
record. If not, the KEG node will remain *unvalidated* but will still be
usable.

If an optional `jq` query is supplied the resulting raw JSON will be
implied in the return. By convention all KEG Node data keys are always
initial capitalized. This allows them to be distinguished from the node
path itself, which always has initial lowercase.

TODO get this updated from log
TODO ensure visibles will work in URI if not another for letter

```pegn
KEGURI <-- 'keg:' Node Query? ('@' Domain)?
Node   <-- (!'.' visible)+ ('.' (!'.' visible)+)*
Query     <-- # jq limited query
```

Examples:

```
keg:md.lang@rwx.gg
keg:md.lang.Summary@rwx.gg
```

## Simplified Pandoc Markdown

Simplified Pandoc Markdown is a subset of full Pandoc Markdown and a
superset of [GitHub Flavored
Markdown](https://duck.com/lite?kd=-1&kp=-1&q=GitHub+Flavored+Markdown).
Its primary purpose is to remove redundancies while providing full
support for mathematical notation. As a result, Simplified Pandoc
Markdown is the easiest to learn and only requires one pass to fully
parse and render. 

### Strongly Recommended But Not Required

Use of Simplified Pandoc Markdown is not a specification requirement,
but a strong suggestion. It is expected that most tools will only
support it, however.

## Simplified YAML Format

YAML is known to be insecure and complicated in its full form but is
commonly used only for simpler data representations. Simplified YAML
requires several specific constraints to address this:

* No `---` or `...`
* No linking
* Add text assumed to be [Simplified Pandoc
  Markdown](#simplified-pandoc-markdown) (therefore, the `|` operator
  is preferred for long text blocks over `>`).

Keep in mind that the sometimes problematic `yes` and `no` Boolean
values are still a part of Simplified YAML.

## Reserved Command Line Utility Names

Reserved Name|Usage
|:-:|-
`keg`|An knowledge package manager and sharing utility build and managed under the KEG initiative.
`kn`|A reserved name for a local knowledge management utility command or script to be created and used however the knowledge worker wants on their local system. It's expected that hundreds or millions of different `kn` tools will exist depending on the specific needs of the worker. A base Bash `kn` script will be managed under the KEG initiative, but it by no means required.

```
# query a node on the KEG
keg tap best.beers  
keg tap best.beers@rwx.gg
eval $(keg _bash)
eval $(kn _bash)
complete -C kn kn
complete -C keg keg
```

## Formerly Known As

Here are some fun and official naming considerations over the years:

* Universal Knowledge Transfer Service (UKNTS)
* Knowledge Universal Transfer Service (KNUTS)
* Federated Universal Knowledge Network (FUKN)
* Universal Federated Knowledge Database (FUKD)
* The Knowledge Net
* README World Exchange
* The Essential Web

## FAQ

### What is the difference between "keg" and "kn"?

The term "keg" always refers to the sharing network on which a "kn"
(knowledge node) is shared. 

### What is the difference between a "KEG node" and a "knowledge node"?

A KEG node is a knowledge node that is shared on the KEG. Knowledge
nodes can exist locally without ever being shared. A KEG node must be
shared to be called such.

### Why not "knowledge base"?

Because the term is inaccurate. The word "base" implied it can't be
further composed or otherwise combined. Therefore, the best and most
accurate term is "knowledge node" even if a single node is a root node
shared over KEG.

## Frequently Asked Questions (FAQ)

Here are the questions most frequently asked about KEG architectural
design.

### So is `keg` like package management for knowledge? 

Sort of.

* No versions.
* Not a whole "package".

### So is `keg` like Git for knowledge?

Sort of.

* No versions. Just currently cached, and latest published.

### So it's like a GPG trust ring?

Sort of.
