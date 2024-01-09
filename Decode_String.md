**<h3>Question</h3>**

Given an encoded string, return its decoded string.

The encoding rule is: k[encoded_string], where the encoded_string inside the square brackets is being repeated exactly k times. Note that k is guaranteed to be a positive integer.

You may assume that the input string is always valid; there are no extra white spaces, square brackets are well-formed, etc. Furthermore, you may assume that the original data does not contain any digits and that digits are only for those repeat numbers, k. For example, there will not be input like 3a or 2[4].

The test cases are generated so that the length of the output will never exceed 10<sup>5</sup>.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/93bfd60d-d9a0-4481-8a1d-ff53235f6c3c)

**<h3>Constraints</h3>**

1. 1 <= s.length <= 30
1. s consists of lowercase English letters, digits, and square brackets '[]'.
2. s is guaranteed to be a valid input.
3. All the integers in s are in the range [1, 300].

**<h3>Approach</h3>**

1. We use recursion to solve this question.
2. In this we will use the base case that either the string has ended or we have reached the end of the square bracket.
3. At the end of every base case we add the word to the ans string and in the end we have the final answer that we return at the end of the for loop.

**<h3>Code</h3>**

```
class Solution {
public:
    string help(int & pos, string s) {
        int mul = 0;
        string word = "";
        for (; pos < s.size(); pos++) {
            if (s[pos] == '[') {
                string currstr = help(++pos,s);
                for (; mul > 0; mul--) word += currstr;
            }
            else if (s[pos] >= '0' && s[pos] <= '9') mul = mul*10 + s[pos]-'0';
            else if (s[pos] == ']') return word;
            else word += s[pos];
        }
        return word;
    }
    string decodeString(string s) {
        int pos = 0;
        return help(pos,s);
    }
};
```
