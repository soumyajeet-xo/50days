# 217. Contains Duplicate
### Explanation : Sort the array and check the consecutive elements... dont forget the last index edge case
```
class Solution {
    public boolean containsDuplicate(int[] nums) {
        int l=nums.length; // 3 [0,2,2]
        Arrays.sort(nums);
        for(int i=1;i<l;i++){

            if(i==l-1){
                if((nums[l-1]==nums[l-2]))
                return true;
            }
            else{
            if(nums[i-1]==nums[i] || nums[i]==nums[i+1])
            return true;
            }
        }
        return false;
    }
}
```
