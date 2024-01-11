**<h3>Question</h3>**

A new deadly virus has infected large population of a planet. A brilliant scientist has discovered a new strain of virus which can cure this disease. Vaccine produced from this virus has various strength depending on midichlorians count. A person is cured only if midichlorians count in vaccine batch is more than midichlorians count of person. A doctor receives a new set of report which contains midichlorians count of each infected patient, Practo stores all vaccine doctor has and their midichlorians count. You need to determine if doctor can save all patients with the vaccines he has. The number of vaccines and patients are equal.

Return true if Possible else return false.

**<h3>Example</h3>**

![image](https://github.com/harshy1718/DSA-Fellowship-Problems/assets/129788726/e3e852df-22d6-4605-b886-b2dfd19ea904)

**<h3>Constraints</h3>**

1. 1 <= n <= 100
2. 1 <= Array Elements <= 10<sup>5</sup>

**<h3>Approach</h3>**

1. Sort both the arrays and then check one by one if vaccine at ith position has less vaccines or not than the midichlorians at the ith position.
2. If we find any case where vaccines are less than midichlorians then we return false.
3. Else at the end of the loop we return true.

**<h3>Code</h3>**

```
class Solution {
public:
	bool savePatients(vector<int>& vaccine, vector<int>& midichlorians) {
		sort(vaccine.begin(),vaccine.end());
        sort(midichlorians.begin(),midichlorians.end());
        for (int i = 0; i <vaccine.size(); i++) {
            if (vaccine[i] <= midichlorians[i]) return false;
        }
        return true;
	}
};
```
