```java
class Solution {
    void pushZerosToEnd(int[] arr, int n) {
        if(n==0 || n==1)    return;
        
        //left should point to the first 0 from left dir
        //right will swap the non zero along right dir
        int left=0,right=0;
        while(right<n){
            if(arr[right]==0)  right++;
            else{
                swap(arr,left,right);
                left++;
                right++;
            }
        }
    }
    public void swap(int arr[],int i,int j){
        int temp=arr[i];
        arr[i]=arr[j];
        arr[j]=temp;
    }
}
```
