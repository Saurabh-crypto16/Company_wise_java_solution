```java

class Solution
{
    //Function to find the number of 'X' total shapes.
    public int xShape(char[][] grid)
    {
        int cnt=0;
        
        for(int i=0;i<grid.length;i++){
            for(int j=0;j<grid[0].length;j++){
                if(grid[i][j]=='X'){
                    cnt++;
                    dfs(i,j,grid);
                }
            }
        }
        
        return cnt;
    }
    public void dfs(int i,int j,char[][] grid){
        if(i<0 || i>=grid.length || j<0 || j>=grid[0].length || grid[i][j]=='O'){
            return;
        }
        
        grid[i][j]='O';
        dfs(i+1,j,grid);
        dfs(i-1,j,grid);
        dfs(i,j-1,grid);
        dfs(i,j+1,grid);
    }
}
```
