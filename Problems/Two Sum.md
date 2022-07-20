## Problem Domain Two Sum
-

[Two Sum]()

### Test cases

```python

```

### Algorithm Explanation



### Code

```Python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        prevMap = {} # val -> index
        
        for i, n in enumerate(nums): # for nums[0], nums [1]
            diff = target - n
            if diff in prevMap:
                return [prevMap[diff], i]
            prevMap[n] = i

```

### BigO Time


### BigO Space


### Design choices and why


### test cases