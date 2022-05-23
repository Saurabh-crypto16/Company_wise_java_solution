```java
class Solution{
    static int R, C;
    static int[] x = { -1, -1, -1, 0, 0, 1, 1, 1 };
    static int[] y = { -1, 0, 1, -1, 1, -1, 0, 1 };

    static boolean search2D(char[][] grid, int row,int col, String word)
    {
        if (grid[row][col] != word.charAt(0))   return false;
 
        int len = word.length();

        for (int dir = 0; dir < 8; dir++) {
            int k, rd = row + x[dir], cd = col + y[dir];

            for (k = 1; k < len; k++) {
                // If out of bound break
                if (rd >= R || rd < 0 || cd >= C || cd < 0)
                    break;
 
                // If not matched, break
                if (grid[rd][cd] != word.charAt(k))
                    break;
 
                // Moving in particular direction
                rd += x[dir];
                cd += y[dir];
            }
 
            if (k == len)   return true;
        }
        return false;
    }
    
    public int[][] searchWord(char[][] grid, String word){
        ArrayList<int[]> ans=new ArrayList<>();
        R=grid.length;
        C=grid[0].length;
        
        for (int row = 0; row < R; row++) {
            for (int col = 0; col < C; col++) {
                if (grid[row][col]==word.charAt(0)  && search2D(grid, row, col, word))
                    ans.add(new int[]{row,col});
            }
        }
        
        int res[][]=new int[ans.size()][2];
        for(int i=0;i<ans.size();i++){
            res[i][0]=ans.get(i)[0];
            res[i][1]=ans.get(i)[1];
        }
        
        return res;
    }
}
```
