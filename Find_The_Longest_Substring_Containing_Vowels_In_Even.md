**<h3>Question</h3>**

Given the string s, return the size of the longest substring containing each vowel an even number of times. That is, 'a', 'e', 'i', 'o', and 'u' must appear an even number of times.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/c706d775-1ea1-48ca-aac1-06cd042e219b)

**<h3>Constraints</h3>**

1. 1 <= s.length <= 5*10<sup>5</sup>
2. s contains only english lowercase letters.

**<h3>Approach</h3>**

1. There are many brute force approaches to solve this question but we will use the bitmasking approach to solve this question in an optimised way.
2. we will start with an integer num that is initialised to 0 and then we will traverse the for loop and check every letter of the string whenever we encounter a vowel we will just take XOR of num with the vowel - 'a' + 1.
3. We have made a map to see which number do we have at i whenever we perform any XOR operation.
4. Then we check if that number has appeared before or not in the map. If yes then we update ans to the max length as the max length will be when we have the same number at two different places that means that either there are no vowels in that gap or the vowels were in even number.
5. We repeat this till the end of the loop and at the end we have the longest substring.

**<h3>Code</h3>**

```
class Solution {
public:
    int findTheLongestSubstring(string s) {
        int num = 0, n = s.length(),start = 0, count = 0,ans = 0;
        unordered_map<int,int>mp;
        mp[0] = -1;
        for (int i = 0; i < n; i++) {
            if (s[i] == 'a' || s[i] == 'e' || s[i] == 'i' || s[i] == 'o' || s[i] == 'u') {
                num ^= (s[i]-'a'+1);
            }
            if (mp.count(num)) {
                ans = max(ans,i - mp[num]);
            }
            else mp[num] = i;
        }
        return ans;
    }
};
```
