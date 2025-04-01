The Boyer-Moore algorithm helps us find the majority element that occurs more than N/2 among the given elements. It takes 2 traversals over the given elements or just one if we know for sure that the given list has a majority element.
It has a time complexity of O(n) and O(1) space complexity.

```python
    def majorityElement(self, nums: List[int]) -> int:
        
        n = len(nums)
        candidate = -1
        votes = 0

        for i in range(n):
            if votes == 0:
                candidate = nums[i]
                votes += 1
            else:
                if candidate == nums[i]:
                    votes += 1
                else:
                    votes -= 1
        
        count = 0

        for i in range(n):
            if nums[i] == candidate:
                count += 1

        if count > n // 2:
            return candidate
        
        return -1     
```

```js
function findMajority(nums)
  {
    var count = 0, candidate = -1;

    for (var index = 0; index < nums.length; index++) {
      if (count == 0) {
        candidate = nums[index];
        count = 1;
      }
      else {
        if (nums[index] == candidate)
          count++;
        else
          count--;
      }
    }

    count = 0;
    for (var index = 0; index < nums.length; index++) {
      if (nums[index] == candidate)
        count++;
    }
    if (count > (nums.length / 2))
      return candidate;
    return -1;

  }
```
