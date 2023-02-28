# 47. Permutations II

```
class Solution {
    public List<List<Integer>> permuteUnique(int[] nums) {
        List<List<Integer>> ans = new ArrayList<>();
        boolean []visited = new boolean[nums.length];
        Arrays.sort(nums);
        backtrack(nums, visited, new ArrayList<Integer>(), ans);
        return ans;
    }
    void backtrack(int [] nums , boolean[] visited, ArrayList<Integer> asf, List<List<Integer>> ans){
        if(asf.size() == nums.length){
            ans.add(new ArrayList<Integer>(asf));
            return ;
        }        
        for(int i =0 ; i < nums.length; i++){
            if(visited[i]) continue;
            if(i > 0 && nums[i-1] == nums[i] && !visited[i-1]) continue;
            visited[i] = true;
            asf.add(nums[i]);
            backtrack(nums, visited, asf, ans);
            visited[i] = false;
            asf.remove(asf.size()-1);
        }
        
    }
}
```
