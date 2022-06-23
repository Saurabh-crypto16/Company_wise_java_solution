```java
class Pair implements Comparable<Pair>{
    int s,e;
    Pair(int s,int e){
        this.s=s;
        this.e=e;
    }
    
    @Override
    public int compareTo(Pair p){
        return this.e-p.e;
    }
}
class Solution
{
    //Function to find the maximum number of activities that can
    //be performed by a single person.
    public static int activitySelection(int start[], int end[], int n)
    {
        Pair act[]=new Pair[n];
        for(int i=0;i<n;i++){
            act[i]=new Pair(start[i],end[i]);
        }
        
        Arrays.sort(act);
        
        int last_meet_end_time=0,ans=0;
        for(Pair curr: act){
            if(curr.s>last_meet_end_time){
                ans++;
                last_meet_end_time=curr.e;
            }
        }
        
        return ans;
    }
}
```
