# 39. Combination Sum 
Medium <br><br>
Given an array of distinct integers candidates and a target integer target, return a list of all unique combinations of candidates where the chosen numbers sum to target. You may return the combinations in any order.

The same number may be chosen from candidates an unlimited number of times. Two combinations are unique if the 
frequency
 of at least one of the chosen numbers is different.

The test cases are generated such that the number of unique combinations that sum up to target is less than 150 combinations for the given input.

```
// rec8
class Solution {
    public List<List<Integer>> combinationSum(int[] candidates, int target) {
        List<List<Integer>> ans=new ArrayList<>(); // final data structure
        comb(0,candidates,target,ans, new ArrayList<>()); // empty ds at right
        return ans;
    }

    private void comb(int i,int[] arr,int target,List<List<Integer>> ans,List<Integer> ds){
        if(i==arr.length){
            if(target==0){ // i.e we got the target as there is no more target left
                ans.add(new ArrayList<>(ds)); // return the new formed datastructure // add is not a constant operation.. linear
            }
            return;
        }

        if(arr[i]<=target){ //otherwise result will be more than target 
            ds.add(arr[i]);
            comb(i,arr,target-arr[i],ans,ds); //minus the the element for the target so the desired target is left
            ds.remove(ds.size()-1); // when it goes for case 2 the element which was added is removed.
        }
        comb(i+1,arr,target,ans,ds); // i.e do not pick
    }
}
```

 
