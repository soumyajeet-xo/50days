# 190. Reverse Bits

## Solution : 
``` 
public class Solution {
    // you need treat n as an unsigned value
    public int reverseBits(int n) {
       int res=0;
        for(int i=1;i<=32;i++){
            res=res<<1;
            if((n&1)==1)
            res=res^1;
            n=n>>1;
        }
        return res;
    }
}
```

Another method include something with cache and hashmap which i couldnt understand
