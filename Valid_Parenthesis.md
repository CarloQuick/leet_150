```
class Solution {
public:
    bool isValid(string s) {
        stack<char> stk;
        if(s.size() == 1)
            return false;

        for(int i = 0; i < s.size(); i++){
            char currChar = s[i];
            if(currChar  == '(' || currChar  == '[' || currChar == '{')
                stk.push(currChar);
            else if(currChar  == ')'){
                if(!stk.empty() && stk.top() == '(')
                    stk.pop();
                else
                    return false;
            }
            else if(!stk.empty() && currChar  == ']'){
                if(stk.top() == '[')
                    stk.pop();
                else
                    return false;
            }
            else if(!stk.empty() && currChar  == '}'){
                if(stk.top() == '{')
                    stk.pop();
                else
                    return false;
            }
            else
                stk.push(currChar);
        }
        return stk.empty();      
    }
};
```
