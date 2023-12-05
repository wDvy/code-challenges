# Find the Index of the First Occurrence in a String

```cpp
class Solution {
public:
    int strStr(string haystack, string needle) {
    
        int needleLength = needle.size();
        string str;
       
        for(int i = 0; i < haystack.size(); i++)
            if(needle[0] == haystack[i])
            {
                str = haystack.substr(i, needleLength);
                if(str == needle){
                    return i;
                }
            }
            
        return -1;
    }
};
```

## Explanation

The objective of this problem is to find, within another string, the first occurrence of the substring and provide it's index.

1. First Initialize variables ```needleLength``` with the size of the substring we're looking for and  ```str``` as an empty string.
2. Next, iterate through the haystack checking if the current letter of the string matches the first letter of the substring.
3. If it does, set the ```str``` variable equal to a substring that is the same length as the needle, then check if they're equal. [[substr function cpp]].
4. if they are equal, return the index the substring was found.
5. Continue this iteration until either the substring is found, or the for loop terminates and returns -1, signifying failure.