```java
class Solution{
    //Function to count the number of possible triangles.
    static int findNumberOfTriangles(int arr[], int n){
        Arrays.sort(arr);
        
        int count=0;
        for(int i=n-1;i>=2;i--){
            int left=0,right=i-1;
            while(left<=right){
                int sum=arr[left]+arr[right];
                
                //for triangle sum of any 2 sides should be greater than 3rd side
                //since array is sorted ascending order then 
                //if sum of less 2 sides > larger side then for all combination of those sides it will be true
                if(arr[i]<sum)  {
                    count+=(right-left);
                    right--;
                }else {
                    left++;
                }
            }
        }
        
        return count;
    }
}
```
