**<h3>Question</h3>**

Given two strings s and p, return an array of all the start indices of p's anagrams in s. You may return the answer in any order.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/2c02f2d8-eaea-4a75-90dd-f547076d2d13)

**<h3>Constraints</h3>**

1. 1 <= s.length,p.length <= 3*10<sup>4</sup> 
1. s and p consist of only lowercase letters.

**<h3>Approach</h3>**

1. We will make 2 maps in order to keep the count of the different number of letters in both the string p and the substring of string s of size p.
2. Now first we will put all the letters of p into map m and simultaneously we will also put the letters in the map mp.
3. Then we will check if both the mpas are same or not if yes then we will push 0 into the answer vector v.
4. Then we will use sliding window technique to keep track of the number of letters in the substring of s of size p.
5. Then again we will check if both the maps are same or not.
6. In the end we will return the vector v.

**<h3>Code</h3>**

```
class Solution {
public:
    vector<int> findAnagrams(string s, string p) {
        unordered_map<char,int>m;
        unordered_map<char,int>mp;
        vector<int>v;
        int n = s.length();
        int k = p.length();
        for (int i = 0; i < k; i++) {
            m[p[i]]++;
            mp[s[i]]++;
        }
        if (m == mp) v.push_back(0);
        for (int i = k; i < n; i++) {
            mp[s[i-k]]--;
            mp[s[i]]++;
            if (mp[s[i-k]] == 0) mp.erase(s[i-k]);
            if (m == mp) v.push_back(i-k+1);
        }
        return v;
    }
};
```
