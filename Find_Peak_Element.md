**<h3>Question</h3>**

A peak element is an element that is strictly greater than its neighbors.

Given a 0-indexed integer array nums, find a peak element, and return its index. If the array contains multiple peaks, return the index to any of the peaks.

You may imagine that nums[-1] = nums[n] = -∞. In other words, an element is always considered to be strictly greater than a neighbor that is outside the array.

You must write an algorithm that runs in O(log n) time.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/a79956c4-8d15-439a-96d3-8e464c6708c9)

**<h3>Constraints</h3>**

1. 1 <= nums.length <= 1000
2. -2<sup>31</sup> <= nums[i] <= 2<sup>31</sup>
3. nums[i] != nums[i+1] for all valid i.

**<h3>Approach</h3>**

1. We will use binary search in this question.
2. We will do the regular binary search but every tiem we check a middle element we will check if the element to its right and left are smaller than it or not. If yes then that mid is the answer.
3. Else we will move to that side of middle element which has the bigger element than mid.
4. We will take start as 1 and end as n-1 as we do not want to go out of memory for the array.
5. Then we will take care of the edge cases that is when we have size of array as 1 and we will check if the first or the last element of the array is the peak element or not.

**<h3>Code</h3>**

```
class Solution {
public:
    int findPeakElement(vector<int>& nums) {
        int n = nums.size();
        if (n == 1) return 0;
        if (nums[0] > nums[1]) return 0;
        else if (nums[n-1] > nums[n-2]) return n-1;
        int start = 1, end = n-2;
        while (start <= end) {
            int mid = (start + end)/2;
            if (nums[mid] > nums[mid-1] && nums[mid] > nums[mid+1]) return mid;
            else if (nums[mid] < nums[mid+1]) start = mid+1;
            else if (nums[mid] < nums[mid-1]) end = mid-1;
        }
        return 0;
    }
};
```
