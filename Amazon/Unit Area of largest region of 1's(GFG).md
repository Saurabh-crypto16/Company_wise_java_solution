```java
class Solution{
    //Function to find unit area of the largest region of 1s.
    public int findMaxArea(int[][] grid){
        int ans=0;
        int n=grid.length,m=grid[0].length;
        for(int i=0;i<n;i++){
            for(int j=0;j<m;j++){
                if(grid[i][j]==1){
                    ans=Math.max(ans,solve(i,j,n,m,grid));
                }
            }
        }
        
        return ans;
    }
    public static int solve(int i,int j,int n,int m,int[][] grid){
        if(i<0 || i>=n || j<0 || j>=m || grid[i][j]==0){
            return 0;
        }
        
        grid[i][j]=0;
        int ans=0;
        for(int x=-1;x<=1;x++){
            for(int y=-1;y<=1;y++){
                ans+=solve(i+x,j+y,n,m,grid);
            }
        }
        
        return 1+ans;
    }
}
```
