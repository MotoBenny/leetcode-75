## Problem Domain Contains Duplicates
Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.

[Contains Duplicates](https://leetcode.com/problems/contains-duplicate/)

### Test Cases

```python
# Example 1:
Input: nums = [1,2,3,1]
Output: true

#Example 2:

Input: nums = [1,2,3,4]
Output: false

#Example 3:

Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true
```

### Algorithm Explanation

We begin by creating an empty python Set, which is an data structure they are unordered and unindexed. and conveniently don't accept any duplicate values. Based on a Hashtable so very efficient  (bigO of 1 insertion to set)

then within a for loop of int in our nums list, we check if the current int is within our set, If it is, we return true otherwise we add it to our set. and move on to the next int in our nums list

If we hit the end the end of our nums list without hitting our True conditional we can return False, since we know there are no duplicates in our test case.
### Code

```Python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        # using a python set
        numset = set() # instantiate a set
        for i in nums: # for each int in nums list
            if i in numset: # If I is in our set return true
                return True
            numset.add(i) # otherwise add the num to our set and loop to next num in list
        return False # like a base case, if we leave the for loop, we didnt find any duplicates, and can return false
```

### BigO Time

For this method our time complexity is O(n) we are adding each unique value to the set, and the set gives us O(1) insertion and O(n) search, Thus our bigO is O(n) as limited by the search time  of a hashtable(set).

### BigO Space


### Design choices and why


### test cases