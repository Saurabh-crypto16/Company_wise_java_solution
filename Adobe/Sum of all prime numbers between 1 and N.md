```java
class Solution
{
    public long prime_Sum(int n)
    {
        boolean[] primes=new boolean[n+1];
        Arrays.fill(primes,true);
        for(int i=2;i<=n;i++){
            if(primes[i]){
                for(int j=i*2;j<=n;j=j+i){
                    primes[j]=false;
                }
            }
        }
        
        long sum=0;
        for(int i=2;i<=n;i++){
            if(primes[i]){
                sum=sum+i;
            }
        }
        
        return sum;
    }
}
```
