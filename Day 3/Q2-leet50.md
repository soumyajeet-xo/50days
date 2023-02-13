50. Pow(x, n)
### Explanation : Lecture & dsa one ; a^b = (a^2)^(b/2) when b is even and a*a^(b-1) when b is odd
```
class Solution {
    public double myPow(double x, int n) {
        if(n < 0){
            n = -n;
            x = 1 / x; // edge case which was causing time limit exceeded
        }

        double res=1;
        while(n!=0){
            if((n&1)!=0)
            res=res*x;
            x=x*x;
            n>>>=1;
        }
        return res;
        
    }
}


```
