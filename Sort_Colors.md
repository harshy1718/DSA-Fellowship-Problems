**<h3>Question</h3>**

Given an array nums with n objects colored red, white, or blue, sort them in-place so that objects of the same color are adjacent, with the colors in the order red, white, and blue.

We will use the integers 0, 1, and 2 to represent the color red, white, and blue, respectively.

You must solve this problem without using the library's sort function.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/10deab77-7d28-40cb-a017-dc1a5fd41b9f)

**<h3>Constraints</h3>**

1. 1 <= n <= 300 
1. nums[i] is either 0, 1 or 2.

**<h3>Approach</h3>**

1. Our approach is simple, we will just sort 0 to the starting and 2s to the end. in this way all the 1s will be sorted in the middle on their own.
2. We will initialise 2 variables start = 0 and end = nums.size()-1.
3. Then we will traverse the array and if nums[i] is 0 then we swap nums[i] and nums[start] and increment start.
4. Else if nums[i] is 2 then we swap nums[i] and nums[end] and decrease end and i as well.
5. We decrease i as well because we want to check that the element we swapped is 0 or 2 or not.
6. Alse the for loop has the condition i < end because the elements after end are already sorted.
   
**<h3>Code</h3>**

```
class Solution {
public:
	vector<int> sortColors(vector<int>& nums) {
		// Your code goes here
        int start = 0;
        int end = nums.size() - 1;
        for (int i = 0; i <= end;i++) {
            if (nums[i] == 0) {
                swap(nums[i],nums[start]);
                start++;
            }
            else if (nums[i] == 2) {
                swap(nums[i],nums[end]);
                i--;
                end--;
            }
        }
        return nums;
	}
};
```
