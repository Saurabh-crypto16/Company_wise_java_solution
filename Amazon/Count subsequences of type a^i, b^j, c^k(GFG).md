```java
/*
when we get 'a' make a_cnt=2*a_cnt+1;
when we get 'b' make ab_cnt=2*ab_cnt+a_cnt;
when we get 'c' make abc_cnt=2*abc_cnt+ab_cnt;
return abc_cnt
*/

class Solution{
    public int fun(String s){
        int a_cnt=0,ab_cnt=0,abc_cnt=0,mod=(int)1e9+7;
        
        for(char ch: s.toCharArray()){
            if(ch=='a'){
                a_cnt=(2*a_cnt)%mod+1;
            }else if(ch=='b'){
                ab_cnt=(((2*ab_cnt)%mod)+(a_cnt%mod))%mod;
            }else if(ch=='c'){
                abc_cnt=(((2*abc_cnt)%mod)+(ab_cnt%mod))%mod;
            }
        }
        
        return abc_cnt%mod;
    }
}
```
