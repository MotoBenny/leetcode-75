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


### BigO Space


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


```

### BigO Time


### BigO Space


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