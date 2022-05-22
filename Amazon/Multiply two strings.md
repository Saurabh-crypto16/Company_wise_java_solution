```java
/*
using naive multiplication algo
    3 3
  * 2 2
    ----
    6 6
+ 6 6
---------
  7 2 6
*/

class Solution{
    public String multiplyStrings(String s1,String s2){
        int sign1=0,sign2=0;
        if(s1.charAt(0)=='-')  {
            sign1=1;
            s1=s1.substring(1);
        }
        if(s2.charAt(0)=='-')  {
            sign2=1;
            s2=s2.substring(1);
        }
        
        int m=s1.length(),n=s2.length();
        int vals[]=new int[m+n];
        
        for(int i=m-1;i>=0;i--){
            for(int j=n-1;j>=0;j--){
                int mul=(s1.charAt(i)-'0')*(s2.charAt(j)-'0');
                int sum=vals[i+j+1]+mul;
                vals[i+j]+=sum/10;
                vals[i+j+1]=sum%10;
            }
        }
        
        StringBuilder sb=new StringBuilder();
        for(int val: vals){
            if(sb.length()>0 || val!=0){
                sb.append(val);
            }
        }
        
        if((sign1==1 && sign2==0) || (sign1==0 && sign2==1)){
           if(sb.length()>0)    sb.insert(0,"-"); 
        }
        
        return sb.length()>0 ? sb.toString() : "0";
    }
}
```
