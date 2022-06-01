```java
class Solution
{
    public String isCircular(String s)
    {
        int x=0,y=0;
        int dir=0;
        //dir=0 => north
        //dir=1 => east
        //dir=2 => south
        //dir=3 => west
        
        for(char ch: s.toCharArray()){
            if(ch=='G'){
                if(dir==0)  y++;
                else if(dir==1) x++;
                else if(dir==2) y--;
                else x--;
            }else if(ch=='L'){
                dir=(4+(dir-1))%4;
            }else if(ch=='R'){
                dir=(dir+1)%4;
            }
        }
        
        return x==0 && y==0 ? "Circular" : "Not Circular";
    }
}
```
