**<h3>Question</h3>**

Implement pow(x, n), which calculates x raised to the power n (i.e., xn).

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/2abc2c5c-8e8e-4bf9-a3fe-681d76e3e756)

**<h3>Constraints</h3>**

1. -2<sup>31</sup> <= n <= 2<sup>31</sup> - 1
2. -100.0 <= x <= 100.0
3. n is an integer
4. -10<sup>4</sup> <= x<sup>n</sup> <= 10<sup>4</sup>

**<h3>Approach</h3>**

1. we will use recursion to solve this problem.
2. We need to tackle the negative powers as well so for that we will just make negative powers positive and make x to 1/x.
3. Then we will work on the recursion function named help.
4. We will make the base case as when n reaches 0 return 1.
5. To make it shorter and so that it takes less time we will divide the question in 2 parts like pow(2,10) is equal to pow(2,5)*pow(2,5).
6. Then it will depend on the value of n is that odd or even.
7. At the end of the recursion we will have our answer.

**<h3>Code</h3>**

```
class Solution {
public:
    double help(double x, int n) {
        if (n == 0) return 1.00;
        double half = help(x,n/2);
        if (n % 2 == 0) return half*half;
        else return half*half*x;
    }
    double myPow(double x, int n) {
        long long num = n;
        if (num < 0) {
            num = -num;
            x = 1/x;
        }
        return help(x,num);
    }
};
```
