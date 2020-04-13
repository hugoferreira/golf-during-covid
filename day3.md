### (58) Haskell by Restivo
```haskell
mncss l=maximum$map sum(subsequences l\\(inits l>>=tails))
```

### (62) Haskell by André Silva
```haskell
mncss x=maximum$map sum[y|y<-subsequences x,not$isInfixOf y x]
```
