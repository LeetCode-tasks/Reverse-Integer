# Reverse Integer

Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range `[-2^31, 2^31 - 1]`, then return 0.

**Assume the environment does not allow you to store 64-bit integers (signed or unsigned).**

_Example 1:_

Input: `x = 123`

Output: `321`


_Example 2:_

Input: `x = -123`

Output: `-321`


_Example 3:_

Input: `x = 120`

Output: `21`


_Example 4:_

Input: `x = 0`

Output: `0`


## Solution in JavaScript

```
var reverse = function(x) {
    let z = ''
    let isReady = true
    let answer
    if (x < 0) {
        x = -x
        isReady = false
    }
    x += ''
    for (let i = x.length - 1; i >= 0; i--) {
        z += x[i];
    }
    
    if (isReady) {
        answer = Number(z)
    } else {
        answer = -Number(z)
    }
    
    
    return answer >= -Math.pow(2, 31) && answer <= Math.pow(2, 31) - 1 ? answer : 0
};
```
