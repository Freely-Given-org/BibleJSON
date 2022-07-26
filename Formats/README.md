# BibleJSON Formats

These formats are unashamedly [USFM](https://UBSICAP.github.io/usfm/)-based.
USFM (and its very semantically-close [USX](https://UBSICAP.github.io/usx/) XML relative) is undoubtedly the currently most popular format for
interchange of Bible translations
(and even for Hebrew/Greek Bible originals).

Wherever USFM is mentioned below, it also applies to USX
and [ESFM](https://github.com/Freely-Given-org/ESFM).

We use [JSON Schema](https://JSON-Schema.org/) for validation
via [JsonSchema on PyPI](https://PyPI.org/project/jsonschema/).

## Design priorities

Basically we want parsed USFM that can be quickly loaded by a Bible app.
Thus it is soon discovered that data must be stored in book files,
as an entire Bible is often to large to load while a user is waiting.

Modern USFM often contains links to lexicons and/or databases,
and translations often contain complex links to original language words.
If this information is stored within the USFM, it tends to be very verbose and unwieldy.
However, if the information is stored in stand-off markup,
then it still must be efficiently linked to the verse text.
Handling all this extra information, could conceivably bulk up the intermediate files
enough to make them slow to load, or to require considerable device memory.
This is especially frustrating if that additional data is not
required for a particular app, e.g., a plain-text Bible reader app.
This then might suggest either breaking book files into chapters
and/or filtering out unnecessary data from the JSON files in advance.

## Text JSON

Can be Bible text or any other Book/Chapter/Verse (B/C/V) resource
like a Bible commentary.

The main container is a list that contains USFM-like lines
as well as a number of additional markers
including closing markers.

## Index JSON

Indexes are calculated at JSON compile time.

The main index links B/C/V references to a slice of text JSON entries.

## Other orgs

eBible.org uses their [USFX](https://ebible.org/usfx/)
as their intermediate format,
but as far as we're aware, USFX hasn't been widely adopted.
Also, over the last decade, JSON has become a more popular
computer-readable data (intermediate) format than XML.

[unfoldingWord](https://www.unfoldingword.org/) supports
[Proskomma](https://doc.proskomma.bible/en/latest/) which uses
PERF (Proskomma Editor-Ready Format) JSON
and Sofria -- see [here](https://github.com/Proskomma).
These attempt to break-away from the USFM-like mindset,
which our work does not attempt to do.