```java
class Solution
{
    //Function to rotate matrix anticlockwise by 90 degrees.
    static void rotateby90(int matrix[][], int n){ 
        //reverse each row
        for(int i=0;i<n;i++){
            int start=0,end=n-1;
            while(start<end){
                int temp=matrix[i][start];
                matrix[i][start++]=matrix[i][end];
                matrix[i][end--]=temp;
            }
        }
        
        //transpose
        for(int i=0;i<n;i++){
            for(int j=i;j<n;j++){
                int temp=matrix[i][j];
                matrix[i][j]=matrix[j][i];
                matrix[j][i]=temp;
            }
        }
    }
}
```
