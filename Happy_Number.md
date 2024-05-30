// was not able to do this one on my own
// I relieved heavily one the follow solution:
// https://leetcode.com/problems/happy-number/solutions/56917/my-solution-in-c-o-1-space-and-no-magic-math-property-involved
```
class Solution {
public:
    int digitSquareSum(int n){
        int sum= 0;
        while(n){
            int tmp = n % 10;
            sum += tmp * tmp;
            n /= 10;
        }
        return sum;
    }
    bool isHappy(int n) {
        int slow, fast; 
        slow = n;
        fast = digitSquareSum(n);
        while(slow != fast){
            slow = digitSquareSum(slow);
            fast = digitSquareSum(digitSquareSum(fast));
        }
        return slow == 1;
    }
};
```
