```java
class Solution {
    //check every even position element with its neighbors
    //if it is not greater than both neighbors then swap
    void zigZag(int arr[], int n) {
        for(int i=1;i<n;i+=2){
            if(arr[i]<arr[i-1]) swap(arr,i,i-1);
            if(i+1<n && arr[i]<arr[i+1]) swap(arr,i,i+1);
        }
    }
    void swap(int arr[],int i,int j){
        int temp=arr[i];
        arr[i]=arr[j];
        arr[j]=temp;
    }
}
```
