```java
class Solution
{
    public String[] wordBoggle(char board[][], String[] dictionary)
    {
        ArrayList<String> words=new ArrayList<>();
        
        for(String d: dictionary){
            for(int i=0;i<board.length;i++){
                for(int j=0;j<board[0].length;j++){
                    if(board[i][j]==d.charAt(0) && dfs(board,i,j,0,d) && !words.contains(d)){
                        words.add(d);
                    }
                }
            }
        }
        
        String []dsf = new String[words.size()];
        words.toArray(dsf);
        return dsf;
    }
    public boolean dfs(char[][] board,int i,int j,int cnt,String word){
        if(cnt==word.length())  return true;
        
        if(i<0 || i>=board.length || j<0 || j>=board[0].length || 
            board[i][j]!=word.charAt(cnt)){
            return false;        
        }
        
        char temp=board[i][j];
        board[i][j]='$';
        boolean found = dfs(board,i+1,j,cnt+1,word) ||
            dfs(board,i-1,j,cnt+1,word) ||
            dfs(board,i,j-1,cnt+1,word) ||
            dfs(board,i,j+1,cnt+1,word) ||
            dfs(board,i-1,j-1,cnt+1,word) ||
            dfs(board,i+1,j-1,cnt+1,word) ||
            dfs(board,i-1,j+1,cnt+1,word) ||
            dfs(board,i+1,j+1,cnt+1,word);
        board[i][j]=temp;
        
        return found;
    }
}
```
