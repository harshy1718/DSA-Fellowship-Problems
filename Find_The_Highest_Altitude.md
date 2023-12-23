**<h3>Question</h3>**

There is a biker going on a road trip. The road trip consists of n + 1 points at different altitudes. The biker starts his trip on point 0 with altitude equal 0.

You are given an integer array gain of length n where gain[i] is the net gain in altitude between points i​​​​​​ and i + 1 for all (0 <= i < n). Return the highest altitude of a point.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/18a87f9d-ebf7-47f1-9321-5539a7afed5b)

**<h3>Constraints</h3>**

1. 1 <= gain.length <= 10<sup>2</sup> 
1. -100 <= gain[i] <= 10<sup>2</sup>

**<h3>Approach</h3>**

1. We will take 2 variables namely sum and maxi.
2. The variable sum will be used to keep on adding the altitude length.
3. And maxi will be used to keep track of the maximum altitude obtained so far.
4. Maxi is initialised to 0 because we start from ground level that is 0.
5. At the end of the for loop we have the highest altitude.

**<h3>Code</h3>**

```
class Solution {
public:
    int largestAltitude(vector<int>& gain) {
        int maxi = 0;
        int sum = 0;
        for (int i = 0; i < gain.size(); i++) {
            sum += gain[i];
            if (sum > maxi) maxi = sum;
        }
        return maxi;
    }
};
```
