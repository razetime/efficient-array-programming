# ngn/k

## General Tips

## Solved Examples
Since ngn/k is based on the k6 dialect, many of these examples will work in oK as well.


#### Solve [Insane Coloured Triangles](https://www.codewars.com/kata/5a331ea7ee1aae8f24000175) in strictly lower than O(n^2) time.

```
f:"RGB"{3!-n-:/+/x*/(3\6901)(3*3\n-1)+3\!n:#x}"RGB"?
```

Where `f` is the function to be run.
