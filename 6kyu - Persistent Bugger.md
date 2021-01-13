# 6kyu - Persistent Bugger.

## Instruction
Write a function, `persistence`, that takes in a positive parameter `num` and returns its multiplicative persistence, which is the number of times you must multiply the digits in `num` until you reach a single digit.

## Example
```JavaScript
persistence(39) === 3  // because 3*9 = 27, 2*7 = 14, 1*4=4
                       // and 4 has only one digit

persistence(999) === 4 // because 9*9*9 = 729, 7*2*9 = 126,
                       // 1*2*6 = 12, and finally 1*2 = 2

persistence(4) === 0   // because 4 is already a one-digit number
```

## Solutions

### JS

```JavaScript
function persistence(num) {
  let count = 0;
  let digits = num.toString();

  while(digits.length > 1) {
    digits = digits.split('').reduce((acc, cur) => acc * cur, 1).toString();
    count++;
  }

  return count;
}
```

### JS (recursive)
```JavaScript
function persistence(num, _count = 0) {
  const digits = num.toString().split('');

  if (digits.length === 1) {
    return _count;
  }

  const nextNum = digits.reduce((acc, cur) => acc * cur, 1);

  return persistence(nextNum, ++_count);
}
```
