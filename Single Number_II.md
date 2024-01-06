**<h3>Question</h3>**

Given an integer array nums where every element appears three times except for one, which appears exactly once. Find the single element and return it.

You must implement a solution with a linear runtime complexity and use only constant extra space

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/176f0e3b-7a35-4e0c-9f06-513a11d36788)

**<h3>Constraints</h3>**

1. 1 <= nums.length <= 3*10<sup>4</sup>
2. -2<sup>31</sup> <= nums[i] <= 2<sup>31</sup>
3. Each element in nums appears exactly three times except for one element which appears once.

**<h3>Approach</h3>**

1. in this question we are going to use bitmasking to solve this question.
2. We will make an array named arr where we will store the number that is appearing in nums as we traverse it in the form of bits in the arr array.
3. With the bits we will also check if the number we just traversed is negative or not if yes then we increase arr[32].
4. once we have traversed the array we will check every bit that is its remainder when divided by 3 1 or not.
5. if the remainder is 1 then that bit is of the number that has appeared once and if it is not then it is of one of the numbers which has appeared thrice.
6. So use the bit to decimal formula to get the answer.

**<h3>Code</h3>**

```
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        long ans = 0;
        vector<int> arr(33,0);
        int n = nums.size();
        for(int i = 0; i < n; i++) {
            long current = nums[i];
            current = abs(current);
            long start = 0;
            while (current) {
                if (current&1 == 1) arr[start]++;
                start++;
                current = current >> 1;
            }
            if (nums[i] < 0) arr[32]++;
        }
        long start = 1;
        for (int i = 0; i < 32; i++) {
            if (arr[i] % 3 == 1) {
                ans += start;
            }
            start *= 2;
        }
        if (arr[32] % 3 == 1) ans = -1*ans;
        return ans;
    }
};
```
