# Challenge 6 (26/04/2020): Niven Numbers

## Specification

A niven number is a non-negative number that is divisible by the sum of its digits.

Write a function/method named `niven` which prints all the niven numbers from 0 to 100 inclusive, each on their own line. The function needs to compute the solution, i.e., it is not acceptable to use any pre-computed data structure or solution.

Source: https://code-golf.io/niven-numbers

## Solutions

### (21) APL by Hugo

```apl
niven←⍸0=⍳|⍨1⊥10⊥⍣¯1⍳
```

You can read about this [here](http://hugosereno.eu/blog/2020/04/26/golfing-in-apl-during-covid/) or [try it online](https://tio.run/##SyzI0U2pTMzJT///Py@zLDXvUduER707DGwf9W6uedS7wvBR11JDAyDxqHfxofWGQNH/j/qmKgBVKYCVKxgaGPwHAA).

### (54) JavaScript by Restivo [try it online](https://tio.run/##y0osSyxOLsosKNEts/j/Py@zLDXPNt7Wrjotv0gjz9bQOs/G0ABIamtr5qlq5OkbGmjnqRoa1Bho1tQUFGXmlWjkadZCtGlo/gcA)

```javascript
niven=_=>{for(n=0;n<101;n++)n%(n/10+n%10|0)||print(n)}
```

### (66) Haskell by Mafalda
```haskell
niven=[x|x<-[1..100],x`mod`(sum(map(\x->read[x]::Int)(show x)))<1]
```

### (62) Python by Mafalda
```python
def niven():[print(n)for n in range(1,101)if n%(n//10+n%10)<1]
```

### (73) Python by Duarte

```python
def niven():[print(i)for i in range(1,101)if i%sum([*map(int,str(i))])<1]
```

[Try it online!](https://tio.run/##LcwxCoAwDADAr2QREulgcRHxJ@Ig2GoGY0mr4OtjB/fj0luOS/ohqdkWIgg/QZDGOSlLQaZ4KTCwgK6yB/TOd544Ajf5PnFuzzVhlS4XrZoWmvxi/2If)
