**<h3>Question</h3>**

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/0442d8fb-5922-4f78-a76c-f1f352717f0f)

**<h3>Constraints</h3>**

1. 2 <= n <= 10<sup>4</sup>
2. -10<sup>9</sup> <= nums[i] <= 10<sup>9</sup>
1. -10<sup>9</sup> <= target <= 10<sup>9</sup>


**<h3>Approach</h3>**

1. We make an unordered map
2. As we travrese the array we take one element at a time and then we check if target-nums[i] is there in the map or not by using the find function
3. if it is not there then we just push the index of the current element in the map.
4. and if it is there we just return the index of nums[i] and the index of target-nums[i] using the map.

**<h3>Code</h3>**

```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
       unordered_map<int,int>mp;
       for (int i = 0; i < nums.size(); i++) {
           if (mp.find(target-nums[i]) == mp.end()) {
               mp[nums[i]] = i;
           }
           else return {mp[target-nums[i]],i};
       }
       return {};
    }
};
```
