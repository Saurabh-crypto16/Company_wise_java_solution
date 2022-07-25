```java
class CompareByFirst implements Comparator<Pair>
{
   public int compare(Pair a, Pair b)
    {
        return a.x - b.x;
    }
}

class GfG
{
    int maxChainLength(Pair arr[], int n)
    {
       int dp[]=new int[n],ans=1;
       Arrays.fill(dp,1);
       Arrays.sort(arr,new CompareByFirst());
       
       for(int i=0;i<n;i++){
           for(int j=0;j<i;j++){
               if(arr[j].y<arr[i].x){
                   dp[i]=Math.max(dp[i],dp[j]+1);
               }
           }
           ans=Math.max(ans,dp[i]);
       }
       
       return ans;
    }
}
```
