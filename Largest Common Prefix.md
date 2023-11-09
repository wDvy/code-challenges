# Largest Common Prefix
```python
class Solution:

    def longestCommonPrefix(self, strs: List[str]) -> str:
        ans=""
        strs = sorted(strs)
        first = strs[0]
        last = strs[-1]
        for i in range(min(len(first),len(last))):
            if(first[i] != last[i]):
                return ans
            ans += first[i]
        return ans
```

## Explained: 

Given list of strings ```strs``` find the largest common prefix of all strings.

1. Declare a empty string that will be the answer for the problem (ans). 
2. Sort the list of strings by alphabetical order, this will allow you to easily test if there is no common prefix between strings.
3. Declare ```first``` and ```last``` to be equal to the first and last strings of the list 
4. Find the minimum length between the first and last string and use that as a range to iterate over.
5. If the first string's first character is not equal to the last string's first character, return ```ans```
6. else, add the first character of the first string to ```ans``` 
7. finally, if all characters are shared, return ```ans```

## CPP Version

```cpp
  string longestCommonPrefix(vector<string>& strs) {
        string ans = "";
        sort(strs.begin(), strs.end());
        int n = strs.size();
        string first = strs[0];
        string last = strs[n-1];
        
        for(int i = 0; i < min(first.size(),last.size()); i++)
        {
            if( first[i] != last[i])
                return ans;
            ans += first[i];
        }
        
        return ans;
    }
```
