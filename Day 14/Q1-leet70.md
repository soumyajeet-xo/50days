# 70. Climbing Stairs
You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?
<br>
dp2
```
class Solution { //memoization
    public int climbStairs(int n) {
        int dp[]=new int[n+1]; //declaration
        Arrays.fill(dp,-1);
        return cs(n,dp);
    }
    public int cs(int n, int[] dp){
        if(n<=1) return 1;
        if(dp[n]!= -1) return dp[n]; //check
        return dp[n]= cs(n-1,dp) + cs(n-2,dp); // storing
    }
}
```
