```java
class GfG {
    int transitionPoint(int arr[], int n) {
        int left=0,right=n-1;
        
        while(left<right){
            int mid=left+(right-left)/2;
            
            if(arr[mid]==0){
                left=mid+1;
            }else{
                right=mid;
            }
        }
        
        return arr[left]==0 ? -1 : left;
    }
}
```
