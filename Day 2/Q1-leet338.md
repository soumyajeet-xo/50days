# 338. Counting Bits

```
class Solution {
    public int[] countBits(int n) {
        int dup,c=0;
        int res[]=new int[n+1];
        for(int i=0;i<n+1;i++){
            dup=i;
            while(dup!=0){
                if((dup&1)!=0)
                c++;
                dup=dup>>1;
            }
            res[i]=c;
            c=0;
        }
        return res;
    }
}
```

# DP solution : no idea how its working

``` 
class Solution {
    public int[] countBits(int n) {
        int[] dp = new int[n + 1];
        dp[0] = 0;
        for (int i = 1; i <= n; i++) {
            dp[i] = dp[i >> 1] + (i % 2);
        }
        return dp;
    }
}
```
