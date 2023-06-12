# 238. Product of Array Except Self



**Prompt:**
Given an integer array ```nums```, return an array answer such that ```answer[i]``` is equal to the product of all the elements of nums except ```nums[i]```.

The product of any prefix or suffix of nums is guaranteed to fit in a 32-bit integer.

You must write an algorithm that runs in ```O(n)``` time and without using the division operation.



  ```
Example 1:

Input: 
nums = [1,2,3,4]
Output: [24,12,8,6]

Example 2:
Input: 
nums = [-1,1,0,-3,3]
Output: [0,0,9,0,0]

   
```

**Approach:**
By having each index as the multiplication of all elements that came before it e.g. ```[1,2,3,4]``` would be ```[1,1,2,6]```.This would be ```prefix``` array and the postfix array ```[24,12,4,1]``` would be from the back.The mulitplication of each index's postfix and prefix is the product of array except self.

 ** *Everythig before it * everything after it= everything without it* **
 

**Ruby**

```ruby
# @param {Integer[]} nums
# @return {Integer[]}
def product_except_self(nums)
    prefix_array=[1] * nums.length
    for x in 1..nums.length-1 do
        prefix_array[x]=prefix_array [x-1] * nums[x-1]
        
    end
    s=1

    while x>-1 do
        prefix_array[x]=prefix_array[x]* s
        s=s * nums[x]
        x-=1
    end

 
        
       
  
    return prefix_array
end

```


