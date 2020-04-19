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

### (165) Python by Duarte (w/o imports)
```python
import re as e
import sys as y
from collections import defaultdict as d
o,r=sorted,d(set)
[r["".join(o(w))].add(w)for w in e.split("\W"," ".join(y.stdin).lower())if len(w)==int(y.argv[1])]
[print(w+": "+",".join(o(r[w])))for w in o(r)]
```

### (168) Haskell by Hugo (230 w/o IO)

```haskell
-- IO ------------------------------------------------------------
main=do;[n]<-getArgs;i<-getContents;putStrLn$ana(read n::Int)i
-- ana n s -------------------------------------------------------
s=sort;f#o=f$(.s).o.s;ana n x=concatMap(\g->s g!!0<>": "<>intercalate","(s g)<>"\n")$groupBy#(==)$sortBy#compare$nub[e|e<-wordsBy(not.isLetter)$toLower<$>x,n==length e]
```

### (224) JavaScript by Restivo

```javascript
ana=(n,s)=>{h={};a=[...(new Set(s.split(/[^\w]+/).map(w=>w.toLowerCase()).filter(w=>w.length==n)))].sort().forEach(w=>{o=w.split('').sort().join('');h[o]?h[o].push(w):h[o]=[w]});r='';for (w in h)r+=w+': '+h[w]+'\n';return r}
```

### (227) Python by Mafalda (335 w/o IO)

```python
## IO
def readInput():
 i = []
 while True:
  try: l = input().split()
  except EOFError: break
  i=i+l
 return i

## ana n s
def ana(n, l):
 a = d(list)
 rp = '|'.join(map(esc, p))
 for w in set(chain(*[split(rp,w.lower()) for w in l])):
  if(len(w)==n): a["".join(sorted(w))].append(w)
 [print(k+": "+",".join(sorted(a[k]))) for k in sorted(a.keys())]
```

### (231) Perl by by Restivo
```perl
use List::MoreUtils qw(uniq);

while(<STDIN>){$_=~s/[^\w]+/ /g;@w=grep{length $_==$ARGV[0]}(split/ /,$_);foreach(@w){$s=join"",sort split//,lc$_;$h{$s}=$h{$s}." ".lc$_;}}foreach $k(sort keys%h){$w=join ",",uniq sort grep{$_ ne''}split/ /,%h{$k};print"$k: $w\n";}
```
