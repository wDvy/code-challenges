Given a string of characters spaces and punctuation, determine if the alphanumeric characters within the string are a palindrome. (reads the same from front to back).

Example String:
```
s = "car is a, is car" // valid, true
s = "car is a, car" // invalid, false
```

```cpp
    bool isPalindrome(string s) {
        int start = 0;
        int end=s.size();
        while(start <= end){
            if(!isalnum(s[start])){
                start++;
                continue;
            }

            if(!isalnum(s[end])){
                end--;
                continue;
            }
            if(tolower(s[start])!=tolower(s[end])){
                return false;
            }
            else{
                start++;
                end--;
            }
        }
        return true;
    }
```

## Explanation - Two pointer method
This problem first appeared as if you would need to clean the data before checking if the string was a palindrome. We can increase efficiency by not iterating through the string and cleaning data by using the two pointer method and utilizing the cpp std function isalphnum().

1. First, initialize the variables start and end, start to 0 and end to the size of the string.
2. Next, start a while loop that will continue until you reach the middle of the string (by pointing from both ends).
3. Check if the index from the start and end variables are alphanumeric. If they aren't iterate the pointer that was not alphanumeric and skip the rest of the while loop logic.
4. Check the two pointers value (after being converted to lower case) are equal to each other. If they are, then iterate both towards the middle. If they are not equal, return false, as the string is not a palindrome.
5. Finally after the whole string is iterated through, and the indices meet up in the middle, return true.

## Time Complexity

This Algorithm operates in O(N) Linear time, as the time will increase linearly to the amount of elements.





