```
class Solution {
public:
    // credits to fabrizo3
    // https://leetcode.com/problems/integer-to-roman/solutions/6274/simple-solution
    string intToRoman(int num) {
    string M[] = {"", "M", "MM", "MMM"};
    string C[] = {"", "C", "CC", "CCC", "CD", "D", "DC", "DCC", "DCCC", "CM"};
    string X[] = {"", "X", "XX", "XXX", "XL", "L", "LX", "LXX", "LXXX", "XC"};
    string I[] = {"", "I", "II", "III", "IV", "V", "VI", "VII", "VIII", "IX"};
    int thousands = num /1000; // Extract thousands place
    int hundreds = (num / 100) % 10; // Extract hundreds place
    int tens = (num / 10) % 10; // Extract tens place 
    int ones = num % 10; // Extract ones place 
    return M[thousands]+C[hundreds]+X[tens]+I[ones];
    }
};
```
