# Challenge 7 (01/05/2020): ☭ The Portuguese Communist Party ☭

## Background

Jerónimo de Sousa and his gang are playing Dominoes in Alameda Dom Afonso
Henriques on this International Worker's Day.

They are growing old and getting pretty tired of the same dull rules of Dominoes
so they decide to give it a twist.

One by one, they grab a piece of domino from an infinite stack of dominoes (yes,
this stack is higher than Torre de Belém). First to win is the one that has the
top part of their dominoes matching the bottom part.

Legend has it that they will be playing this game until the End of Time...

## Specification

Given a (finite) collection of dominoes, each containing two strings, one on top
and another on bottom, the task is is to make a list of these dominoes, with
repetitions allowed, so that the string we get by reading off the symbols on the
top is the same as the string of symbols on the bottom.

Create a function `pcp s`, that returns the string that matches, if such list
exist, otherwise it returns `no`.

See [Example 1](#example-1) for clarity.

`s` is a set of 2-tuples, e.g `{(bc, ca), (a, ab)}`, where the first element is
a string that is the top part of a "domino" and the second element is the bottom
part. The alphabet of the strings is limited to `{a, b, c}`. The strings are not
empty and can have repeated characters.

If such list exists, the matching string should be returned. Otherwise, the
output is `no`.

Any matching string solves the task (or `no` if no solution is possible).

The input set is not empty, it does not have repeated dominoes and it is not
necessary to use all dominoes from input in the solution. An empty solution (e.g
not using any domino) is not allowed.

## Technicalities

For golf purposes, only the definition and declaration of the function `pcp`
count. Input of the `pcp` function should already be "parsed" i.e you do not
need to implement input / output from stdin / to stdout inside `pcp`.

## Examples

### Example 1:

`pcp {(bc, ca), (a, ab), (ca, a), (abc, c)}` -> `abcaabc`

Because the sequence of dominoes where the concatenated top string matches the
bottom string is `(a, ab)`, and then `(bc, ca)`, and then `(a, ab)` again, and
finally `(abc, c)`. Note that repetitions are allowed and the piece `(ca, a)`
was not used.

![dominoes1](data/day7/dominoes1.png)

### Example 2:

`pcp {(abc, ab), (ca, a), (acc, ba)}` -> `no`

No solution is possible. It's not possible to have a list of dominoes where the
top string matches the bottom string.

## Test Cases

`pcp {(bc, ca), (a, ab), (ca, a), (abc, c)}` -> `abcaabc`  
`pcp {(abc, ab), (ca, a), (acc, ba)}` -> `no`  
`pcp {(a, a), (b, b)}` -> `a` or `b` or `aa` or `ab` or ...  
`pcp {(c, ab), (aa, b)}` -> `no`  
`pcp {(ab, aa), (bba, bb), (a, baa)}` -> `bbaabbbaa`
