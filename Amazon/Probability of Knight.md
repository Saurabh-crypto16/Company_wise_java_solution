```java
class Solution
{
    public double findProb(int N, int start_x, int start_y, int steps)
    {
        double curr[][]=new double[N][N];
        double next[][]=new double[N][N];
        int dirs[][]={{-2,-1},{-1,-2},{1,-2},{2,-1},{2,1},{1,2},{-1,2},{-2,1}};
        
        curr[start_x][start_y]=1;
        
        for(int step=1;step<=steps;step++){
            for(int i=0;i<N;i++){
                for(int j=0;j<N;j++){
                    for(int dir[]: dirs){
                        int new_i=i+dir[0];
                        int new_j=j+dir[1];
                        
                        if(new_i>=0 && new_i<N && new_j>=0 && new_j<N){
                            next[new_i][new_j]+=(curr[i][j]/8.0);
                        }
                    }
                }
            }
            
            curr=next;
            next=new double[N][N];
        }
        
        double sum=0.0;
        for(int i=0;i<N;i++){
            for(int j=0;j<N;j++){
                sum+=curr[i][j];
            }
        }
        
        return sum;
    }
}
```
