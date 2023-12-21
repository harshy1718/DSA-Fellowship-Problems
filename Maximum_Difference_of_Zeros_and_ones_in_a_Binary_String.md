**<h3>Question</h3>**

Given a binary string s of 0's and 1's. The task is to find the maximum difference between the number of 0s and the number of 1s (number of 0s — number of 1s) for a substring . In case of all 1s print -1.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/c8ddad1e-ab2e-44a1-87b3-23a1110f16ba)

**<h3>Constraints</h3>**

1. 1 <= n <= 10<sup>5</sup> 
1. s contains only 0s and 1s

**<h3>Approach</h3>**

1. we initialise 2 variables maxi with the value INT_MIN and sum with value 0.
2. Now we traverse the array and if s[i] is 0 then we do sum++ else if s[i] is 1 we do sum--.
3. Then we check if sum is greater than maxi or not and if yes then we update maxi to sum.
4. then we check if sum is getting negative or not if yes then we make sum 0.
5. This is done so that whenever we add the next element its entire value is added and not the one which is reduced by negative sum.
6. At the end of the loop we check if maxi is 0  or not. If maxi is 0 we return -1 else we return maxi.

**<h3>Code</h3>**

```
class Solution {
public:
	int getMaxDifference(string s) {
		int sum = 0, maxi = INT_MIN;
        for (int i = 0; i < s.length(); i++) {
            if (s[i] == '0') sum++;
            else sum--;

            if (maxi < sum ) maxi = sum;
            if (sum < 0) sum = 0;
        }
        if (maxi == 0) return -1;
        return maxi;
	}
};
```
