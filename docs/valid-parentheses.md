---
id: valid-parentheses
title: Valid Parentheses
sidebar_label: Valid Parentheses
---
## Description
<div class="description">
<p>Given a string containing just the characters <code>&#39;(&#39;</code>, <code>&#39;)&#39;</code>, <code>&#39;{&#39;</code>, <code>&#39;}&#39;</code>, <code>&#39;[&#39;</code> and <code>&#39;]&#39;</code>, determine if the input string is valid.</p>

<p>An input string is valid if:</p>

<ol>
	<li>Open brackets must be closed by the same type of brackets.</li>
	<li>Open brackets must be closed in the correct order.</li>
</ol>

<p>Note that an empty string is&nbsp;also considered valid.</p>

<p><strong>Example 1:</strong></p>

<pre>
<strong>Input:</strong> &quot;()&quot;
<strong>Output:</strong> true
</pre>

<p><strong>Example 2:</strong></p>

<pre>
<strong>Input:</strong> &quot;()[]{}&quot;
<strong>Output:</strong> true
</pre>

<p><strong>Example 3:</strong></p>

<pre>
<strong>Input:</strong> &quot;(]&quot;
<strong>Output:</strong> false
</pre>

<p><strong>Example 4:</strong></p>

<pre>
<strong>Input:</strong> &quot;([)]&quot;
<strong>Output:</strong> false
</pre>

<p><strong>Example 5:</strong></p>

<pre>
<strong>Input:</strong> &quot;{[]}&quot;
<strong>Output:</strong> true
</pre>

</div>

## Solution(javascript)
```javascript
/**
 * @param {string} s
 * @return {boolean}
 */
var isValid = function(s) {
    const map = {
        ')': '(',
        ']': '[',
        '}': '{'
    };
    
    s = s.split('');
    let t = [];
    
    while(s.length) {
        if (!map[s[0]]) {
            t.push(s[0]);
            s.splice(0, 1)
        } else if (t.length && t[t.length - 1] === map[s[0]]) {
            t.splice(t.length - 1, 1);
            s.splice(0, 1);
        } else {
            return false;
        }
    }
    
    if(t.length) return false;
    
    return true;
};
```