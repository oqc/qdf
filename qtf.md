# The Quran Text Format (QTF)

File format for Quran texts that uses plain text internally: one line per verse,
delimited by a `\n` or `0x0A` (newline or line feed), contains no unnumbered bismallahs,
and is UTF-8 encoded.
Verse numbers are implicit in this format, they can be derived from the line number count.
All chapters simply follow one after another in a single file.

The extension for this format is `.qtf`.

It is based upon the "Text" format that [tanzil.net](http://tanzil.net) and
[zekr.org](http://zekr.org) use; and extends on that basis by having a strict
definition (this document) and allowing metadata to be embedded.

For a more sophisticated format see the [Quran Latex Format](https://github.com/oqc/qdf/blob/master/qlf.md).
The QLF has much more features, including: markup, footnotes, in-verse line breaks and headings.


## Metadata

QTF allows metadata to be embedded, by appending it to the end of the file.
The reason for appending it (instead of putting it at the start of the file) are:

1. the bismallah thereby is still on the first line of the file, and
2. the line numbers can still be used to derive the chapter and verse numbers from.

The metadata should adhere to the [Quran Metadata Format](https://github.com/oqc/qdf/blob/master/qmf.md)
and is separated from the Quran text by a line that starts with three dashes.
basename, in the same folder.

For example:

    [...]
    Say, "I seek refuge in the Lord of the people,
    The King of the people,
    The god of people,
    From the evil of the sneaky whisperer,
    Who whispers into the chests of the people,
    From among the Jinn and people."
    ---
    title = "Quran: A Reformist Translation"
    type = "translation"
    creator = ["Edip Yüksel", "Layth Saleh al-Shaiban", "Martha Schulte-Nafeh"]
    publisher = "Rainbow Press"
    language = "en"
    date = "2007"
    identifier = "urn:isbn:978-0979671500"



## VERSION

* `0.0.2` -- Remove the compression feature, and speficy metadata to be embedded.
* `0.0.1` -- Initial release.
