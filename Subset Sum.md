Algorithm to check if we can find a subset in a given list that has it's sum equal to a target sum.
Outside the function we will initialize the dp matrix which will look like this:
```python
 dp = [[-1 for _ in range(target + 1)] for i in range(n)]
```

```python
        def solve(index, target):

            nonlocal dp

            if target == 0:
                return True

            if index == 0:
                return nums[0] == target

            if dp[index][target] != -1:
                return dp[index][target]

            notTaken = solve(index - 1, target)

            taken = False

            if nums[index] <= target:
                taken = solve(index - 1, target - nums[index])

            dp[index][target] = notTaken or taken

            return dp[index][target]
```
