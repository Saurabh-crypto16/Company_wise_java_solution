```java
class Solution
{
    public int minStepToReachTarget(int start[], int end[], int N)
    {
        int dirs[][]={{-2,-1},{-2,1},{-1,2},{1,2},{2,1},{2,-1},{1,-2},{-1,-2}};
        Queue<int[]> q=new LinkedList<>();
        int ans=0;
        q.offer(new int[]{start[0],start[1]});
        boolean vis[][]=new boolean[N+1][N+1];
        vis[start[0]][start[1]]=true;
        
        while(!q.isEmpty()){
            int size=q.size();
            while(size-->0){
                int curr[]=q.poll();
            
                if(curr[0]==end[0] && curr[1]==end[1])  return ans;
                
                for(int dir[]: dirs){
                    int new_pos[]=new int[2];
                    new_pos[0]=curr[0]+dir[0];
                    new_pos[1]=curr[1]+dir[1];
                    
                    if(new_pos[0]<1 || new_pos[0]>N || new_pos[1]<1 || new_pos[1]>N ||
                        vis[new_pos[0]][new_pos[1]])
                        continue;
                    else{
                        q.offer(new_pos);
                        vis[new_pos[0]][new_pos[1]]=true;
                    }
                }
            }
            ans++;
        }
        
        return -1;
    }
}
```
