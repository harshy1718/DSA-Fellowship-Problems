**<h3>Question</h3>**

You are given an array rectangles where rectangles[i] = [li, wi] represents the ith rectangle of length li and width wi.

You can cut the i<sup>th</sup> rectangle to form a square with a side length of k if both k <= l<sub>i</sub> and k <= w<sub>i</sub> For example, if you have a rectangle [4,6], you can cut it to get a square with a side length of at most 4.

Let maxLen be the side length of the largest square you can obtain from any of the given rectangles.

Return the number of rectangles that can make a square with a side length of maxLen.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/7b9a0255-f3b9-4a98-8e5d-1c524694bb29)

**<h3>Constraints</h3>**

1. 1 <= rectangles.length <= 1000
2. 1 <= l<sub>i</sub>, w<sub>i</sub> <= 10<sup>9</sup>
3. rectangles[i].length == 2
4. l<sub>i</sub> != w<sub>i</sub>


**<h3>Code</h3>**

```
class Solution {
public:
    int countGoodRectangles(vector<vector<int>>& rectangles) {
        int count = 0, n = rectangles.size(), maxi = -1;
        for (int i = 0; i < n; i++) {
            int sol = min(rectangles[i][0],rectangles[i][1]);
            if (sol == maxi) count++;
            else if (maxi < sol) {
                count = 1;
                maxi = sol;
            }
        }
        return count;
    }
};
```
