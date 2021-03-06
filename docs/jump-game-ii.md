---
id: jump-game-ii
title: Jump Game II
sidebar_label: Jump Game II
---
## Description
<div class="description">
<p>Given an array of non-negative integers, you are initially positioned at the first index of the array.</p>

<p>Each element in the array represents your maximum jump length at that position.</p>

<p>Your goal is to reach the last index in the minimum number of jumps.</p>

<p><strong>Example:</strong></p>

<pre>
<strong>Input:</strong> [2,3,1,1,4]
<strong>Output:</strong> 2
<strong>Explanation:</strong> The minimum number of jumps to reach the last index is 2.
    Jump 1 step from index 0 to 1, then 3 steps to the last index.</pre>

<p><strong>Note:</strong></p>

<p>You can assume that you can always reach the last index.</p>

</div>

## Solution(javascript)
```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var jump = function(nums) {
    let jumps = 0, end = 0, furthest = 0;
    
    for(let i = 0; i < nums.length-1; i++){
        furthest = Math.max(furthest, nums[i]+i);
        if(i === end){
            jumps++;
            end = furthest;
        }
    }
    
    return jumps;
};
```