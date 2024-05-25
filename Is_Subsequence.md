```
class Solution {
public:
    bool isSubsequence(string s, string t) {
        // if t is smaller than s return false

        if(t.length() < s.length()){
            return false;
        }
        int sPtr = 0;
        int tPtr = 0;
        while( tPtr != t.length()){
            if(s[sPtr] == t[tPtr]){
                sPtr++;
                tPtr++;
            }
            else{
                tPtr++;
            }
        }
        cout << s.length();
        if(sPtr == s.length())
            return true;
        else{
            return false;
        }
        
    }
};
```
