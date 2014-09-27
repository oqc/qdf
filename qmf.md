# The Quran Metadata Format (QMF)

A metadata format for Quran texts, part of the [Quran Data Formats](https://github.com/oqc/qdf).
It can either be embedded in another file format (as per that file format's
specification), or alternatively it can be saved in a standalone file with the `.qmf` extension,
placed alongside the file/directory provides metadata for --
in carrying the same filename (except for the extension).

The format of the metadata is based on two stadards, that are themselves based on
other standards (mainly ISO-, IETF standards and RFCs).  As the data format
a subset of [TOML](https://github.com/toml-lang/toml) is used, which is quite similar to, yet
more advance and well-specified, then the (in)famous `INI` format.

To provide semantics to the property names we use a subset of the
[Dublin Core](http://en.wikipedia.org/wiki/dublin_core)
[metadata element set](http://dublincore.org/documents/dces) vocabulary.

QMF is always UTF-8 encoded.




## Example

This is what a `qmf` stanza looks like:

    title = "De Edele Koran"
    creator = "Sofian S. Siregar"
    publisher = "ICCN"
    date = "2000"
    language = "nl"
    type = "translation"
    identifier = "urn:isbn:9073355087"
    [en]
    title = "The Noble Quran"

As you can see it is basically a key-value mapping.

The TOML consists of three parts.  First a language agnostic part, followed by
an English (`[en]`) section (in TOML jargon sections are called "tables").

In the case above `title` is the only property that is "localized", but other
contender for localization is the name (or names) of the creator(s) of the text.

The keys in the file are all from the Dublin Core vocabulary and their exact use is
detailed in this document.


## Language codes

Language indentification tags are used as value of the `language` property, and as value of the section
headers.  The possible values are specified in [BCP74/RFC5646](http://tools.ietf.org/html/rfc5646).
The shortest language code that does properly covers the text at hand is preferred.


## Overview of keywords

We use the [dc metadata element set](http://dublincore.org/documents/dces)
vocabulary, narrowed down and possibly slightly extended to our purpose.
All terms may be either omitted, occure once, or contain a list of values.


#### title

The title of the document it describes.  May quite likely be localized.


#### creator

A person, or organization, that created the text: the author.  Please
use a list in case there is more then one primary author.

May quite likely be localized.


#### publisher

The organization that holds the publishing rights.


#### contributor

A person (or organization) who made minor contributions to the text.


#### date

When the text was first published, on the Gregorian calendar, formatted as a string.
Valid are: `"YYYY"`, `"YYYY-MM"` and `"YYYY-MM-DD"`.


#### description

A short description of the text.  May quite likely be localized.


#### type

The type of data it describes.
One of `"original"`, `"translation"`, `"transliteration"`, `"commentary"`
or `"paragraphing"`.


#### identifier

Here the ISBN can be supplied as a URN, for example `"urn:isbn:9073355087"`.

An identifier may also be made up as long as it is unique.


#### language

Contains the text's "language identification tag" as specified in [BCP74/RFC5646](http://tools.ietf.org/html/rfc5646).


#### rights

Used to specify the copyright notice or to state it resides in the public
domain.  Possible content licenses (like Creative Commons) can also be
provided here.  In case it is not know, the "Unknown" value should be supplied.


#### source

Link to the origin of this text, like the site it was downloaded from.
Please supply a list in case more then one origin is deemed noteworthy.


#### direction

This is the only key that is *not* part of Dublin Core. It specifies the
text direction and can be one of `"ltr"` and `"rtl"`.



## VERSIONS

* `0.0.1` -- Original specification.
* `0.0.2` -- Switched from N3 to the TOML format, and allow localization of specific bits of metadata (by using sections).
* `0.0.3` -- Added the "direction" key and the "transliteration" value for the "type" key.
* `0.0.4` -- Minor tweaks.
