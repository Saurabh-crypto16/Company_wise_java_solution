```java
class Solution {
    String printLargest(String[] arr) {
        Arrays.sort(arr,(a,b) -> {
            double n1=Double.parseDouble(a+b);  
            double n2=Double.parseDouble(b+a);
            
            if(n1>n2)   return 1;   //keep a after b
            else if(n2>n1)  return -1;  //keep b after a
            return 0;
        });
        
        String ans="";
        for(String s: arr)  {ans=s+ans;}
        
        return ans;
    }
}
```
