```java

class Solution
{
    //Function to rotate an array by d elements in counter-clockwise direction. 
    static void rotateArr(int arr[], int d, int n)
    {
        if(d>n){
            d-=n;
        }
        reverse(arr,0,d-1);
        reverse(arr,d,n-1);
        reverse(arr,0,n-1);
    }
    static void reverse(int arr[],int l,int r){
        while(l<r){
            int temp=arr[l];
            arr[l++]=arr[r];
            arr[r--]=temp;
        }
    }
}
```
