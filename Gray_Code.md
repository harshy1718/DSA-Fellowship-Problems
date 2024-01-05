**<h3>Question</h3>**

An n-bit gray code sequence is a sequence of 2n integers where:

Every integer is in the inclusive range [0, 2<sup>n</sup> - 1],

The first integer is 0,

An integer appears no more than once in the sequence,

The binary representation of every pair of adjacent integers differs by exactly one bit, and

The binary representation of the first and last integers differs by exactly one bit.

Given an integer n, return any valid n-bit gray code sequence.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/58fb5565-d630-4370-a87a-de03beb7ebb3)

**<h3>Constraints</h3>**

1. 1 <= n <= 16

**<h3>Approach</h3>**

1. the formula for finding the gray code is taking XOR of i with half of i.
2. we will use that formula only to find the gray code of particular index.

**<h3>Code</h3>**

```
class Solution {
public:
	vector<int> grayCode(int n) {
		vector<int>ans;
        ans.push_back(0);
        for (int i = 1; i < pow(2,n); i++) {
            ans.push_back(i^(i>>1));
        }
        return ans;
	}
};
```
