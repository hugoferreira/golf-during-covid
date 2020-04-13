# Challenge 3 (12/04/2020)

## Premises

## Examples

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
