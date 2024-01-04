**<h3>Question</h3>**

You are given a string s and an integer k. You can choose any character of the string and change it to any other uppercase English character. You can perform this operation at most k times.

Return the length of the longest substring containing the same letter you can get after performing the above operations.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/8faf1522-f73f-4821-911c-5b0ab2d96757)

**<h3>Constraints</h3>**

1. 1 <= s.length <= 10<sup>5</sup>
2. s consists of only uppercase english letters
3. 0 <= k <= s.length

**<h3>Approach</h3>**

1. We are going to do this question using the sliding window approach.
2. For that we will maintain a vector where we will keep track of the frequency of a letter appearing.
3. we will maintain variables st(keeps track of starting point of window) , e(keeps track of the ending of the window), n(size of the string) and longest(keeps track of the longest window so far).
4. we will run a loop and keep track of how many times a letter has appeared in the current window by using the vector v.
5. We will also keep track of the highest frequency letter of the window by updating it every time there is a change in the window.
6. Next we will see if the minimum repeating letter in the window is less than or equal to k or not and the lowest repeating letter will be size of window(e - st) - the mx(highest frequency letter).
7. In the end of the loop we will return the longest window length so far.

**<h3>Code</h3>**

```
class Solution {
public:
    int characterReplacement(string s, int k) {
        vector<int>v(26,0);
        int st = 0, e = 0, longest = 0, n = s.size(),mx = 1;
        while (e < n) {
            v[s[e]-'A']++;
            mx = max(mx,v[s[e++]-'A']);
            if (e-st-mx <= k) longest = max(longest,e-st);
            else v[s[st++]-'A']--;
        }
        return longest;
    }
};
```
