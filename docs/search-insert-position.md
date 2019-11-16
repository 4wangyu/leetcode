---
id: search-insert-position
title: Search Insert Position
sidebar_label: Search Insert Position
---
## Description
<div class="description">
<p>Given a sorted array and a target value, return the index if the target is found. If not, return the index where it would be if it were inserted in order.</p>

<p>You may assume no duplicates in the array.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> [1,3,5,6], 5
<strong>Output:</strong> 2
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> [1,3,5,6], 2
<strong>Output:</strong> 1
</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input:</strong> [1,3,5,6], 7
<strong>Output:</strong> 4
</pre>

<p><strong>Example 4:</strong></p>

<pre>
<strong>Input:</strong> [1,3,5,6], 0
<strong>Output:</strong> 0
</pre>

</div>

## Solution(javascript)
```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
var searchInsert = function(nums, target) {
    let left = 0, right = nums.length - 1;
    
    while(left <= right) {
        const mid = Math.floor((left + right)/2);
        if(nums[mid] === target) {
            return mid;
        } else if (nums[mid] > target && (mid === 0 || nums[mid-1]<target)) {
            return mid;
        } else if (nums[mid] < target && (mid === nums.length-1 || nums[mid+1]>target)) {
            return mid+1;
        } else if (nums[mid] > target) {
            right = mid-1;
        } else if (nums[mid] < target) {
            left = mid+1;
        }
    }
};
```