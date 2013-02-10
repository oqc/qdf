# The Quran Text Format (QTF)

A file format for Quran texts that is uses plain text internally: one line per verse,
delimited by a `\n` (newline), no unnumbered bismallahs, and UTF-8.
Verse numbers are not part of this format and all chapters follow one after another
in a single file.  The extension for this format is `.qtf`.

For a more sophisticated format see the [Open Quran Format](https://github.com/oqc/oqf)
(featuring: markup, footnotes, in-verse line breaks, headings and more).


# Metadata

One can supply metadata to a `qtf` file by placing a
[Quran Metadata Format](https://github.com/oqc/qmf) file, `.qmf`, with the same
basename, in the same folder.


# Packaging and compression

When packaging a Quran text in this format simply place both the `qtf` file (content)
and the `qmf` file (metadata), both with the same basename in a folder that equals that
basename.  Then use the PKZIP algorithm to compress and bundle them up in to a file
with the `.zqfz` extension.
