// got help from https://leetcode.com/problems/summary-ranges/solutions/1805583/c-detailed-explanation-w-dry-run-faster-than-100-basic-concept-used
```
class Solution {
public:
    vector<string> summaryRanges(vector<int>& nums) {
        int n = nums.size();

        vector<string> res;
        string s = "";

        for(int i = 0; i < n; i++){
            int ptr = i;
            while(ptr + 1 < n && nums[ptr+1] == nums[ptr] + 1) // finding range
                ptr++;
            
            if(ptr > i) // more than one element
                s += to_string(nums[i]) + "->" + to_string(nums[ptr]);
            else
                s += to_string(nums[i]);
    
            res.push_back(s);
            s = "";
            i = ptr;
    }
    return res;
    }
};
```
