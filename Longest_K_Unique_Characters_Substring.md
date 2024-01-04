**<h3>Question</h3>**

Given a string you need to return the size of the longest possible substring that has exactly K unique characters. If there is no possible substring then print -1.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/08309e11-cc58-4462-8b47-4518dd9e7f9b)

**<h3>Constraints</h3>**

1. 1 <= |S| <= 10<sup>5</sup>
2. all characters are lowercase latin characters
3. 1 <= k <= 26

**<h3>Approach</h3>**

1. We are going to do this question using the sliding window approach.
2. For that we will maintain a vector where we will keep track of the frequency of a letter appearing.
3. we will maintain variables st(keeps track of starting point of window) , e(keeps track of the ending of the window), n(size of the string) and longest(keeps track of the longest window so far).
4. we will run a loop and keep track of how many times a letter has appeared in the current window by using the vector v.
5. We have made a function help which will tell us how many unique characters are there in the current window on the basis of which we will run a if else loop
6. So we will see if number of unique characters is equal to k then we we will update the value of longest else we will keep on increasing e and if number of unique characters int he string are more than k we will reduce the size of the window by increasing the value of st.
7. In the end we will return the longest variable.

**<h3>Code</h3>**

```
class Solution {
public:
	int help(vector<int>&v) {
		int count = 0;
		for (int i = 0; i < 26; i++) {
			if (v[i] != 0) count++;
		}
		return count;
	}
	int longestKSubstr(string s, int k) {
		vector<int>v(26,0);
		int st = 0, e = 0, n = s.size(),longest = -1;
		while (e < n) {
			v[s[e]-'a']++;
			int num = help(v);
			if (num == k) {
				longest = max(longest,e-st+1);
				e++;
			}
			else if (num < k) e++;
			else {
				e++;
				v[s[st++]-'a']--;
			}
		}
		return longest;
	}
};
```
