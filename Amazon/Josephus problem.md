```java
class Solution
{
   public int josephus(int n, int k)
    {
        if(n==1)    return 1;
        
        int r=(josephus(n-1,k)+k)%n;
        
        return r==0 ? n : r;
    }

}


```
