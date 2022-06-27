```java
class Solution {
    int find(char[] b,char a) //check all possible conditions
    {
        int cnt=0;
        if(b[0]==b[1] && b[1]==b[2] && b[0]==a) cnt++;  //1st row
        if(b[3]==b[4] && b[4]==b[5] && b[3]==a) cnt++;  //2nd row
        if(b[6]==b[7] && b[7]==b[8] && b[6]==a) cnt++;  //3rd row
        
        if(b[0]==b[3] && b[3]==b[6] && b[0]==a) cnt++;  //1st col
        if(b[1]==b[4] && b[4]==b[7] && b[1]==a) cnt++;  //2nd col
        if(b[2]==b[5] && b[5]==b[8] && b[2]==a) cnt++;  //3rd col
        
        if(b[0]==b[4] && b[4]==b[8] && b[0]==a) cnt++;  //primary diag
        if(b[2]==b[4] && b[4]==b[6] && b[2]==a) cnt++;  //secondry diag
        
        return cnt;
    }
    boolean isValid(char[] b) {
        // code here
        int co=0,cx=0;
        for(int i=0;i<b.length;i++)
        {
            if(b[i]=='O') co++;
            else cx++;
        }
        
        if(cx>co && (cx-co)==1){ //for a board to be valid as x plays first
            int x=find(b,'X');
            int y=find(b,'O');
            if(x>0 && y>0) return false; //both can't be the winners
            
            if(y>0 && cx!=co) return false; //if second one is the winner then cx==co
            
            return true;
        }else return false;
    }
}
```
