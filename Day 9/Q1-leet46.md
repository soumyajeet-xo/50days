# 46. Permutations
rec12
```
class Solution {
    public List<List<Integer>> permute(int[] nums) {
        List<List<Integer>> ans= new ArrayList<>(); // to store all the permutaion
        List<Integer> ds=new ArrayList<>(); // ds for operation
        boolean freq[]=  new boolean[nums.length]; // frequency array for marking if element is taken or not
        rec(nums,ds,ans,freq);
        return ans;
        
    }
    private void rec(int[] nums,List<Integer> ds,List<List<Integer>> ans,boolean[] freq){
        if(ds.size()==nums.length){
            ans.add(new ArrayList<>(ds));
            return;
        }
        for(int i=0;i<nums.length;i++){ //to check every possible number at a particular position
        if(!freq[i]){
            freq[i]=true; // mark it taken
            ds.add(nums[i]);
            rec(nums,ds,ans,freq);
            ds.remove(ds.size()-1); //remove it while backtrack
            freq[i]=false; //mark it not taken as it is removed for ds
        }
        }

    }
}
```
