# 204. Count Primes
## Explanation : Sieve of Eratosthenes (check notes)
```
class Solution {
    public int countPrimes(int n) {
      boolean prime[]=new boolean[n+1];
      Arrays.fill(prime, true);
      for(int i=2;i*i<=n;i++){
          if(prime[i]==true){
            for(int p=i*i;p<=n;p+=i){
                prime[p]=false;
            }
          }
      }
      int c=0;
      for(int i=2;i<n;i++){
          if(prime[i]==true)
          c++;
      }
      return c;
    }
}
```
