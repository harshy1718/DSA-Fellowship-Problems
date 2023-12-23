**<h3>Question</h3>**

The product difference between two pairs (a, b) and (c, d) is defined as (a * b) - (c * d).

For example, the product difference between (5, 6) and (2, 7) is (5 * 6) - (2 * 7) = 16.
Given an integer array nums, choose four distinct indices w, x, y, and z such that the product difference between pairs (nums[w], nums[x]) and (nums[y], nums[z]) is maximized.

Return the maximum such product difference.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/079f709e-803d-40a5-a21e-7b672950a44a)

**<h3>Constraints</h3>**

1.  0 <= nums.length <= 10<sup>4</sup> 
1.  1 <= nums[i] <= 10<sup>4</sup>

**<h3>Approach</h3>**

1. The maximum difference will be when we have the difference of the product of 2 max elements and 2 min elements of the array.
2. The approach is that we will find 2 of the maximum and 2 of the minimum elements of the array.
3. And in the end return the difference.

**<h3>Code</h3>**

```
class Solution {
    public:
   int maxProductDifference(vector<int>& nums) {
     // Your code goes here
     int maxi1 = INT_MIN;
     int maxi2 = nums[0];
     int mini1 = INT_MAX;
     int mini2 = nums[0];
     for (int i = 1; i < nums.size(); i++) {
       if (nums[i] > maxi2) {
         maxi1 = maxi2;
         maxi2 = nums[i];
       }
       else if (nums[i] > maxi1) {
         maxi1 = nums[i];
       }
       if (nums[i] < mini2) {
         mini1 = mini2;
         mini2 = nums[i];
       }
       else if (nums[i] < mini1) {
         mini1 = nums[i];
       }
     }
     return ((maxi1*maxi2) - (mini1*mini2));
   }
};
```
