# 191. Number of 1 Bits

## Solution 1 : 
``` 
public class Solution {
    // you need to treat n as an unsigned value
    public int hammingWeight(int n) {
        int dup=n;
        int c=0;
        while(dup!=0){
            if((dup&1)==0)
            c++;
            dup=dup>>1;

        }
        return c;
    }
}
```
## Explanation : 
This will be time limit exceeded though <b/>
if the number & 1 == 0, it is even, then last digit is 0; else last digit is 1... when last digit is 1.. c++. <br/>
the number is right shifted regardless.. the get rid of the last bit


```
public class Solution {
    // you need to treat n as an unsigned value
    public int hammingWeight(int n) {
        int dup=n;
        int c=0;
        while(dup!=0){
            dup=dup&(dup-1);
            c++;
        }
        return c;
    }
}
```
## Explanation
dup*(dup-1) just makes least significant bit to 0. i.e right most set bit to 0;  <br />
set bit is the bit whose value is 1 <br/>

-Soumyajeet
