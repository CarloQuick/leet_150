// https://www.youtube.com/watch?v=1IzCRCcK17A
```
class Solution {
public:
    int candy(vector<int>& ratings) {
        int n = ratings.size();
        vector<int> res(n,1); 

        for(int i = 0; i < n; i++){
            if(i - 1 >= 0){
                if(ratings[i-1] < ratings[i]){
                    res[i] = res[i-1] + 1;
                }
            }
        }
        for(int i = n-1; i >=0; i--){
            if( i + 1 < n){
                if(ratings[i] >  ratings[i+1] &&
                res[i] <= res[i+1]){
                    res[i] = res[i+1] + 1;
                }
            }
        }

        int ans = 0;
        for(int i = 0; i < res.size(); i++){
            ans += res[i];
        }
        return ans;
        
    }
};
```
