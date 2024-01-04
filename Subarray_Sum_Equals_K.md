**<h3>Question</h3>**

Given an array of integers nums and an integer k, return the total number of subarrays whose sum equals to k.

A subarray is a contiguous non-empty sequence of elements within an array.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/fd65f03e-0d9c-4245-b88b-3a189d68f604)

**<h3>Constraints</h3>**

1. 1 <= nums.length <= 2*10<sup>4</sup>
2. -10<sup>7</sup> <= k <= 10<sup>7</sup>
3. -1000 <= nums[i] <= 1000

**<h3>Approach</h3>**

1. In this question we will use the prefix sum approach.
2. For this approach we will keep an unordered map and 2 variables sum (for keeping the running sum of the array) and ans (total number of subarrays). We will make mp[0] as 1 because if sum is equal to k then we have already got one of the subarrays whose sum equals k.
3. So we will traverse the array using the for loop and keep on adding nums[i] to sum and then we will update ans. To update ans we will check if there is any subarray that has appeared earlier in the nums array while traversing it whose prefix sum and k sum up to the prefix sum of the current time.
4. And then we will add the number of those subarrays to the value of ans and add the value of mp[sum]++.
5. In the end we will have the total number of subarrays whose sum equals k.

**<h3>Code</h3>**

```
class Solution {
public:
    int subarraySum(vector<int>& nums, int k) {
        unordered_map<int,int>mp;
        mp[0]++;
        int sum = 0, ans = 0, n = nums.size();
        for (int i = 0; i < n; i++) {
            sum += nums[i];
            ans += mp[sum - k];
            mp[sum]++;
        }
        return ans;
    }
};
```
