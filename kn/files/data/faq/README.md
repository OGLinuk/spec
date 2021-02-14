# FAQ

## Will CSV ever be supported?

No. Its quirky requirements to escape commas and double quote, double
quotes are simply too difficult and error-prone to expect anyone to
maintain by hand.

## May I include other YAML/JSON/TSV files as well?

Yes. Only those beginning with the `data` prefix are reserved. But it is
generally preferred to put such files into their own nodes if they are
ever to be queried in any way.
