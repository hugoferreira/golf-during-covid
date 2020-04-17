# Challenge 4 (17/04/2020): EHT CDOORRSSW AAAGMNR ACDIINORTY

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
- The program should disregard any punctuation `,!;-/_`, so for all intended purposes;
- The set of valid characters that comprise a word is `[a-zA-Z]`;
- The program is case-insensitive;
- There should be no repeated anagrams;
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
eginrs: resign,signer,singer
```

```
$> ana 4 < echo "Thou hast ignore the region where the ringer and the singer resigns. The signer, Has Kell"
hotu: thou
ahst: hast
ekll: kell
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

## Test Files

## Solutions