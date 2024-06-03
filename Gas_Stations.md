// https://leetcode.com/problems/gas-station/solutions/1706142/java-c-python-an-explanation-that-ever-exists-till-now
```
class Solution {
public:
    int canCompleteCircuit(vector<int>& gas, vector<int>& cost) {
        int n = gas.size();
        int start = 0;
        int totalSurplus = 0;
        int currSurplus = 0;

        for(int i = 0; i < n; i++){
            totalSurplus += gas[i] - cost[i]; // geting the suplus for later comparison
            currSurplus += gas[i] - cost[i];

            if(currSurplus < 0){
                currSurplus = 0;
                start = i+1;
            }
        }
         return (totalSurplus >= 0) ? start : -1;
    }
};
```
