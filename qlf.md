# The Quran LaTeX Format (QLF)

Is a proper [LaTeX](http://en.wikipedia.org/wiki/LaTeX) subset to semantically structure Quran texts.
The extension is `.qlf` and the encoding is expected to be UTF-8.

This standard has been created to allow richer markup, specifically:
  * managable Arabic text
  * allow normal and large linebreaks after verses AND within verses
  * headings
  * links
  * rich footnotes (all of LaTeX can technically be used)

Two documents are currently being prepared with this format:
 1. the QRT in English
 2. a translation of the QRT to Dutch

## Splitting in files

Splitting a Quran text in to one file per chapter is a good practice.


## Compression

GZip is used to compress texts.


## Design goals:
  * should be trivial to export an `oqf` file to `zqf`
  * to be processed with LaTeX: digital formats are important
  * in browser parsing of this format should be doable


## VERSIONS

* `0.0.1` -- original specification
