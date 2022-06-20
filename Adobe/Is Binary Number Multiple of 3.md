```java
//eg let number be abcde then if (a+b+c)-(b+d) is divisibe by 3 then abcde is divisibe be 3 
class Solution {
    int isDivisible(String s) {
        int odd=0;
        int even=0;
        
        for(int i=0;i<s.length();i++){
            if(i%2==0){
                even+=(s.charAt(i)-'0');
            }else{
                odd+=(s.charAt(i)-'0');
            }
        }
        
        return (even-odd)%3==0 ? 1 : 0;
    }
}
```
