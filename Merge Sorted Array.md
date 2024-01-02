# Merge Sorted Array
Given 2 sorted arrays ```nums1``` and ```nums2``` merge them and sort them in non decreasing order.

```cpp
void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {
	for(int i = 0; i<n; i++){
		nums1[m+i] = nums2[i];
	}
	sort(nums1.begin(), nums1.end());
}
```

## Explanation
1. Use a for loop to add merge both arrays together. You do this by iterating a variable up to the size of the second array, and assigning the value of the index after the last element in the array to the first element in the second array.
2. after merging the arrays, use the in-built sort function on nums1 in order to create an array in non decreasing order. 



