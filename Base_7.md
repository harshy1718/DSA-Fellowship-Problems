**<h3>Question</h3>**

Given an integer num, return a string of its base 7 representation.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/363ecd69-480d-4b25-a44e-669ec424bc2e)

**<h3>Constraints</h3>**

1. -10<sup>7</sup> <= num <= 10<sup>7</sup> 

**<h3>Approach</h3>**

1. We will use the same technique that we use to convert decimals to bits.
2. We will take num and find its remainder when divided by 7 that will be the ones place for the answer string.
3. Then we will divide num by 7 and again do the same process but this time the remainder will be the tens place digit and then the hundreds place digit and son on till the valueof num becomes 0.

**<h3>Code</h3>**

```
class Solution {
public:
    string convertToBase7(int num) {
        int ans = 0, i = 0;
        while (num != 0) {
            ans += (num%7)*pow(10,i);
            i++;
            num /= 7;
        }
        return to_string(ans);
    }
};
```
