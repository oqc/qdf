# The Quran Binary Format (QBF)

Fun attempt to create the smallest possbile file containing the
complete original Quran in the 28-letter Arabic alphabet in which it
was originally revealed (using 5bit code points).


## Rationale

The choice for 5bits is easy the first power of 2 that is larger then 28
is 5 (2^5 = 32).  So 5bits gives us a character space of 32, of which 28
are used for the Arabic letters, of the 4 remaining code points we need
one for the space and one for the verse separator.  Which leaves us with
an overhead of 2 unused code points on 32 (or ~6%)

Since files are usually written in bytes (8bits) we group our 5bit code
points by 8 to form 40bit blocks that can be interpreted both as 5 byte
and as 8 of our 5bit characters.  For padding on the back we use the
highest unused code point (all five bits set to `1`).


## Mapping

For mapping the [Abjad](http://en.wikipedia.org/wiki/Abjad_numerals)
system's ordering of the letters is used.  In the mapping we show the
Abjad value of a letter between parenthesis.

* `00000` -- **space**
* `00001` -- alif (1)
* `00010` -- baa (2)
* `00011` -- jim (3)
* ...
* `11011` -- za (900)
* `11100` -- gayn (1000)
* `11101` -- **(unused)**
* `11110` -- **verse delimiter**
* `11111` -- **padding**


## Expectations

We expect the raw binary size of the Quran with this format will be
around 250 kilobyte.




