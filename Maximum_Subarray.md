**<h3>Question</h3>**

Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

A subarray is a contiguous part of an array.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/78a78d78-45cf-4b17-83d9-1c8d42181b02)

**<h3>Constraints</h3>**

1. 1 <= n <= 10<sup>5</sup> 
1. -10<sup>4</sup> <= nums[i] <= 10<sup>4</sup>

**<h3>Approach</h3>**

1. we initialise 2 variables maxi with the value INT_MIN and sum with value 0.
2. Now we traverse the array and add the value of nums[i] to sum.
3. Then we check if sum is greater than maxi or not and if yes then we update maxi to sum.
4. then we check if sum is getting negative or not if yes then we make sum 0.
5. This is done so that whenever we add the next element its entire value is added and not the one which is reduced by negative sum.
6. At the end of the loop we have maximum sum of subarray.

**<h3>Code</h3>**

```
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int maxi = INT_MIN;
        int sum = 0;
        for (int i = 0; i < nums.size(); i++) {
            sum+= nums[i];
            if (sum > maxi) maxi = sum;
            if (sum < 0) sum = 0;
        }
        return maxi;
    }
};
```
