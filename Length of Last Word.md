Give a string S that contains words and spaces, find the length of the last word in the string.

```cpp
class Solution {
public:
    int lengthOfLastWord(string s) {
        reverse(s.begin(), s.end());
        string ans;
        
        for(int i = 0; i < s.size(); i++)
        {
            if(s[i] != ' '){
                ans += s[i];
                if(s[i+1] == ' '){
                    return ans.size();
                }
            }
        }
        return ans.size();

    }

};
```

While this technically works, it could be optimized by omitting the reverse() function and just iterating backwards instead of forwards. (whoops). Might re-implement that next time.

## Explanation

1. Reverse string s. (This is not necessary)
2. create string ans to store the last word string.
3. iterate through the reverse of string S. if s[i] is not equal to a space, add that char to the ans string. if the next char is a space, return the ans.size().
4. once you have iterated through the entire string return ans.size(). (This would be used if there were only one word in the string and there were no spaces preceding it.)
