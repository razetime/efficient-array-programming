# Dyalog APL

## General Tips
 - Some sets of symbols are parsed as *idioms* which are special cased to have more efficient implementations. You can see a rather comprehensive list on [APLcart.](https://aplcart.info/?q=idiom#)
 - The `dfns` library contains a few functions like `lisp` and `parse` which can be used to parsing/evaluation non-APL expressions or language implementation: [APLcart](https://aplcart.info/?q=expr%20parser) [eval,min,max](https://dfns.dyalog.com/)
 - The `dfns` library from the previous point also has a wealth of implementations of fast algorithms to common programming tasks in APL.
 - Asymptotic complexity is often hard to calculate for an APL program, since each primitive is optimized for specific arguments, but the generalized complexity can be calculated through understanding the implementation of each primitive. [Here's an overview from Rich Park.](https://www.youtube.com/watch?v=f0qhOKW0iw0)
 - `]runtime` and `dfns.cmpx` are indispensable tools for calculating the practical complexity of an algorithm. It is recommended to test with a wide range of inputs for an accurate comparison.
