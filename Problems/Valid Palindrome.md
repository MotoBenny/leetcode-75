## Problem Domain Valid Palindrome
-A phrase is a **palindrome** if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string `s`, return `true` _if it is a **palindrome**, or_ `false` _otherwise_.

[Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)

### Algorithm Explanation

initially i create a clean variable which will hold a string stripped of all characters that are not alphanumeric (A-Z 0-9). we can use some built in python methods for this. like a .join and .isalnum within a list comprehension which allows us to iterate through the input string.

then we can use string slicing to revers the string as a new veriable. 

then we return the result of the equality opperator with a .lower method to make the result case insensitive. 

### Code

```Python
class Solution:
    def isPalindrome(self, s: str) -> bool:
        # add character from input string to clean variable If character is a letter, or a number 
        clean = ''.join([i for i in s if i.isalnum()])
        

        # reverse the clean string using indexing/slicing
        reverse = clean[::-1]

        # returns boolean based on == opperator.
        return clean.lower() == reverse.lower()
    

```

### BigO Time

This result is O(n) where n is the length of the input string, since we have to iterate through all the characters to perform the opperation

### BigO Space
The space for this is O(n) since our memory space does not expand past the two strings we create. if we were using multiple pointers we mght see additional space useage. 

### Design choices and why
This method is a little brute forcy, not using much memory, but allows for a very fast resolution.
Alternatively we could use a method of placing a pointer at either end of the problem.

In a case where we cannot use the built in pythonic method for finding alphanumeric characters we could build out a helper function like so to handle that for us. 

```python 
# Could write own alpha-numeric function 
def alphanum(self, c): 
	return (ord('A') <= ord(c) <= ord('Z') or 
			ord('a') <= ord(c) <= ord('z') or 
			ord('0') <= ord(c) <= ord('9'))

```

### test cases

In this application we know our case is alphanumeric and our algorithm ignores characters that dont adheir to this structure. 