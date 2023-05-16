# 198 - House Robber


**Prompt:**
You are a professional robber planning to rob houses along a street. Each house has a certain amount of money stashed, the only constraint stopping you from robbing each of them is that adjacent houses have security systems connected and ``` it will automatically contact the police if two adjacent houses were broken into on the same night ```

Given an integer array nums representing the amount of money of each house, return the maximum amount of money you can rob tonight without alerting the police.

 


  ```
  Example 1:
  Input: nums = [1,2,3,1]
Output: 4
Explanation: Rob house 1 (money = 1) and then rob house 3 (money = 3).
Total amount you can rob = 1 + 3 = 4.
  
 
  Example 2:
  Input: nums = [2,7,9,3,1]
Output: 12
Explanation: Rob house 1 (money = 2), rob house 3 (money = 9) and rob house 5 (money = 1).
Total amount you can rob = 2 + 9 + 1 = 12.
```

**Approach:**

Starting from the back, keep track of the total max sum at each position all the way to index 0.Then return max of arr[0] and arr[1] since that would show the final two sums.

From Example 1 :
nums =[1,2,3,1] + [-1]

sum=[4,3,3,1,-1]


**Python**

```python
    def rob(self, nums):
        """
        :type nums: List[int]
        :rtype: int
        """
        nums.append(-1)
        third_last=len(nums)-4

        for x in range(third_last,-1,-1):
            nums[x]+= max(nums[x+2],nums[x+3])
        return max(nums[0],nums[1])

```
