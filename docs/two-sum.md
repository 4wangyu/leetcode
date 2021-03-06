---
id: two-sum
title: Two Sum
sidebar_label: Two Sum
---
## Description
<div class="description">
<p>Given an array of integers, return <strong>indices</strong> of the two numbers such that they add up to a specific target.</p>

<p>You may assume that each input would have <strong><em>exactly</em></strong> one solution, and you may not use the <em>same</em> element twice.</p>

<p><strong>Example:</strong></p>

<pre>
Given nums = [2, 7, 11, 15], target = 9,

Because nums[<strong>0</strong>] + nums[<strong>1</strong>] = 2 + 7 = 9,
return [<strong>0</strong>, <strong>1</strong>].
</pre>

</div>

## Solution(javascript)
```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
  var map = new Map();
  var len = nums.length;
  
  for(var i = 0; i < len; i++){
      var num = nums[i];
      var complement = target - num;
      if(map.has(complement)){
         return [map.get(complement), i];
      } else {
        map.set(num, i);
      }
  }
};
```