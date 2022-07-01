```java
class Solution{
    //Function to count the frequency of all elements from 1 to N in the array.
    public static void frequencyCount(int arr[], int n, int p)
    {
        //converting value to 0 based indexing
        for(int i=0;i<n;i++)    arr[i]-=1;
        
        // step 2 : We increase the element at index "i" by "p" after every visit
        // After 1st itration -> arr[] = {1,2+n,1,2,4}
        // After 2nd itration -> arr[] = {1,7,6,2,4}
        // After 3rd itration -> arr[] = {6,12,6,2,4}
        // After 4th itration -> arr[] = {6,12,11,2,4}
        // After 5th itration -> arr[] = {6,12,11,2,9}
        
        // calculation : int num = arr[i] % n
        // arr[num] = arr[num] + n;
        for(int i=0;i<n;i++){
            if(arr[i] % p < n){
                int num = arr[i] % p;
                arr[num] = arr[num] + p;
            }
           
        }
        
        // Step 3 : converting back to previous array
        // arr[] = {6,12,6,3,4}
        // int count = arr[i] / n
        // To set back array to original form follow the below step. But in quesn not required
        // int num = arr[i] % n + 1;
        for(int i=0;i<n;i++)    arr[i]/=p;
    }
}

```
