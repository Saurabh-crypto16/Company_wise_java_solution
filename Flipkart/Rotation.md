```java
class Solution {
    int findKRotation(int arr[], int n) {
        int left=0,right=n-1;
        
        while(left<right){
            int mid=left+(right-left)/2;
            
            if(arr[mid]>arr[right]){
                left=mid+1;
            }else{
                right=mid;
            }
        }
        
        return left;
    }
}
```
