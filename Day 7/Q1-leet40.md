# 39. Combination Sum 
Rec9 Medium <br><br>
Given a collection of candidate numbers (candidates) and a target number (target), find all unique combinations in candidates where the candidate numbers sum to target.

Each number in candidates may only be used once in the combination.

Note: The solution set must not contain duplicate combinations.
```
class Solution {
    public List<List<Integer>> combinationSum2(int[] candidates, int target) {
        List<List<Integer>> ans= new ArrayList<>(); //to hold the final answer
        Arrays.sort(candidates); // easy to find repetition and we need sorted combination
        comb(0,candidates,target,ans,new ArrayList<>()); //new ds will store the combination at various stages
        return ans;
    }

    private void comb(int ind,int[] arr,int target,List<List<Integer>> ans,List<Integer> ds){
        if(target==0){
            ans.add(new ArrayList<>(ds));
            return;
        }
        for(int i=ind;i<arr.length;i++){  //see rec tree all position from i to end is checked
        if(i>ind && arr[i]==arr[i-1])continue; //>ind so if it is the 1st occurence it doesnt stops otherwise stops
        if(arr[i]>target) break;  //we found the target.. the particular rec ends

        ds.add(arr[i]);
        comb(i+1,arr,target-arr[i],ans,ds); // to go to the next child of the tree
        ds.remove(ds.size()-1); // removal of the element during backtrack
        }
    }
}
```


Another solution includes using the logic of combination sum 1.. and increasing the index everytime. The ans must be stored in a HashSet to avoid repetition
