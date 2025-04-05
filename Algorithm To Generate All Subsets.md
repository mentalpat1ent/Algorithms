Algorithm To Generate All Subsets

```python
def subsets(nums):
    output = []
    subset = []

    def dfs(index):
        if index >= len(nums):
            output.append(subset.copy())
            return

        subset.append(nums[index])
        dfs(index + 1)

        subset.pop()
        dfs(index + 1)

    dfs(0)
    return output
```
