**<h3>Question</h3>**

Monk's best friend Micro's birthday is coming up. Micro likes Nice Strings very much, so Monk decided to gift him one. Monk is having N nice strings, so he'll choose one from those. But before he selects one, he need to know the Niceness value of all of those. Strings are arranged in an array A, and the Niceness value of string at position i is defined as the number of strings having position less than i which are lexicographicaly smaller than A[i]. Since nowadays, Monk is very busy with the Code Monk Series, he asked for your help.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/eb02cc9c-963d-4d82-93e6-c392d3759bd9)

**<h3>Constraints</h3>**

1. 1 <= length of (A[i]) <= 10
2. 1 <= A.length <= 10<sup>5</sup>
3. A[i] consists of lowercase english letters.

**<h3>Approach</h3>**


**<h3>Code</h3>**

```
class Solution {
public:
	vector<int> niceStrings(vector<string>& A) {
        vector<int>ans;
        ans.push_back(0);
        for (int i = 1; i < A.size(); i++) {
            int sol = 0;
            for (int j = 0; j < i; j++) {
                if (A[j] < A[i]) sol++; 
            }
            ans.push_back(sol);
        }
        return ans;
	}
};
```
