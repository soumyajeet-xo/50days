dp3 - frog jump
# 403. Frog Jump

```
class Solution {
    public boolean canCross(int[] stones) {
        return frogJump(stones, 0, 0, stones[0], new Boolean[stones.length][stones.length - 1]);
    }
    
    private boolean frogJump(int[] arr, int index, int curr, int k, Boolean[][] dp) {
	   
        while(index < arr.length && curr > arr[index]) {
            index++;   
        }
        if(curr == arr[arr.length - 1]) return true;
        else if(index >= arr.length || curr != arr[index]) return false;       
        
        if(dp[index][k] != null) return dp[index][k];
        

        return dp[index][k] = frogJump(arr, index + 1, curr + k + 1, k + 1, dp) ||
               frogJump(arr, index + 1, curr + k, k, dp) ||
               frogJump(arr, index + 1, curr + k - 1, k - 1, dp);
    }
}
```
