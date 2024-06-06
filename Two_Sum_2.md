```
class Solution {
public:
    vector<int> twoSum(vector<int>& numbers, int target) {
        int l = 0;
        int n = numbers.size();
        int r = n - 1;
        
        vector<int> res;
        if(n == 2){
            res.push_back(1);
            res.push_back(2);
            return res;
        }
        while(l != r){
            if(numbers[l] + numbers[r] > target){
                r--;
            }
            if(numbers[l] + numbers[r] < target){
                l++;
            }
            if(numbers[l] + numbers[r] == target){
                res.push_back(l + 1);
                res.push_back(r + 1);
                break;
            }
        }
    return res;
    }
};
```
