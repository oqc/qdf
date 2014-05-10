# The Quranic Data Formats (QDF)

This [repository](https://github.com/oqc/qdf) contains the specification
of file formats for storing Quranic data.  The secifications are
collaborated on by the [Open Quran Collective](https://github.com/oqc),
anyone using the formats is encouraged contribute to any future
developments.

The specifications are not restricted in any way of form so can be
considered [open standards](http://en.wikipedia.org/wiki/Open_standard),
or [open formats](http://en.wikipedia.org/wiki/Open_format).

The formats are:

* [Quran Text Format](http://github.com/oqc/qdf/blob/master/qtf.md) (QTF) --
  Simple one-line-per-verse format, mostly compatible with the format
  used by [zekr.org](http://zekr.org).
* [Quran LaTeX Format](http://github.com/oqc/qdf/blob/master/qlf.md) (QLF) --
  Subset of the [LaTeX](http://en.wikipedia.org/wiki/LaTeX) document
  markup language, specifically tailored for rich Quranic content (e.g.:
  footnotes, Arabic text, links, headings).
* [Quran Metadata Format](http://github.com/oqc/qdf/blob/master/qmf.md) (QMF) --
  Uses the [N3](http://en.wikipedia.org/wiki/Notation3) format with a
  subset of the [Dublin Core](http://en.wikipedia.org/wiki/Dublin_Core)
  [Metadata Element Set](http://dublincore.org/documents/dces)
  vocabulary.
* [Quran Paragraphing Format](http://github.com/oqc/qdf/blob/master/qpf.md) (QPF) --
  Simple one-line-per-verse format for adding paragraphing to Quranic
  texts, especially useful with originals and translations in the QTF
  format (as they lack paragraphs).
* [Quran Binary Format](http://github.com/oqc/qdf/blob/master/qbf.md) (QBF) --
  Fun attempt to create the smallest possbile file containing the
  complete original Quran in the 28-letter Arabic alphabet in which it
  was originally revealed (using 5bit code points).


## History

These standards were introduced to facilitate collaboration on Quran
study and publication in the age of the internet.

Only the QTF was in use before before it was specified as part of this
project, and is sometimes refered to as the [zekr.org](http://zekr.org)
format as it released many Quran textx (originals and translations) that
mostly conform the QTF specificetion.


## Goals

* facilitate online collaboration
* interoperability between different viewer/editor applications
* allow rich styling and annotation (where that makes sense)


## Future proofing and backward compatibility

For all format we try to maintain backward compatible, the version
number of the format will reflect a major version bump whenever a
backwards incompatible change is made (as specified in the
[semver.org](http://semver.org), where this is called "breaking puplic
API).

We also try to keep formats future proof where possible, avoiding the
need to break backward compatibility.

