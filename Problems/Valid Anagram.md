## Problem Domain Valid Anagram
-Given two strings `s` and `t`, return `true` _if_ `t` _is an anagram of_ `s`_, and_ `false` _otherwise_.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

[Valid Anagram](https://leetcode.com/problems/valid-anagram/)

### Test cases

```python
**Example 1:**

**Input:** s = "anagram", t = "nagaram"
**Output:** true

**Example 2:**

**Input:** s = "rat", t = "car"
**Output:** false
```

### Algorithm Explanation

First we compare the lengths of the strings, if the length isnt the same we can return False, as they cannot be an anagram with differing lengths. 

then we call the native sorted method on the strings and compare the outputs, if the input strings are anagrams the sorted strings will be an exact equals.  so we can return True,

finally as a catch-all we would return False, If we dont trigger either of the previous exit cases, we can return a False. 


### Code

```Python
class Solution:
def isAnagram(self, s: str, t: str) -> bool:
	 # if strings are not of equal length they cannot possibly be anagrams
	if len(s) != len(t):
		return False
	# once we sort the strings they should be perfect matches of eachother so we 
	#can return true  
	if sorted(s) == sorted(t):
		return True
	 # if we havent hit either previous return conditional we can return false.
	return False

```

### BigO Time

This method is O(n) time where N is the number of characters in the input strings.


### BigO Space

This method is also O(n) space, and it is fairly memory light, since we are not creating any 
the downside of this is the extra memory space required to perform the sort. depending on the sorting method happening in the background this can be ineffiecent. 

### Design choices and why

This method is simple but not terribly fast, we call the built in Len and sorted methods which arnt particularly effiencent. we could impliment this with a hashmap to get much faster time. 


### test cases

___

# Hashmap implimentation

## Problem Domain Valid Anagram
-Given two strings `s` and `t`, return `true` _if_ `t` _is an anagram of_ `s`_, and_ `false` _otherwise_.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

[Valid Anagram](https://leetcode.com/problems/valid-anagram/)

### Test Cases
```python
**Example 1:**

**Input:** s = "anagram", t = "nagaram"
**Output:** true

**Example 2:**

**Input:** s = "rat", t = "car"
**Output:** false
### Algorithm Explanation
```

### Code

```Python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        
        # if strings are not of equal length they cannot possibly be anagrams
        if len(s) != len(t):
            return False
        # creating our empty dicts (hashmaps)
        countS, countT = {},{}
        
        # populating the hashmaps with key value pairs for each character in the input string
        for i in range(len(s)): # we can use either string for len here since we've verified the lengths match.
            # countS is our empty dict (hashmap), S is our input string, i is our for loop index
            countS[s[i]] = 1 + countS.get(s[i],0)
            countT[t[i]] = 1 + countT.get(t[i],0)
            
        for c in countS: # for character in now populated countS dict. 
            # if countS[c] != countT[c]: <<< careful here! countT[c] will throw a key Error! since the key does not exist. 
            if countS[c] != countT.get(c, 0): # if the character in dict S does not match dict T return false > not anagrams
                return False
            
        # if we dont return False from any of the previous checks, we know we have an anagram! return True
        return True

```
### BONUS CODE
```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return Counter(s) == Counter(t)
```

### Algorithm Explanation

We again check if the lengths are the same

### BigO Time
O(n) where N is the number of characters in both the strings, otherwise visible as O(s + t)

### BigO Space
 O(s + t) This solution is slightly more memory intensive due to the use of the Hashmaps
This method is memory expensive since we create two hashmaps and must itterate through them.

### Design choices and why

Hashmap - (dict key:value pair)

different hashmap for each string.

Example s = "anagram" t = "nagaram"

Key = character 
value = num of occurences

S "anagram" hashmap
| key | value |
| --- | ----- |
| a   | 3     |
| n   | 1     |
| g   | 1     |
| r   | 1     |
| m   | 1      |

So in this implimentation we build out two hashmaps (dictionaries) one for each string, then compare they values behind each key. If they are ever dissimilar we can return false. 


### test cases

I would immediately test to verify inputs, if either of the inputs are not of type string we can stop the function

Type handling? - How should we handle numbers within the string? 