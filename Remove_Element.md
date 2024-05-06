![]

```
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        if(nums.size() == 0 || (nums.size() ==1 && nums[0] == val))
            return 0;
        int front = 0;
        int back = nums.size() - 1;
        int count = 0;
        while(front <= back){
            if(nums[back] == val){
                count++;
                back--;
                if(back < front)
                    break;
            }
            if(nums[front] == val){
                int temp = nums[front];
                nums[front] = nums[back];
                nums[back] = temp;
                if(nums[back] == val){
                    count++;
                    back--;
                }
            }
            else
                front++;
        }
        return (nums.size() - count);
    }
};
```
