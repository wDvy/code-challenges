# Remove Element

```cpp
    int removeElement(vector<int>& nums, int val) {
        int k = 0;
        for(int i = 0; i < nums.size(); i++){
            if(nums[i] != val){
                nums[k] = nums[i];
                k++;
            }
        }
    return k;
    }
```

## Explanation

Given Array ```nums``` and int ```val```, remove all instances of ```val``` from ```nums```.

1. Initialize integer k, that will be the answer integer. 
2. Iterate over the array.
3. check if the current number in the array is not equal to ```val```
4. if it is not, set ```nums[k]``` to ```nums[i]``` and iterate ```k```. As we iterate through the array, k will represent the numbers that are not ```val```, so items on the right that are not ```val``` will be moved to the left and the element is deleted. 
5. finally return the amount of numbers that are not ```val``` as ```k```.

## Time Complexity

Time complexity is O(n), with n being the amount of numbers in the given array. we iterate through the array then apply constant-time operations on them.
