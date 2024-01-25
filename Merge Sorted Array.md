# Merge Sorted Array
Given 2 sorted arrays ```nums1``` and ```nums2``` merge them and sort them in non-decreasing order.

```cpp
void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
	for(int i = 0; i<n; i++){
		nums1[m+i] = nums2[i];
	}
	sort(nums1.begin(), nums1.end());
}
```

## Explanation
1. Use a for loop to add and merge both arrays. You do this by iterating a variable up to the size of the second array and assigning the value of the index after the last element in the array to the first element in the second array.
2. after merging the arrays, use the in-built sort function on nums1 to create an array in non-decreasing order. 


Cringe Solution that uses a sort method within a function that is supposed to be for a sort method... tsk tsk

## Two Pointer Solution

```cpp
    void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
        int i = m - 1;
        int j = n - 1;
        int k = m + n - 1;

        while(j >= 0){
            if ( i >= 0 && nums1[i] > nums2[j] ){
                nums1[k--] = nums1[i--];
            } else {
                nums1[k--] = nums2[j--];
            }
        }
    }
```


## Explanation
1. Initialize 3 variables, i - the last item in the first array, j - the last item in the second array, and k the last position in the combined array.
2. Create a while loop that checks while the second array has not been completely iterated through, check if the first array has not been iterated through and if the current iteration in array 1 is greater than array 2, if so set the last position in the combined array, if not set the other value.
3. then decrement the combined array index and the index of the array that had the larger input.
4. Continue until the combined array is sorted.

## Time Complexity
- O(n + m)
