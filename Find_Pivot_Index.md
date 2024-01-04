**<h3>Question</h3>**

Given an array of integers nums, calculate the pivot index of this array.

The pivot index is the index where the sum of all the numbers strictly to the left of the index is equal to the sum of all the numbers strictly to the index's right.

If the index is on the left edge of the array, then the left sum is 0 because there are no elements to the left. This also applies to the right edge of the array.

Return the leftmost pivot index. If no such index exists, return -1.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/d6d69e41-5b03-43eb-881d-77a16d62b2a9)

**<h3>Constraints</h3>**

1. 1 <= nums.length <= 10<sup>4</sup>
2. -1000 <= nums[i] <= 1000

**<h3>Approach</h3>**

1. we will keep 2 variables rightsum and leftsum which will be used to keep the sum of the left and the right side of each element.
2. First we will traverse the array and put the entire sum of the array int he rightsum.
3. And then we will run a for loop again and this time we will keep updating the rightsum by removing the value of nums[i] from the rightsum and update the leftsum after checking whether sughtsum and leftsum are equal or not.
4. If they are equal at any i we will return that i else at the end of the loop we will be ensured that there is no i such that leftsum and rightsum are equal so we will return -1.

**<h3>Code</h3>**

```
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
        int rightSum = 0, leftSum = 0;
        for (int i = 1; i < nums.size(); ++i) rightSum += nums[i];
        for (int i = 0; i < nums.size(); ++i) {
            if (rightSum == leftSum) return i;
            leftSum += nums[i];
            if (i + 1 < nums.size()) rightSum -= nums[i+1];
        }
        return -1;
    }
};
```
