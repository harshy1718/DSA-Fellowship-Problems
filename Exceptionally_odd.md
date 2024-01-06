**<h3>Question</h3>**

Given an array of N positive integers where all numbers occur even number of times except one number which occurs odd number of times. Find the exceptional number.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/9079ce8a-25f8-4481-803c-8a86821d2702)

**<h3>Constraints</h3>**

1. 1 <= N <= 10<sup>5</sup>
2. 1 <= arr[i] <= 10<sup>6</sup>

**<h3>Approach</h3>**

1. We will traverse the array one by one and keep on taking XOR of every number the numbers that will appear even number of times will become 0 after taking XOR with each other.
2. At the end of the for loop the only number we will have will be the one that appeared odd umber of times.

**<h3>Code</h3>**

```
class Solution {
public:
	int getOddOccurrence(vector<int>& arr) {
        int a = 0;
        for (int i = 0; i < arr.size(); i++) {
            a = a^arr[i];
        }
        return a;
	}
};
```
