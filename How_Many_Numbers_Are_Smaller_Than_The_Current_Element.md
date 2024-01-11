**<h3>Question</h3>**

Given the array nums, for each nums[i] find out how many numbers in the array are smaller than it. That is, for each nums[i] you have to count the number of valid j's such that j != i and nums[j] < nums[i].

Return the answer in an array.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/2798f53c-4577-4e80-bac0-bf8523e9343f)

**<h3>Constraints</h3>**

1. 0 <= nums[i] <= 100
2. 2 <= nums.length <= 500

**<h3>Approach</h3>**

1. As we can see from the constraints that the value of nums[i] is always between 0 and 100 so we will make a count vector of size 101 where we will increase only the value that are present in the nums vector.
2. Then we will update the count vector such that the indexes corresponding to the value of nums[i] contains the number of nums elements that are smaller than nums[i].
3. Then we will traverse the nums array changing it to the number of elements smaller than the current element using the count vector.

**<h3>Code</h3>**

```
class Solution {
public:
    vector<int> smallerNumbersThanCurrent(vector<int>& nums) {
        vector<int>count(101,0);
        for (auto num : nums) count[num]++;
        for (int i = 1; i < 101; i++) {
            count[i] += count[i-1];
        }  
        for (int i = 0; i < nums.size(); i++) {
            if (nums[i] != 0)
            nums[i] = count[nums[i]-1];
        }
        return nums;
    }
};
```
