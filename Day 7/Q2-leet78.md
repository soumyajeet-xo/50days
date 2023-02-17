# 78. Subsets
Given an integer array nums of unique elements, return all possible 
subsets
 (the power set).

The solution set must not contain duplicate subsets. Return the solution in any order. <br>
Medium <br>
Explanation : contagious sub sequence using take and not take algorithm <br>
Dont forget to remove the last element while backtrack... not nums[i] but ds.size()-1
```
class Solution {
    public List<List<Integer>> subsets(int[] nums) {
        List<List<Integer>> ans= new ArrayList<>();
        sub(0,nums,ans,new ArrayList<>());
        return ans;
    }
    private void sub(int i,int[] nums, List<List<Integer>> ans ,List<Integer> ds){
        if(i>=nums.length){
            ans.add(new ArrayList<>(ds));
            return;
        }
        ds.add(nums[i]);
        sub(i+1,nums,ans,ds); //left child call i.e take
        ds.remove(ds.size()-1); //removal of the end element after backtrack
        sub(i+1,nums,ans,ds); //right child call i.e not take
    }
}
```
