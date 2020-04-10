# Challenge 1 (10/4/2020)

Implement a function that given a list of 
natural numbers, returns the lowest number 
not present in the list.

## Premises

```
0 <= list size <= 2^16
len(unique(list)) = len(list)
```

## Examples

```
minFree of 1, 2, 3, 4, 5 returns 6
minFree of an empty list returns 1
minFree of 10, 5, 9, 2, 24, 3, 1 returns 4
```

## Solutions

### (Chars) Language by Name  

```haskell
cenas = cenas
```

### (24) Haskell by Mafalda   

```haskell
minFree x=head([1..]\\x)
```

### (72) Python by Mafalda   

```python
def minFree(l):return 1 if not l else min(set(range(1,max(l)+2))-set(l))
```
