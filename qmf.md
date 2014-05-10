# The Quran Metadata Format (QMF)

This format stores metadata for the other Quran Data Formats. It uses the
[N3](http://en.wikipedia.org/wiki/Notation3) schema (a plaintext format)
and the [Dublin Core](http://en.wikipedia.org/wiki/Dublin_Core)
[Metadata Element Set](http://dublincore.org/documents/dces) vocabulary.
Both of these technologies are [w3c](http://w3c.org) standards.

The extension for Quran Metadata Format files is `.qmf`, and it should
be placed alongside the file(s)/directory provides metadata for --
in practice this means it should have the same name (except for the
extension).


## Example

A typical `qmf` file looks like this:

    @prefix : <http://purl.org/dc/elements/1.1/>.
    <>
    :title      "De Edele Koran";
    :creator    "Sofian S. Siregar";
    :publisher  "ICCN";
    :date       "2000";
    :language   "nl";
    :format     "qtf";
    :type       "translation";
    :identifier "URN:ISBN:90-73355-08-7".

The first line includes the Dublin Core Elements vocabulary.
The second line starts an unnamed resource, the conscutive lines describe
properties their values on the unnamed resource.


## Overview of keywords

We use the [DC Metadata Element Set](http://dublincore.org/documents/dces)
vocabulary, narrowing it down to our purpose.
Except for the title (which must occure exactly once), all terms may be omitted or
repeated if that seems appropriate.

The terms below are understood as part of the Quran Metadata Format:

#### title

The title of the text it describes.

#### creator

An person (or organization) that created the text: the author.  Please
repeat this in case there are more then one primary author.

#### publisher

The organization that holds the publishing rights.

#### contributor

A person (or organization) who made minor contributions to the text.

#### date

When the text was first published.  Valid are: YYYY, YYYY-MM and
YYYY-MM-DD.

#### description

A short description of the text.

#### type

The type of data it describes.
One of `"original"`, `"translation"`, `"commentary"` or `"paragraphing"`. 

#### format

The format of the data it describes.
One of `"qtf"` (for the [Quran Text Format](https://github.com/oqc/qdf/qtf.md)),
`"qlf"` (for the [Quran LaTeX Format](https://github.com/oqc/odf/qlf.md)) or
`"qpf"` (for the [Quran Paragraphing Format](https://github.com/oqc/odf/qpf.md)).

#### identifier

Here the ISBN can be supplied as a URN, for example
"URN:ISBN:90-73355-08-7", an identifier may also be made up as long as
it is unique.

#### language

Contains a "language identification tag" as specified by the Internet
Engineering Task Force (IETF) in document
[BCP 47](http://tools.ietf.org/html/bcp47). Unless it clearly leads to
ambiguity the shorter '2 digit' codes are preferred.

#### rights

Used to specify the copyright notice or to state it resides in the public
domain.  Possible content licenses (like Creative Commons) can also be
provided here.

#### source

Link to the origin of this text, like the site it was downloaded from.
May be repeated in case more then one origin is deemed noteworthy.


## VERSIONS

* `0.0.1` -- original specification
