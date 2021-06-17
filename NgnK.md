# ngn/k

## General Tips

## Solved Examples
Since ngn/k is based on the k6 dialect, many of these examples will work in oK as well.


#### Solve [Insane Coloured Triangles](https://www.codewars.com/kata/5a331ea7ee1aae8f24000175) in strictly lower than O(n^2) time.

`f:"RGB"{3!-n-:/+/x*/(3\6901)(3*3\n-1)+3\!n:#x}"RGB"?`

The idea behind this question is to apply an inverted pascal's triangle-type operation repeatedly to a string until a desired result is reached.

From ngn:

> (Similar to the) technique for computing the cell at i,j from sierpinski's triangle from the bits of i and j, this expression is doing the same but for "tripinski's" triangle, so it uses ternary digits and it computes a whole row of the triangle, so j ranges from 0 to i.

There's a way to generalize this using the pascal triangle, mod 3, where with `R=0, G=1, B=2`, a pattern emerges:

```
 1
 1 1
 1 2 1
 1 0 0 1
 1 1 0 1 1
 1 2 1 1 2 1
 1 0 0 2 0 0 1
 1 1 0 2 2 0 1 1
```

This can further be clarified by negating every odd column.

> in other words, the result is (-1)^n times some linear combination of the input with the binomial coefficients as weights.(ngn)

This formula, combined with some well hardcoded rows, give us the required function for the problem.

```
f:"RGB"{3!-n-:/+/x*/(3\6901)(3*3\n-1)+3\!n:#x}"RGB"?
                                              "RGB"? Determine indices of each character in "RGB"                                                     
       {                                     } run function:
                                         n:#x  set n to string length
                                        !      range 0..n-1
                                      3\       convert to base 3 matrix
                            (3*3\n-1)          n-1 in base 3
                                     +         add to matrix
                                               index using this into:
                    (3\6901)                   first 3 rows of pascal's triangle
                 x*/                           fold from left with original indices as start value
               +/                              fold from left with addition
           n-:/                                negate the sum n times
          -                                    negate again
        3!                                     3 modulo
  "RGB"                                        use that to index into "RGB" again 
```

Where `f` is the function to be run.
