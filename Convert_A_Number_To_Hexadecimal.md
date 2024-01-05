**<h3>Question</h3>**

Given an integer num, return a string representing its hexadecimal representation. For negative integers, two’s complement method is used.

All the letters in the answer string should be lowercase characters, and there should not be any leading zeros in the answer except for the zero itself.

Note: You are not allowed to use any built-in library method to directly solve this problem.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/51c2a3c5-12a9-49ff-b4e1-a4f5122e955e)

**<h3>Constraints</h3>**

1. -2<sup>31</sup> <= num <= 2<sup>31</sup> - 1

**<h3>Approach</h3>**

1. We will use the same algorithm that we used in the Base 7 question just the difference will be that in this case we will have to tackle the negative integers as well.
2. So for that we will use the unsigned int variable that converts any negative integer to positive integer in the bitwise manner.
3. once we have taken care of the negative sign we can use the usual way to convert decimal to hexadecimal for that we will use a string of soze 17 that will consist of all the numbers and the letters corresponding to the remainder that we get while dividing the num by 16.

**<h3>Code</h3>**

```
class Solution {
public:
    string toHex(int num) {
        string s = "0123456789abcdef";
        string ans;
        unsigned int n = num;
        if (n == 0) return {"0"};
        while(n) {
            ans += s[n%16];
            n /= 16;
        }
        reverse(ans.begin(),ans.end());
        return ans;
    }
};
```
