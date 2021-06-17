# Dyalog APL

## General Tips
 - Use Rank(⍤) instead of Each(¨) since Rank is better optimized to work on cells.
 - Some sets of symbols are parsed as *idioms* which are special cased to have more efficient implementations. You can see a rather comprehensive list on [APLcart.](https://aplcart.info/?q=idiom#)
 - The `dfns` library contains a few functions like `lisp` and `parse` which can be used to parsing/evaluation non-APL expressions or language implementation: [APLcart](https://aplcart.info/?q=expr%20parser) [eval,min,max](https://dfns.dyalog.com/)
