**<h3>Question</h3>**

Given an array nums. We define a running sum of an array as runningSum[i] = sum(nums[0]…nums[i]).

Return the running sum of nums.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/032258e0-84cd-4dcf-bc49-5afdd6144c84)

**<h3>Constraints</h3>**

1. 1 <= nums.length <= 1000
1. -10<sup>6</sup> <= nums[i] <= 10<sup>6</sup>

**<h3>Approach</h3>**

1. We will just keep updating the recent element of the array by the sum of the recent element and the previous element by running a for loop on the array starting from index 1.

**<h3>Code</h3>**

```
class Solution {
public:
    vector<int> runningSum(vector<int>& nums) {
        int n = nums.size();
        for (int i = 1; i < n; i++) {
            nums[i] = nums[i] + nums[i-1];
        }
        return nums;
    }
};
```
