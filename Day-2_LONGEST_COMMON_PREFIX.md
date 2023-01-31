# <mark>LONGEST COMMON PREFIX</mark>

```python
class Solution:
    def longestCommonPrefix1(self, strs) -> str:
        #TIME COMPLEXITY = O(N*M) \
        #zip function invocation itself is O(N) as the interpreter \
        #must convert parameters into an array. Every subsequent next \
        #call  on the iterator also runs O(N) exhausting the zip object \
        #Therefore it is O(N*M) assuming M is the average legth of the iterables.        
        res = ""
        for i in zip(*strs):
            if len(set(i)) ==1:
                res += i[0]
            else:
                break
        return res

    def longestCommonPrefix2(self, strs) -> str:
        #TIME COMPLEXITY = O(2n*m+S)
        #find method has a time complexity of O(n*m).
        #The inner loop iterates through the characters of prefix and \
        #since the prefix can have atmost n characters, the inner loop has \
        #a time complexity of O(n)."find" function has a worst case time \
        #complexity of O(n*m). and since there are S. Discuss later. \        
        if len(strs) == 0:
            return ""
        prefix = strs[0]
        for i in range(1, len(strs)):
            while strs[i].find(prefix) != 0:
                prefix = prefix[:len(prefix) - 1]

        return prefix


    def longestCommonPrefix3(self, strs)->str:
        #Time Complexity: O(MAX * n * log n ) where n is the number of strings 
        #in the array and MAX is maximum number of characters in any string. 
        #Comparison of two strings would take at most O(MAX) 
        #time and for sorting n strings.
        if len(strs)==0:
            return ""
        elif len(strs)==1:
            return strs[0]
        strs.sort()
        start = strs[0]
        end = strs[len(strs) - 1]

        prefix = ""
        for i in range(len(start)):
            if start[i] == end[i]:
                prefix +=  start[i]
            else:
                break                        
        return prefix

Sol = Solution()
print("common prefix:", Sol.longestCommonPrefix1(["oolongcha", "oojicha", "ooa"]))
print("common prefix:", Sol.longestCommonPrefix2(['deep','deepa', 'devil']))
print("common prefix:", Sol.longestCommonPrefix3(["aaaaaaaaaa", "aab", "aa"]))   
```
