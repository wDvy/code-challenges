# Remove Duplicates
```cpp
    int removeDuplicates(vector<int>& nums) {
        int j = 1;
        for(int i = 1; i < nums.size(); i++){
            if( nums[i] != nums[i-1]){
                nums[j] = nums[i];
                j++;
            }
        }
        return j;
    }
```

## Explanation 

given array of  numbers ```nums```, remove the duplicates in the array and return the amount of unique numbers.

1. Initialize a variable j to hold the answer and set it 1.  (nums length is guaranteed to be greater than or equal to 1)
2. iterate over the array and check if the current (starting at the second element) member of the array is not equal the previous one. if it is, set the j element to equal the current element and iterate j.
3. finally return j. Nums should also now have all duplicates removed. 
