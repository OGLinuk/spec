# URLS Node Type

Bookmarking locations to external information is the most important
online research tool anyone will use. It's important to have a way to
quickly save them in a way that can be universally and easily shared
with others without any specific service dependency. The URLS node type
provides for this allowing Web and KEG (and any other online accessible
URL/URI type stuff) to be easily saved.

## Use `data.json` Only

This data is easy enough to maintain in JSON format and will usually be
added with the assistance of some script or tool. 

## Fields

Field|Description
|:-:|-
U|The actual URI/URL with or without a schema. Schemas should only be used if it is only available from a specific schema (such as web-only content).
D|Description in terms that others would value. This can be the title, but doesn't necessarily need to be (and often will not be).
S|Shortcut is any valid node name and will be used for quick tab. completion and mnemonic references.
N|Additional notes that don't make sense in the description, usually not displayed unless verbose mode is on.
