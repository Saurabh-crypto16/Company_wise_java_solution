```java
class Solution {
    boolean checkTriplet(int[] arr, int n) {
        for(int i=0;i<n;i++)    arr[i]*=arr[i];
        Arrays.sort(arr);
        
        for(int i=n-1;i>=2;i--){
            int l=0,r=i-1;
            
            while(l<r){
                if(arr[l]+arr[r]==arr[i])   return true;
                
                if(arr[l]+arr[r]<arr[i]){
                    l++;
                }else{
                    r--;
                }
            }
        }
        
        return false;
    }
}
```
