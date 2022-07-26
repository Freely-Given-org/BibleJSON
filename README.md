# BibleJSON

A set of documented JSON formats (with schemas) to contain Bible data and indexes
(rather than using the source [USFM](https://ubsicap.github.io/usfm/)
or our [ESFM](https://github.com/Freely-Given-org/ESFM)
or [USX](https://ubsicap.github.io/usx/)).

These formats are intended to be used in the middle of command-line (CLI) modules
which can be chained/piped together
(i.e., taking the output of one and using it as the input for the next one).
The enclosed compilers are designed to be fast and simple with minimum
error checking of the inputs and minimum user feedback,
i.e., they are designed for processing Bibles that are finished and polished.

For a work-in-progress Bible, we recommend using our
(Python) [BibleOrgSys](https://github.com/Freely-Given-org/BibleOrgSys)
instead to load the files.
Although the BibleOrgSys (or BOS) uses the same intermediate formats,
the input processors are designed to cope with the many various styles of sculpting USFM
and also with unfinished works and with human errors.
The BOS also loads many other different Bible formats into these JSON formats.

## Formats

The (compiled) JSON formats.

These formats are designed for any texts which use the traditional
Bible Book/Chapter/Verse (B/C/V) referencing.
As well as Bibles themselves, this also includes other works such
as Bible commentaries.

## Compilers

Fast Rust processors which load USFM or USX with minimal user feedback
and compile the B/C/V text into our JSON formats.

## Used by

These JSON formats are used by the following systems and/or organisations:

- our [BibleOrgSys](https://github.com/Freely-Given-org/BibleOrgSys) B/C/V checker and formatter
- our [Biblelator](https://github.com/Freely-Given-org/Biblelator) B/C/V resource viewer and translation editor
