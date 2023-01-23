# <mark>Valid Palindrome</mark>

```python
class Solution:
    def isPalindrome(self, s: str) -> bool:

        s = s.lower()
        start = 0
        end = len(s)-1
        while(start<=end):
            if s[start].isalnum() and s[end].isalnum():
                if s[start] == s[end]:
                    start += 1
                    end -= 1
                else:
                    return False
            elif not s[start].isalnum():
                start += 1
            elif not s[end].isalnum():
                end -= 1
```
