```java
class Solution{
    public boolean isWordExist(char[][] board, String word){
        for(int i=0;i<board.length;i++){
            for(int j=0;j<board[0].length;j++){
                if(board[i][j]==word.charAt(0) && dfs(i,j,board,word,0)){
                    return true;
                }
            }
        }
        
        return false;
    }
    public boolean dfs(int i,int j,char[][] board,String word,int cnt){
        if(cnt==word.length()){
            return true;
        }
        
        if(i<0 || i>=board.length || j<0 || j>=board[0].length || 
            board[i][j]!=word.charAt(cnt)){
            return false;
        }
        
        char curr_char=board[i][j];
        board[i][j]=' ';
        
        boolean ans=dfs(i-1,j,board,word,cnt+1) ||
                    dfs(i+1,j,board,word,cnt+1) ||
                    dfs(i,j-1,board,word,cnt+1) ||
                    dfs(i,j+1,board,word,cnt+1);
                    
        board[i][j]=curr_char;
        return ans;
    }
}
```
