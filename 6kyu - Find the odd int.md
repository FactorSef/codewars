# 6kyu - Find the odd int

## Instruction
Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.

## Solutions

### JS

```JavaScript
function findOdd(A) {
  const counts = A.reduce(function (prev, cur) {
    prev[cur] = ++prev[cur] || 1;
    return prev;
  }, {})

  return +Object.keys(counts).find(key => counts[key] % 2)
}
```
