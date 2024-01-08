**<h3>Question</h3>**

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/8703702e-bc06-4ef0-8155-47e686635bde)

**<h3>Constraints</h3>**

1. 1 <= s,length <= 2*10<sup>5</sup> 

**<h3>Approach</h3>**

1. First we will make an additional string in which we will store only the alphabets and numbers and remove all the spaces and the unwanted characters.
2. Then we will pass it to the recursive code where the base case will be when we have traversed more than half the string.
3. We will just check the first and last part of the string for palindrome check.

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
