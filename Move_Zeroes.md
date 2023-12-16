**<h3>Question</h3>**

"Given an array A[] of size N containing non-negative integers. You have to move all 0's to the end of array while maintaining the relative order of the non-zero elements.

Note:
You must do this in-place without making a copy of the array.
Minimize the total number of operations."

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/01aad1d0-9a38-412b-a306-27fa95c3b9c3)


**<h3>Constraints</h3>**

1. 1 <= N <= 10<sup>5</sup> 
1. 1 <= A[i] <= 10<sup>5</sup>

**<h3>Approach</h3>**

1. We just want to move all the zeroes to the end so instead of moving the zeroes to the end we start moving the non zero elements to the front without changing the order
2. In this way all the zeroes shift to the end without changing the order of the non zero elements

**<h3>Code</h3>**

```
class Solution {
public:
	vector<int> moveZeros(vector<int>& nums) {
		int count = 0;
        for (int i = 0; i < nums.size(); i++) {
            if (nums[i] != 0) {
                swap(nums[i],nums[count]);
                count++;
            }
        }
        return nums;
	}
};
```
