# KN Structured Data File

A knowledge node may contain a single structured `data.yml`, `data.json`, or
`data.tsv` file that can be maintained by hand or generated from any
source.

The most common, user-friendly structure data formats are supported so
that data can easily be maintained with nothing more than a simple text
editor.

## YAML

If YAML, the file should not begin with `---` and must be in [KEG
simplified YAML format](#simplified-yaml-format). Use of YAML files is
designed to allow content maintainers the greatest flexibility and
readability without losing specificity in order to organize files in the
most convenient manner to be maintained "by hand."

## JSON

If JSON, the file is assumed to be generated somehow (although such is
not required) and can be either in indented form, or compressed without
indentation. 

Files may and should contain extensive use of visual whitespace and
comments with the expectation and promise that these files will *only*
be changed through the use of text editors used by humans. (JSON should
be used for everything else.)

## Tab-Delimited (TSV)

If TSV, the file is assumed to contain one record per line each
separated by a tab character. The first line must always contain the
field names which must consist only of legal [KN Data Field
Names](../names/data).

## Frequently Asked Questions (FAQ)

### Will CSV ever be supported?

No. Its quirky requirements to escape commas and double quote, double
quotes are simply too difficult and error-prone to expect anyone to
maintain by hand.

### Can I have other YAML/JSON/TSV files as well?

Yes. Only those beginning with the `data` prefix are reserved. But it is
generally preferred to put such files into their own nodes if they are
ever to be queried in any way.
