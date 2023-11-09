# Valid Parentheses
```cpp
#include <stack>

class Solution {
public:
    bool isValid(string s) {
        stack<char> st;
        for(int i = 0; i < s.size(); i++){
            if((s[i] == '[') || (s[i] == '{') || (s[i] == '(')){
                st.push(s[i]);
            }else {
                if(st.empty() ||
                (s[i] == ']' && st.top() != '[') ||
                (s[i] == ')' && st.top() != '(') ||
                (s[i] == '}' && st.top() != '{')) {
                    return false;
                }
                st.pop();
            }
        }  
        return st.empty();
    }
};
```

## Explanation

given string ```s```, check the parenthesis and closing braces are valid.
Valid:
``` '[{()}]''[]{}()' ```
Not valid:
``` '[()}''(())}]'```


1. Initialize an empty  stack ```st``` with type char
2. iterate through the given string ```s```
3. if the current character of string ```s``` is an opening brace, push that character to the stack
4. check if the string is empty, if it is, return false. if the current character of the string is closing brace of any kind, and the top of the stack is not a opening brace that matches a closing brace, then also return false.
5. if the closing brace is correctly matched with the opening brace, remove it from the stack with pop. (this is essentially canceling out the brackets)
6. finally return the function ```st.empty()``` the function check if the stack it is a member of is empty or not. if it is empty, that means all of the braces have cancelled each other out. if it is not empty, that means that there were braces that did not correctly match up.

## Time Complexity

The time complexity is **O(n)** Linear, where n is the length of the input string. We traverse the string only once and only preforms constant operations on it.

