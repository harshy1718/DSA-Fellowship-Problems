**<h3>Question</h3>**

Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/1771ffbc-58ab-4ce2-85bd-3e4a2d8fddb0)

**<h3>Constraints</h3>**

1. 1 <= nums.length <= 5*10<sup>4</sup> 
1. -10<sup>9</sup> <= prices[i] <= 10<sup>9</sup>

**<h3>Approach</h3>**

1. We know that this question can be done with the help of map or hash table but that takes up extra space and we want to do this question with minimal space.
2. WE know there is an element which is present more than n/2n/2n/2 times so keep a counter and element varaible which will track if element is same as previous then counter will be incremnted else decremented .
3. If our counter becomes 0 somewhere we will change the element because its lead is over now we will take another element (give chance to other as well) and keep doing the same with it.
4. But we will think that we might lose our element by taking the new element but no it will come again later.
5. Since we know there is an element whose occurence is more than n/2 times.
6. So no matter how many times we change the elemnt it will come again , either its counter will not become zero or it will come agian in lead because rest elements can have max n/2−1 occurence so they can't win form it.

**<h3>Code</h3>**

```
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int count = 1;
        int ele = nums[0];
        int n = nums.size();
        for (int i = 1; i < n; i++) {
            if (count == 0) {
                ele = nums[i];
            }

            if (nums[i] == ele) count++;
            else count--;
        }
        return ele;
    }
};
```
