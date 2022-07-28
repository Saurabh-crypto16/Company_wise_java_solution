```java
class Pair{
    int val;
    int idx;
    Pair(int val,int idx){
        this.val=val;
        this.idx=idx;
    }
}

class Solution
{
    //Function to find the minimum number of swaps required to sort the array.
    public int minSwaps(int nums[])
    {
        Pair[] p=new Pair[nums.length];
        int swaps=0;
        
        for(int i=0;i<nums.length;i++){
            p[i]=new Pair(nums[i],i);
        }
        
        Arrays.sort(p,(p1,p2)->p1.val-p2.val);
        
        int ans=0;
        boolean vis[]=new boolean[nums.length];
        for(int i=0;i<nums.length;i++){
            if(vis[i] || p[i].idx==i){
                continue;
            }
            
            int cycle_len=0,j=i;
            while(!vis[j]){
                vis[j]=true;
                cycle_len++;
                j=p[j].idx;
            }
            
            ans+=(cycle_len-1);
        }
        
        return ans;
    }
}
```
