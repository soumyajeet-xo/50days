# 90. Subsets II
Given an integer array nums that may contain duplicates, return all possible 
subsets
 (the power set).

The solution set must not contain duplicate subsets. Return the solution in any order.

 
```
class Solution {
    public List<List<Integer>> subsetsWithDup(int[] nums) {
        Arrays.sort(nums);
        List<List<Integer>> ans=new ArrayList<>();   
        sub(0,nums,ans,new ArrayList<>());
        return ans;
    }

    private void sub(int i,int[] nums,List<List<Integer>> ans,List<Integer> ds){
        ans.add(new ArrayList<>(ds));
        for(int j=i;j<nums.length;j++){
            if(j!=i && nums[j]==nums[j-1]) continue;
            ds.add(nums[j]);
            sub(j+1,nums,ans,ds);
            ds.remove(ds.size()-1);
        }
    }
}
```
