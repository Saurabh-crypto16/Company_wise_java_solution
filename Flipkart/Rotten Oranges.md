```java
class Solution
{
    //Function to find minimum time required to rot all oranges. 
    public int orangesRotting(int[][] grid)
    {
        if(grid==null || grid.length==0) return 0;
        int rows=grid.length;
        int cols= grid[0].length;
        Queue<int[]> queue = new LinkedList<>();
        int count_fresh=0;
       
        //put the position of all rotten oranges in the queue
        //count the no. of fresh oranges
        for(int i=0;i<rows;i++){
            for(int j=0;j<cols;j++){
                if(grid[i][j]==2){//rotten orange
                    queue.offer(new int[]{i,j});
                }
                if(grid[i][j]!=0){
                    count_fresh++;
                }
            }
        }
        
        if(count_fresh==0) return 0; //all oranges already rotten
        int countMin=0,cnt=0;
        int dx[] = {0,0,1,-1}; //x axis directions
        int dy[] = {1,-1,0,0}; //y axis directions
        
        //bfs starting from initially rotten oranges in queue
        while(!queue.isEmpty()){
            int size=queue.size();
            cnt+=size;
            for(int i=0;i<size;i++){
                int[] point=queue.poll();
                for(int j=0;j<4;j++){
                    int x = point[0]+dx[j];//j goes in all the four directions
                    int y = point[1]+dy[j];
                    //if any of below condn we dont have to do anything
                    if(x<0 || y<0 ||x>=rows || y>=cols || grid[x][y]==0 || grid[x][y]==2) continue;
                    grid[x][y]=2;
                    queue.offer(new int[]{x,y});
                }
            }
            if(queue.size()!=0){
               countMin++;
            }
        }
        return count_fresh==cnt?countMin:-1;
    }
}
```
