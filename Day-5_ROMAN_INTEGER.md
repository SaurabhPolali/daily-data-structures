# <mark>ROMAN INTEGER</mark>

```python
class Solution:
    def romanToInt(self, s: str) -> int:
        #Time complexity = O(n)
        rom = {
            'I' :    1,
            'V' :    5,
            'X' :   10,
            'L' :   50,
            'C' :  100, 
            'D' :  500,
            'M' : 1000 
        }

        ans = 0
        for i in range(len(s)-1, -1, -1):
            val = rom[s[i]]
            if (4 * val) < ans:
                ans -= val
            else: 
                ans += val 
                
        return ans
```
