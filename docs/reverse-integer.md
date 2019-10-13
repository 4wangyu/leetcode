---
id: reverse-integer
title: Reverse Integer
sidebar_label: Reverse Integer
---
## Description
<div class="description">
<p>Given a 32-bit signed integer, reverse digits of an integer.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> 123
<strong>Output:</strong> 321
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> -123
<strong>Output:</strong> -321
</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input:</strong> 120
<strong>Output:</strong> 21
</pre>

<p><strong>Note:</strong><br />
Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [&minus;2<sup>31</sup>,&nbsp; 2<sup>31&nbsp;</sup>&minus; 1]. For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.</p>

</div>

## Solution(javascript)
```javascript
/**
 * @param {number} x
 * @return {number}
 */
var reverse = function(y) {
    var reverseAbs = function(x){
        if (x == 0) return '';
        return x%10 + reverseAbs(Math.floor(x/10));
    }
    var limit = 2147483648;
    var rvsdY = reverseAbs(Math.abs(y));
    
    if(rvsdY > limit || y == 0) return 0;
    return parseInt((y < 0 ? '-' : '') + rvsdY);
};

```