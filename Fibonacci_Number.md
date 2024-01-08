**<h3>Question</h3>**

The Fibonacci numbers, commonly denoted F(n) form a sequence, called the Fibonacci sequence, such that each number is the sum of the two preceding ones, starting from 0 and 1. That is,

F(0) = 0, F(1) = 1

F(n) = F(n - 1) + F(n - 2), for n > 1.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/cec23428-1e8e-4674-84a6-8e52dabf7181)

**<h3>Constraints</h3>**

1. 0 <= n <= 30 

**<h3>Approach</h3>**

1. We will use memoization and recursion in this question.
2. We will write a recursive function with the base case that we already know the fibonacci number corresponding to that n in the ans vector or n is either 0 or 1.
3. The recursive code will call the same help function for n-1 and n-2 and then we add them and store the value of that fibonacci number corr to that n in the ans vector.

**<h3>Code</h3>**

```
class Solution {
public:
    bool revStr(string& sol, int i){
        int len=sol.length();
        if(i>=len/2) return true;
        else if (sol[i]!=sol[len-i-1]) return false;
        return revStr(sol, i+1);
    }

    bool isPalindrome(string s) {
        string sol;
        for(int i=0;i<s.length();i++){
            if(s[i]>='A'&&s[i]<='Z') sol.push_back(tolower(s[i]));
            else if(s[i]>='a'&&s[i]<='z'||s[i]>='0'&&s[i]<='9') sol.push_back(s[i]);
        }
        return revStr(sol, 0);
    }
};
```
