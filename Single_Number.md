**<h3>Question</h3>**

Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/17f16cd5-abc0-4d37-9ba0-2b5c0600866b)

**<h3>Constraints</h3>**

1. 1 <= nums.length <= 3*10<sup>4</sup> 
1. -3* 10<sup>4</sup> <= nums[i] <= 3* 10<sup>4</sup>

**<h3>Approach</h3>**

1. We initialise an element **a** to 0 and as we traverse the array we keep on taking its XOR with nums[i].
2. Now we know that XOR of any number with itself is zero only sso once the for loop is ended **a** will contain only that element that appeared once only.

**<h3>Code</h3>**

```
class Solution {
public:
	int singleNumber(vector<int>& nums) {
        int a = 0;
        for (int i = 0; i < nums.size(); i++) {
            a ^= nums[i];
        }
        return a;
	}
};
```
