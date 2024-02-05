# Remove Duplicates II

Given an array of ints, remove any instance of the int where it appears more than 2 times. return the length of the array that would comprise the orignal array - any double duplicates.

```cpp

int removeduplicates(vector<int>& nums){
  int i =0;
  for (int element : nums)
    {
    if(i == 0 || i == 1 || nums[i-2] != element)
      {
        nums[i] = element;
        i++;
      }
    }
    return i;
}

```


## Explanation:
1. Initialize i = 0, this is the index for the modified array to be returned.
2. iterate through the length of the array, checking
3. If we are on the first element, the second element, or if the index two steps back equals the current element.
4. if so, set the array's ith element to the current element and increase i, if not skip that element and continue to the next.
5. return i.
