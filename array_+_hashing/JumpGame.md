# 55.JumpGame


**Prompt:**
You are given an integer array nums. You are initially positioned at the array's first index, and each element in the array represents your maximum jump length at that position.

Return ```true``` if you can reach the last index, or ```false``` otherwise.

 
  ```
Example 1:
Input: nums = [2,3,1,1,4]
Output: true
Explanation: Jump 1 step from index 0 to 1, then 3 steps to the last index.


Example 2:
Input: nums = [3,2,1,0,4]
Output: false
Explanation: You will always arrive at index 3 no matter what. Its maximum jump length is 0, which makes it impossible to reach the last index.
```

**Approach:**
Rather than check from front -> back check back->front.Assume the second last index is your start position and last index is your goal position, if from the start you can get to goal, then the goal position should now be the current start position while the start position will get decremented regardless at each iteration and you just keep checking if from start you can get to goal until start gets to -1.

Basically, divide the problem of getting to the last index into a sub problem by changing the positions accordingly.

**Golang**

```go
func canJump(nums []int) bool {
    start:=len(nums)-2
    end:=left+1

    for start>-1 {
        if (start + nums[start] >= end){
            end=start

        }

        start-- //regardless
    }
    return end==0


    
}

```


