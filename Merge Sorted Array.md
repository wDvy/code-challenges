# Merge Sorted Array

2 Methods for Merge Sorted Array:

Non Decreasing Order: Each number or amount is not less than the previous one. Essentially it's increasing order, but allows duplicate values.

## Sort() Method:
```cpp
void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {        

	for (int j=0, i=m; j <n; j++){
         nums1[i] = nums2[j];
         i++;
    
    }
    sort(nums1.begin(),nums1.end());
 }

```

## Explanation:

We are given 2 sorted arrays in non-decreasing order, our goal is to merge these 2 arrays into one sorted array.

1. First we iterate for the length of the second string, and set the empty elements at the end of ```nums1``` to the elements in ```nums2```. This merges ```nums1``` and ```nums2``` into ```nums1``` but unsorted.
2. We can then use the Sort() function (from the standard template library) to sort the merged array.

This solution has a time complexity of O((M+N) log (M+N)) because of the sort function.
## Two Pointer Method:
```cpp
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        int i = m - 1;
        int j = n - 1
        int k = m + n - 1;

        while(j >= 0)
        {
            if (i >= 0 && nums[i] > nums2[j]){
                nums1[k--] = nums1[i--];
            }
            else {
                nums1[k--] = nums2[j--];
            }
        }
    }
```

## Explanation:

1. First we initialize 3 variables: ```i``` Which we set equal to m-1 is the final index of significant values in the ```nums1``` array. ```j``` which we set equal to n-1 is the real final index of the ```nums2``` array. finally, ```k``` which we set equal to m+n-1 is the real final index of the ```nums1``` array.
2. Next, we setup a while loop that continues until all numbers in ```nums2``` are merged into the ```nums1``` array. 
3. Within the loop we check if we if we're on the final element and which if the two elements we're pointing to are bigger. If ```i``` is bigger, it goes to index ```k``` in ```nums1```, then both elements decrement their indices.
4. If ```i``` is smaller, then the ```j``` element is assigned to the index ```k``` and both elements decrement.
5. This happens until we reach the last index of the smaller array, ```n```.

This solution has a time complexity of O ( m + n ) because we are iterating through both arrays.
