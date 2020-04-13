# Challenge 3 (12/04/2020)

Given a list of summable things, the maximum segment sum is highest value given by summing all the elements of a contiguous group of items. In this problem, you'll have to find the highest value given by the sum of all the elements of a non-contiguous subsequence of the original list.

## Premises

- There are no non-contiguous subsequences of a list with two or fewer elements (duh!);
- A non-contiguous subsequence is still a sequence, but which has at least one of the constituting elements originally not contiguous to the others (left or right);
- As long as the elements are summable, there are no additional constrains;
- Lists are finite.

## Examples

```
mncss [-4,-3,4] returns 0 (given by [-4,4])
mncss [-4,-3,-7,2,1,-2,-1,-4] returns 2 (given by [2,1,-1])
mncss [1,2,3,4] returns 8 (given by [1,3,4])
mncss [2,4] is an invalid input with non-specified output
```

## Solutions

### (57) Haskell by Hugo (based on Restivo)

```haskell
mncss l=maximum$sum<$>(subsequences l\\(inits l>>=tails))
```

### (58) Haskell by Restivo
```haskell
mncss l=maximum$map sum(subsequences l\\(inits l>>=tails))
```

### (60) Haskell by André Silva
```haskell
-- point-free version of Restivo's solution
import Data.List
import Control.Applicative
import Control.Arrow
import Control.Monad
mncss=liftA2(\\)subsequences(tails>=>inits)>>>maximum.map sum
```

### (62) Haskell by André Silva
```haskell
mncss x=maximum$map sum[y|y<-subsequences x,not$isInfixOf y x]
```

### (75) Julia by Ferrolho
```julia
mncss(x)=maximum(sum(x[s]) for s=subsets(1:length(x)) if any(≠(1),diff(s)))
```

### (125) Python by António
```python
s=lambda l:max(l)if max(l)<0else sum([max(x,0)for x in l])
mncss=lambda l:max([s(l[:i])+s(l[i+1:])for i in range(1,len(l)-1)])
```
