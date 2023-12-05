# Search Insert Position - Utilizing Binary Search

```cpp 
  
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        int low = 0;
        int high = nums.size() - 1;

        while( low <= high ) {
            int mid = low + (high - low) / 2;

            if (nums[mid] == target) {
                return mid;
            } else if (nums[mid] < target) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }

        }
        return low;
    }
};
```

## Explanation:

Given a sorted array of integers, find out where the target integer is if it is in the array or where it should be if it were.

1. First, Initialize variables ```low``` to the index of the beginning of the array (0) and ```high``` as the end of the array (nums.size() - 1).
2.  Start iterating until a position is found
3. in that iteration , set the variable ```mid``` to the string midpoint. if the target is equal to the midpoint, return it. 
4. if the target is less than the midpoint, set the low variable (the starting index of the area we're searching) to be the mid point of the previous search area.
5. if the target is more than the midpoint, set the high variables (the ending index of the area we're searching) to the midpoint of the previous search area.
6. continue until the midpoint is equal to the target.

Time Complexity O(log N)
## More: Binary Search
Why does this solution work, and why is it more efficient than normally iterating through a list?

This solution utilizes Binary Search, which is an algorithm that is significantly more efficient than linear search but has some basic requirements. 
- The List has to be sorted
- The list has to have  access to values from indices at constant time.

The process of binary search is as follows:

1. Get the starting point and the ending point of an array of numbers.
2. get the midpoint of that array
3. check if the target number is equal, less or more than the midpoint.
4. if its more, move the lower bounds of the search area up to the midpoint and go again. 
5. do the opposite if it's less.
6. continue this until the target is equal to the midpoint.
7. return midpoint.
