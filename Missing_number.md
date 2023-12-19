**<h3>Question</h3>**

Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/3cad4f7b-b7ed-4750-8dda-3f972b6756df)

**<h3>Constraints</h3>**

1. 1 <= n <= 10<sup>4</sup> 
1. 0 <= nums[i] <= n
2. All the numbers of **nums** are **unique**.

**<h3>Approach</h3>**

1. We initialise a variable **a** with 0.
2. Then we traverse the array nums and we keep on taking XOR of nums[i] with a and i+1.
3. We know that XOR of 2 same numbers is 0.
4. So at the end of the loop a will contain only that number that has appeared once and those which appeared twice will become zero.
   
**<h3>Code</h3>**

```
class Solution {
public:
	int missingNumber(vector<int>& nums) {
		int a = 0;
        for (int i = 0; i < nums.size(); i++) {
            a = a^nums[i]^i+1;
        }
        return a;
	}
};
```
