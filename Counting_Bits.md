**<h3>Question</h3>**

Given an integer n, return an array ans of length n + 1 such that for each i** (0 <= i <= n), ans[i] is the number of 1's in the binary representation of i.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/20c4c03f-481d-4226-a6c6-eab86c6e16f3)

**<h3>Constraints</h3>**

1. 0 <= n <= 10<sup>5</sup> 

**<h3>Approach</h3>**

1. if we will lool closely in the number of bits of every positive integer we will see that the number of bits in any integer can be related to the number of bits in integer/2.
2. For example bits in 2 = 1, bits in 4 = 1, bits in 8 = 1. All power of 2 have bits equal to 1.
3. If we look at the odd numbers like - 1 has 1 bit, 3 has 2 bits, 5 has 2 bits that is equal to number of bits in 5/2 i.e. 2 + 1.
4. So the pattern is that number of bits in i(odd) is equal to number of bits in i/2 + 1 and the number of bits in i(even) is equal to number of bits in i/2.
5. So we will use the same formula by running a loop from 1 to n+1.

**<h3>Code</h3>**

```
class Solution {
public:
    vector<int> countBits(int n) {
        vector<int>ans(n+1);
        ans[0] = 0;
        for (int i = 1; i <= n; i++) {
            if (i %2 == 0) ans[i] = ans[i/2];
            else ans[i] = ans[i/2] + 1;
        }
        return ans;
    }
};
```
