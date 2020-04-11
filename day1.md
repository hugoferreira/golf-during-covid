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

### (42) Javascript by Restivo (recursive)

```javascript
minFree=(S,i=1)=>S.has(i)?minFree(S,++i):i
```

### (45) JavaScript by Restivo (iterative)
```javascript
minFree=(S,i=0)=>{while(S.has(++i));return i}
```

### (53) Javascript by Restivo (lodash,sort,reduce)
```javascript
minFree=(S)=>_.sortBy(S).reduce((r,v)=>r==v?r+1:r,1)
```

### (55) Javascript by Restivo (lodash,difference)
```javascript
minFree=(S)=>_.difference(_.range(1,S.length+2), S)[0]
```

### (64) Javascript by Restivo (lodash,sort,find)
```javascript
minFree=(S)=>_.sortBy(S).findIndex((v,i)=>v!=i+1)+1||S.length+1
```

### (23) Haskell by Hugo (fixed by Restivo)

```haskell
minFree x=([1..]\\x)!!0
```

### (22) Haskell by Hugo

```haskell
minFree=head.([1..]\\)
```

### (24) Haskell by Mafalda   

```haskell
minFree x=head([1..]\\x)
```

### (48) Python by Mafalda   

```python
minFree=lambda x:min(set(range(1,2**15))-set(x))
```

### (63) Rust by André Silva
```rust
let minFree=|x:Vec<u64>|(1..).filter(|i|!x.contains(i)).next();
```

### (54) Rust untyped by André Silva
```rust
let minFree=|x|(1..).filter(|i|!x.contains(i)).next();
```

### (47) Scala by André Silva
```scala
def minFree(x:Seq[Int])=(1 to 2<<15).diff(x)(0)
```

### (38) Scala untyped by André Silva
```scala
def minFree(x)=(1 to 2<<15).diff(x)(0)
```

### (33) Scalaskell by André Silva
```scala
minFree x=(1 to 2<<15).diff(x)(0)
```

### (51) JavaScript by André Silva
```javascript
minFree=x=>{for(i=1;;i++)if(!x.indexOf(i))return i}
```

### (64) Swift by Tiago Almeida
```Swift
let minFree={(l:[Int])in l.sorted().reduce(1){$0==$1 ?$1+1:$0}}
```

### (41) Julia by Henrique Ferrolho
For `0 <= list size <= 2^16`
```julia
minFree(x::Set{Int})=setdiff(1:2^16,x)[1]
```

### (31) Julia untyped by Henrique Ferrolho
For `0 <= list size <= 2^16`
```julia
minFree(x)=setdiff(1:2^16,x)[1]
```

### (56) Julia by Henrique Ferrolho
For `0 <= list size <= 2e16`
```julia
minFree(x::Set{Int})=for i=1:Int(2e16) i∉x&&return i end
```

### (41) Julia untyped by Henrique Ferrolho
For `0 <= list size <= 2e16`
```julia
minFree(x)=for i=1:2e16 i∉x&&return i end
```

### (64) Python by António Ramadas
```python
minFree=lambda l:[i for i in range(1,len(l)+2) if i not in l][0]
```
