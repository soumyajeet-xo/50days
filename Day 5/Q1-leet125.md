# 125. Valid Palindrome
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

### Solution : Brute Force 

```
class Solution {
    public boolean isPalindrome(String s) {
        s=s.trim();char c;
        s=s.toUpperCase();
        String sn="";
        String rev="";
        int l=s.length();
        for(int i=0;i<l;i++){
            c=s.charAt(i);
            if((c>=65 && c<=90) || (c>=48 && c<=57)){
            sn=sn+c;
            rev=c+rev;
            }
        }
        if(sn.equals(rev)==true)
        return true;
        else
        return false;
    }
}
```
