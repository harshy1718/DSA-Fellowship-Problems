**<h3>Question</h3>**

The Tribonacci sequence Tn is defined as follows:

T0 = 0, T1 = 1, T2 = 1, and Tn+3 = Tn + Tn+1 + Tn+2 for n >= 0.

Given n, return the value of T(n).

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/f7212e08-0cbd-46f5-b87c-21907b046f36)

**<h3>Constraints</h3>**

1. 0 <= n <= 30 

**<h3>Approach</h3>**

1. We will use memoization and recursion in this question.
2. We will write a recursive function with the base case that we already know the tribonacci number corresponding to that n in the ans vector or n is either 0 or 1 or 2.
3. The recursive code will call the same help function for n-1 and n-2 and n-3 and then we add them and store the value of that tribonacci number corr to that n in the ans vector.

**<h3>Code</h3>**

```
class Solution {
public:
    int trib(int n, vector<int>&ans) {
        if (n == 0 || n == 1) return n;
        else if (n == 2) return 1;
        if (ans[n] != -1) return ans[n];
        else return ans[n] = trib(n-1,ans) + trib(n-2,ans) + trib(n-3,ans);
    }
    int tribonacci(int n) {
        vector<int>ans(n+1,-1);
        return trib(n,ans);
    }
};
```
