# Climbing Staircase


**Prompt:**

You are climbing a staircase. It takes `n` steps to reach the top.

Each time you can either climb `1` or `2` steps. In how many distinct ways can you climb to the top?

  ```
  Example 1:
  
  Input: n = 2
  Output: 2
  Explanation: There are two ways to climb to the top.
  1. 1 step + 1 step
  2. 2 steps

  Example 2:

  Input: n = 3
  Output: 3
  Explanation: There are three ways to climb to the top.
  1. 1 step + 1 step + 1 step
  2. 1 step + 2 steps
  3. 2 steps + 1 step
   
```

**Approach:**

Wrote down the combos by hand,realized it was `fibonacci`.

**Java**

```java

  public int climbStairs(int n) {
        int [] dp= new int[n];
        if (n==1){
            return 1;
        }
        dp[0]=1;
        dp[1]=2;

        for (int i=2;i<n;i++){
            dp[i]=dp[i-1] + dp[i-2];
        }
        return dp[n-1];
    }

```

**Ruby**
```ruby
# @param {Integer} n
# @return {Integer}
def climb_stairs(n)
  dp=[]
  dp.append(1)
  dp.append(2)
  x=2

  while x<n 
    dp.append(dp[x-1]+dp[x-2])
    x+=1

  end
  return dp[n-1]

    
end


```
