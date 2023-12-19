**<h3>Question</h3>**

Given an array nums of n integers . Find the maximum number from an array.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/0bb1f00e-0457-4a25-b34a-ab6c68f41031)

**<h3>Constraints</h3>**

1. 1 <= n <= 10<sup>5</sup> 
1. -10<sup>6</sup> <= nums[i] <= 10<sup>6</sup>

**<h3>Approach</h3>**

1. We initialise a variable maxi which is initialised with the value nums[0].
2. Now we will traverse the array from the 2nd element of the array and compare it with maxi.
3. if the element is greater than maxi then we overwrite maxi with that particular element.
4. Once we are out of the loop we have our largest element of the array.

**<h3>Code</h3>**

```
class Solution {
    public:
   int findLargestElement(vector<int>& nums) {
     int maxi = nums[0];
     for (int i = 1; i < nums.size(); i++) {
       if (nums[i] > maxi) {
         maxi = nums[i];
       }
     }
     return maxi;
   }
};
```
