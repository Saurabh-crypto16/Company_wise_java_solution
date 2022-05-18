```java
class Solution {
    int rowWithMax1s(int arr[][], int n, int m) {
        int ans_row=0,max_one_cnt=0;
        boolean flag=false;
        
        for(int i=0;i<n;i++){
            for(int j=0;j<m;j++){
                if(arr[i][j]==1){
                    flag=true;
                    int curr_one_cnt=m-j;
                    if(curr_one_cnt>max_one_cnt)    {
                        ans_row=i;
                        max_one_cnt=curr_one_cnt;
                    }
                    break;
                }
            }
        }
        
        return flag ? ans_row : -1 ;
    }
}
```
