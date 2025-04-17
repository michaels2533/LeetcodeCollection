
**Prompt**
Given two strings s and t, return true if t is an anagram of s, and false otherwise. 

**Example 1**
Input: s = "anagram", t = "nagaram"

Output: true

**Example 2**
Input: s = "rat", t = "car"

Output: false

**Constraints**
1 <= s.length, t.length <= 5 * 104
s and t consist of lowercase English letters.
 

Follow up: What if the inputs contain Unicode characters? How would you adapt your solution to such a case?

```js
// Frequency Object Approach. 
var isAnagram = function(s, t) {
    
  if(s.length !== t.length) return false;

   const freqS = {}
   const freqT = {}

   for(let i = 0; i < s.length; i++) {
    //If the character exists within the freq obj; update the count. 
    if(freqS[s[i]]) {
        freqS[s[i]]++;
     }
    if(freqT[t[i]]) {
        freqT[t[i]]++;
     } 
     // If the character isn't in the freq obj, add an entry. 
    if(!freqS[s[i]]) {
        freqS[s[i]] = 1
     }
     if(!freqT[t[i]]) {
        freqT[t[i]] = 1;
     }
   }

 const objectKeys = Object.keys(freqS);
 for(let j = 0; j < objectKeys.length; j++) {
    if(freqS[objectKeys[j]] !== freqT[objectKeys[j]]) {
        return false;
    }
 }
 return true;
};
```

// String Sort Approach
```js
var isAnagram = function(s, t) {
    
    // Sort the input strings. 
    sSorted = s.split('').sort().join('');
    tSorted = t.split('').sort().join('');

  // Compare the strings.
  return sSorted === tSorted
```