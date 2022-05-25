```java
class Solution {
    void rotateRight(int arr[],int from,int to){
        int temp=arr[to];
        for(int i=to;i>from;i--){
            arr[i]=arr[i-1];
        }
        arr[from]=temp;
    }
    void rearrange(int arr[], int n) {
        int wrongIdx=-1;
        
        for(int i=0;i<n;i++){
            if(wrongIdx!=-1){
                if((arr[wrongIdx]>=0 && arr[i]<0) || (arr[wrongIdx]<0 && arr[i]>=0)){
                    rotateRight(arr,wrongIdx,i);
                    
                    //if more than 2 elements are rotated then there will be a wrongidx
                    //between them
                    if(i-wrongIdx>=2)   wrongIdx+=2;
                    else    wrongIdx=-1;
                }
            }else{
                if((arr[i]<0 && i%2==0) || (arr[i]>=0 && i%2==1)){
                    wrongIdx=i;
                }
            }
        }
    }
}
```
