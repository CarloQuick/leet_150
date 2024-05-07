```
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        map<int, int> m;
        int index = 0;
        
        for(int i = 0; i < nums.size(); i++){
            if(!m.count(nums[i])){
                m[nums[i]] = 1;
                nums[index] = nums[i];
                index++;
            }
        }
        return index;       
    }
};
```
