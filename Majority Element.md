The majority element is the element that appears more than `⌊n / 2⌋` times. return the majority element, it can be assumed that there is always one.

## Sort method
```cpp
class Solution {
	public:
		int majorityElement(vector<int>& nums) {
			sort(nums.begin(), nums.end());
			int n = nums.size();
			return nums[n/2];
		}
};
```

## Explanation

1. This method is based on the fact that if a majority element is present within the array then, then when it is sorted, that element will always be in the middle. 
2. to start, we sort the array. we use the built-in sorting function for simplicity.
3. then we assign a variable n to be the size of the array nums.
4. finally we return the middle index of that array, by dividing the size of the array by two. 

## Time Complexity

Because of the [[Introsort]] based sort function, this method operates at a time complexity of O(NlogN) in all cases.

#algorithms 
