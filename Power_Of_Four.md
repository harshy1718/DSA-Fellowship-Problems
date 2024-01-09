**<h3>Question</h3>**

Given an integer n, return true if it is a power of four. Otherwise, return false.

An integer n is a power of four, if there exists an integer x such that 
n == 4<sup>x</sup>

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/0750b013-e7c7-4d52-8e37-21725bd4415b)

**<h3>Constraints</h3>**

1. -2<sup>31</sup> <= n <= 2<sup>31</sup> - 1

**<h3>Approach</h3>**

1. We are going to use recursion for this one and the recursive code will be totally based on if else statements.
2. The base case will be checking if n is 0 or 1 and returning false if n is 0 else true is n is 1.
3. Then we will check if n si divisible by 4 or not if yes then we pass n/4 in the recursive case else we return false.

**<h3>Code</h3>**

```
class Solution {
public:
    bool ans = true;
	bool isPowerOfFour(int n) {
        if (n == 0) {
            ans = ans & false;
        }
		else if (n == 1) {
            ans = ans & true;
        }
        else if (n % 4 == 0) {
            ans = ans & isPowerOfFour(n/4);
        }
        else if (n %4 != 0 && n != 1) {
            ans = ans & false;
        }
        return ans;
	}
};
```
