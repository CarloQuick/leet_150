```
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int count = 1;
        int n = nums.size();
        sort(nums.begin(), nums.end());
        if(n == 1)
            return nums[0];
        
        for(int i = 0; i < n; i++){
            if(nums[i+1] == nums[i]){
                count++;
                if(count > n/2){
                    return nums[i];
                }
            }
            else
                count = 1;
        }
        return -1;
    }
};
```
