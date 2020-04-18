# Challenge 4 (17/04/2020): aabbcdfhiiiiiiilnnoorstttuu

## Background

An ancient book was found with the mysterious title _EHT CDOORRSSW AAAGMNR ACDIINORTY_. No less mysterious was the contents, that left linguists excited and puzzled for years about their meaning. Most postulated this book was nothing less than the rosetta stone for the long forgotten written language of atlantis; a dictionary of some sorts to 17th century english. All attempts to decode its grammar, though, failed. The book was organized into 27 chapters, and each chapter contained something like this:

```
VI --------------
...
eginor: ignore,region 
eginrr: ringer
eginrs: resign,signer,singer
...
```

It was Sir. Has Kell that recognized the true nature of the book, and it did so by crafting a beautiful short program capable of generating the full contents of all twenty-seven chapters.

## Specification

Given a text corpus as input, the program `ana n` generates all the possible anagrams, and their corresponding words, of length `n`. 

## Premises

- The input corpus is a list of words, separated by spaces ` ` or new lines `\n`;
- The program should disregard any punctuation (e.g. `,!;-/_`) for all intended purposes;
- The set of valid characters that comprise a word is `[a-zA-Z]`;
- The program is case-insensitive;
- There should be no repeated anagrams, e.g. `abc = bca = cba`; the one to appear is the one that is lexicographically ordered, i.e., `abc`.
- For each anagram, there should be no repeated corresponding words;
- Both the anagrams and the corresponding words are to be output in lexicographic ascendent order;
- Each anagram appears in a new line;
- Anagrams are separated by words with a semi-colon `: `;
- Words are separated by commas `,`; 
- You must read the corpus from _stdin_ and output the result to _stdout_.

## Examples

```
$> ana 6 < echo "Thou hast ignore the region where the ringer and the singer resigns. The signer, Has Kell"
eginor: ignore,region 
eginrr: ringer
eginrs: signer,singer
```

```
$> ana 4 < echo "Thou hast ignore the region where the ringer and the singer resigns. The signer, Has Kell"
ahst: hast
ekll: kell
hotu: thou
```

```
ana 4 < echo "Thou.hast.ignore.the.region.where.the.ringer.and.the.singer.resigns.The.signer,Has.Kell!"
ahst: hast
ekll: kell
hotu: thou
```

```
$> ana 2 < echo "Thou hast ignore the region where the ringer and the singer resigns. The signer, Has Kell"
```

```
$> ana 3 < echo "cab"
abc: cab
```

```
$> ana 3 < echo ""
```

```
$> ana 3 < echo "cba aaaa abc bbbb abc bca zzzz"
abc: abc,bca,cba
```

```
$> ana 3 < echo "bca bcd abc acb cdb the abc"
abc: abc,acb,bca
bcd: bcd,cdb
eht: the
```

## Test Files

* `ana 5` [Shakespeare's Love's Labour's Lost](data/day4/loves-labours-lost.in) produces [this output](data/day4/loves-labours-lost.ana5).

## Solutions
