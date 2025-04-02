# Question 13: Longest Common Prefix.

## Problem Description

    Write a function to find the longest common prefix amongst an array of strings.
    if there is no common prefix, return an empty string "".

## Example 1;

Input: strs = ["flower","flow","flight"]
Output: "fl"

## Example 2:

Input: strs = ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.

## Constraints

1 <= strs.length <= 200
0 <= strs[i].length <= 200
strs[i] consists of only lowercase English letters if it is non-empty.

## Reducing the prefix string approach.

```js
var longestCommonPrefix = function (strs) {
  let prefix = strs[0];

  // Looping through the arrays of strings.
  for (let i = 1; i < strs.length; i++) {
    //Checks whether the current string starts with the prefix string.
    while (strs[i].indexOf(prefix) !== 0) {
      // Reduces the prefix string by one character to the right.
      prefix = prefix.substring(0, prefix.length - 1);
      console.log(prefix);
    }
  }
  return prefix;
};
```
