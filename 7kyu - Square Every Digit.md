# 7kyu - Square Every Digit

## Instruction
For example, if we run `9119` through the function, `811181` will come out, because `9^2` is `81` and `1^2` is `1`.

### Notes
The function accepts an integer and returns an integer

## Solutions

### JS

```JavaScript
function squareDigits(num) {
  return +num.toString().split('').map(function (item) {
    return Math.pow(item, 2);
  }).join('');
}
```