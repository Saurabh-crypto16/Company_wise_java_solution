```java
class Solution{
    //Function to return a list containing the union of the two arrays.
    public static ArrayList<Integer> findUnion(int arr1[], int arr2[], int n, int m){
        TreeSet<Integer> ans=new TreeSet<Integer>();
        
        for(int a: arr1)    if(!ans.contains(a))    ans.add(a);
        for(int a: arr2)    if(!ans.contains(a))    ans.add(a);
        
        return new ArrayList<>(ans);
    }
}


```
