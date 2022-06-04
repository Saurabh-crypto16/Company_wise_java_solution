```java
class Solution{
    //Function to find the minimum number of platforms required at the
    //railway station such that no train waits.
    static int findPlatform(int arr[], int dep[], int n){
        int i=0,j=0,maxPlatforms=0,maxTrains=0;
        Arrays.sort(arr);
        Arrays.sort(dep);
        
        while(i<n && j<n){
            if(arr[i]<=dep[j]){
                maxTrains++;
                i++;
            }else{
                maxTrains--;
                j++;
            }
            
            maxPlatforms=Math.max(maxPlatforms,maxTrains);
        }
        
        return maxPlatforms;
    }
}
```
