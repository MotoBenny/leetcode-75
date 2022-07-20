## Problem Domain Best time to buy and sell stock
-

[Best time to buy and sell stock]()

### Test cases

```python

```

### Algorithm Explanation

Two Pointers
Left pointer on day 1
right pointer on day 2
then compair pointer one and pointer 2
where left is buy day
and right is sell day




### Code

```Python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        # two pointer
        # left pointer index 0 right pointer the following index, since we cannot buy and sell same day
        l, r = 0,1
        # max profit, set to 0
        maxP = 0
        
        # while r less than length of prices list.
        while r < len(prices):
            # profitable? 
            # if prices at L is less than prices at R
            if prices[l] < prices[r]:
                # temp profit = prices at R minus prices at L
                profit = prices[r] - prices[l]
                # maxP = whichever is more, current maxP or temp profit variable
                maxP = max(maxP, profit)
            else:
                # new Left pointer = to right hand pointer
                l = r
            # right pointer incriment by one
            r += 1
        # return max profit
        return maxP


```

### BigO Time


### BigO Space


### Design choices and why


### test cases