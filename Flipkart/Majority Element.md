```java
class Solution
{
    static int majorityElement(int a[], int size)
    {
        int cnt=0,ans=-1;
        
        for(int i: a){
            if(i==ans){
                cnt++;
            }else if(cnt==0){
                ans=i;
                cnt++;
            }else{
                cnt--;
            }
        }
        
        cnt=0;
        for(int i: a){
            if(i==ans)  cnt++;
        }
        
        return cnt>size/2 ? ans : -1;
    }
}
```
