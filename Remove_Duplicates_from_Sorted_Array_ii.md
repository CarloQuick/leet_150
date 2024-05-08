```
class Solution {
public:
    // credit for solution - StefanPochmann
    // https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/solutions/27976/3-6-easy-lines-c-java-python-ruby
    int removeDuplicates(vector<int>& nums) {
        int i = 0;
        for(int n : nums){
            if(i < 2 || n > nums[i-2]){
                nums[i] = n;
                i++;
            }
        }
        return i;
    }
};
```
