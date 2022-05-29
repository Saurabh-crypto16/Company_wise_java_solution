```java
class Compute {
    public long[] minAnd2ndMin(long a[], long n){
        long smallest=Long.MAX_VALUE,secondsmallest=Long.MAX_VALUE;
        
        for(long i: a){
            if(i<smallest) {
                secondsmallest=smallest;
                smallest=i;
            }
            else if(i<secondsmallest && i!=smallest) secondsmallest=i;
        }
        
        long ans[]=new long[]{-1L,-1L};
        if(secondsmallest!=Long.MAX_VALUE){
            ans[0]=smallest;
            ans[1]=secondsmallest;
        }
        
        //ystem.out.println(smallest+" "+secondsmallest);
        
        return ans;
    }
}

```
