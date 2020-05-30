# Challenge 8 (30/05/2020): The Sudoknightking's puzzle

## Background

"*Here, look at this!*" he said while using his daughter's markers to highlight the cells. She wondered what all those colorful, blocky figures would mean, what secrets would hide behind the beautiful patterns emerging from her daddy's cryptic doodles. She could see snowflakes, birds, crosses, and strange little clouds. "*According to the knight's rule, you cannot put the same number here, nor here or here*" — a starship, she wondered. "*From the kings' rule, you should also scratch these*" — and there are the headlights. "*So you are forced to accept that the 2 should go into this square. Wonderful, right?"*. Wonderful indeed! And at this moment, she has made her mind: when she grows up, she would become... a firewoman.

## Specification

Based on a recent favorite YouTube video that most participants have watched, I hereby declare it worthwhile to solve the Sudoknightking by golfing as hard as you can. The rules? Oh, you need those? And they'll never be perfect, will they? You'll always find some lurking bug, some misspecification, that'll allow you to bend the fabric of your favorite language and gain an advantage over your component. Now, I know exactly how to deal with this type of behavior: `/ignore`.

All rules of classic sudoku apply: you have to solve the puzzle in a 9x9 grid composed of 9 smaller 3x3 grids. Besides classic sudoku, (1) any two cells separated by a knight's move, or (2) king's move (in chess) cannot contain the same digit. Also, (3) any two orthogonally adjacent cells cannot contain consecutive digits.

You function receives a vector of 81 values, from 0 to 9, where 0 represents an empty cell (any number that is not zero is "pinned" and thus cannot be changed); it returns a vector of 81 values, from 1 to 9, fulfilling the aforementioned rules.

## Examples

```
skk 000000000000000000000000000000000000001000000000000200000000000000000000000000000
483726159726159483159483726837261594261594837594837261372615948615948372948372615
```
