# Challenge 2 (11/04/2020)

Given a list of elements, a surpasser of an element 
is an element on its right hand side that is larger
than it. The surpasser count of an element is the
number of its surpassers. Return the maximum surpasser
count of a list.

## Premises

* List of elements may occupy max memory size;
* The set of elements are any a poset (orderable);
  
## Examples

```
msc of G,E,N,E,R,A,T,I,N,G is 6
msc of 10,3,4,5,2 is 2
```

## Solutions

### (50) Haskell by Hugo

```haskell
msc=maximum.ap(zipWith((length.).filter.(<)))tails
```

### (57) Julia by Ferrolho

```julia
msc(x)=maximum(count(>(x[i]),x[i:end]) for i=1:length(x))
```

### (76) Python by Mafalda

```python
msc=lambda l:max([len([x for x in l[e:] if x>l[e]]) for e in range(len(l))])
```
