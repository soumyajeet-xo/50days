# 268. Missing Number
## Solution : Simple mathematical formula to find sum from 0 to n   O(n)
```
class Solution {
    public int missingNumber(int[] nums) {
        int l=nums.length;
        int res=0;
        int r=(l*(l+1))/2;
        for(int i=0;i<l;i++){
            res=res+nums[i];
        }
        r=r-res;

        return r;
        
    }
}
```

## Solution : bit manipulation technique O(n) 
### Explanation : just xor all the number in the array and then xor 0 to length of the array... the repeating element will be cancelled and the unique element is the one missing in the array

```
class Solution {
    public int missingNumber(int[] nums) {
        int l=nums.length;
        int res=0;
        for(int i=0;i<l;i++){
            res=res^nums[i];
        }
        for(int i=0;i<=l;i++)
        res=res^i;

        return res;
        
    }
}
```
