**<h3>Question</h3>**

Given an integer array nums, return all the triplets [nums[i], nums[j], nums[k]] such that i != j, i != k, and j != k, and nums[i] + nums[j] + nums[k] == 0.

Notice that the solution set must not contain duplicate triplets.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/5120d5d4-edf9-4eca-87e9-f35915d8a344)

**<h3>Constraints</h3>**

1. 3 <= nums.length <= 3000
1. -10<sup>5</sup> <= nums[i] <= 10<sup>5</sup>

**<h3>Approach</h3>**

1. We know that this question can be done by using 3 loops and that will be the brute force approach but we want to reduce the time complexity.
2. So we will try to use 2 pointer approach to solve this question.
3. We will first sort the given array and then run a for loop with the condition i < n-2 because the 2 pointer approach will require atleast 2 variables.
4. Next we will initialise 2 pointers s and e which will mark the start and end of the 2 pointer apporoach and then we will chek that the value at i,s,e sum up to 0 or not.
5. If it sums up to 0 we will do s++,e-- and we will make sure that we skip those values which are repeating by using 2 while loops.
6. If the sum of i,s,e is less than 0 we will just increment s else we decrease e.
7. After that while loop has ended we will make sure the same i is skipped so that we dont have repeating triplets.

**<h3>Code</h3>**

```
class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        int n = nums.size();
        vector<vector<int>> v;
        sort(nums.begin(),nums.end());
        for (int i = 0; i < n-2; i++) {
            int s = i+1;
            int e = n-1;
            while (s < e) {
                if (nums[i] + nums[s] + nums[e] == 0) {
                    v.push_back({nums[i],nums[s],nums[e]});
                    while (s < e && nums[s] == nums[s+1]) s++;
                    while (s < e && nums[e] == nums[e-1]) e--;
                    s++;
                    e--;
                }
                else if (nums[i] + nums[s] + nums[e] < 0) s++;
                else e--;

            }
            while (i +1 < n && nums[i] == nums[i+1]) i++;
        }
        return v;
    }
};
```
