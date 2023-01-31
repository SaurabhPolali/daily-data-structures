# <mark>TWO SUM</mark>

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        #Time Complexity is O(n)
        a = {}
        for i in range(len(nums)):
            num = target - nums[i]
            if num not in a:
                a[nums[i]] = i
            else:
                return [a[num], i]   
```
