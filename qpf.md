# The Quran Paragraphing Format (QPF)

Specify paragraphing for Quran texts.

Many Quran text formats put one verse on one line (like format used on
the popular [Zekr](www.zekr.org) website).  These text have no paragraph
breaking style other then verses.

In this format break styles can be specified.


## Using the files

On each line paragraph break is set by a number:

  * `0` -- no paragraph break
  * `1` -- a small break
  * `2` -- a larger break
  * ...

Larger then "1" or "2" may be ignored by the interpreting software.

Anything after the first character is ignored, this makes `9` the
'biggest' paragraph separator and `0` the smallest.  The additional
character on a line may be used for other purposes (like commenting).

Comments on the same line as a parapgraphing number should be prefixed
with ` -- ` (that being a space, 2 hyphens and one more space).

As the last verse of a chapter needs no extra break, this line is
ignored and can therefore be safely used as chapter label to make the
files more 'human readable'.  The breaks for  verse 1:1 till 2:4 (the
first 11 verses of the Quran) could look like this:

    "2\n0\n0\n1\n0\n0\n1\n==2==\n0\n0\n0\n0"

Like the bismallah being specified only once in the QTF format, the
break after the bismallah is specified only once in this format.
