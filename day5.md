# Challenge 5 (19/04/2020): The Princess, the Cake, and the Guillotine!

## Background

"Thou shalt not vex the princess or thee might loseth thy head" wast common knowledge among all villagers. And every year the dreadful day would arrive; the day someone would beest chosen to cutteth that lady birthday cake. And this year, thee wast the chosen one. 

The cake wast gorgeous, and long, very long; with white and black chocolate strips of various sizes. And the princess wast adamant, the lady wanted the largest piece of cake possible, but the lady wanted to has't the exact same amount of white and black chocolate.

Thee didn't wan't to loseth thy headeth, so thee hadst to beest extremely careful or face the dreaded guillotine!

## Specification

The function `cake` receives an array containing only 0's and 1's and returns the size of the largest consecutive substring having exactly the same number of 0's and 1's. 

**Note:** Extra marks if your solution works with arrays up to 50,000 binary numbers. Test it with these [three examples](https://github.com/hugoferreira/golf-during-covid/tree/master/data/day5) and PM me your results.

## Examples

```
cake([]) -> 0

cake([1]) -> 0

cake([0,0]) -> 0

cake([0,1]) -> 2

cake([1,0]) -> 2

cake([0,1,0]) -> 2

cake([1,0,1]) -> 2

cake([0,1,1,0]) -> 4

cake([1,0,1,1,0,1,0,0,0,0,1,1,1,1,1,1,1,1,0,0]) -> 12

cake([0,0,0,0,1,0,0,0,0,0,0,0,0,0,1,1,0,0,0,0,0,0]) -> 4

cake([0,0,0,1,1,1,0,0,1,1,0,1,1,1,0,0,0,1,1,0,1,1,0,1,0,1,0,1]) -> 20

cake([0,1,0,1,0,1,0,1,0,1,0,1,0,1,0,1,0,1,0,1,0,1,0,1,0,1,0,1]) -> 28
```

## Solutions

### (94) Javascript by Restivo (works with big input)
```javascript
cake=c=>{h={0:-1};m=t=0;c.map((s,i)=>{t+=s*2-1;h[t]?m=Math.max(m,i-h[t]):h[t]=''+i});return m}
```
