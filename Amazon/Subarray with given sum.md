```java
class Solution
{
    //Function to find a continuous sub-array which adds up to a given number.
    static ArrayList<Integer> subarraySum(int[] arr, int n, int s) 
    {
        ArrayList<Integer> ans=new ArrayList<Integer>();
        HashMap<Integer,Integer> map=new HashMap<>();
        
        int sum=0;
        for(int i=0;i<n;i++){
            sum+=arr[i];
            map.put(sum,i);
            
            if(sum<s)   continue;
            else if(sum==s){
                ans.add(1);
                ans.add(i+1);
                return ans;
            }
            else if(map.containsKey(sum-s)){
                ans.add(map.get(sum-s)+2);
                ans.add(i+1);
                return ans;
            }
        }
        
        ans.add(-1);
        return ans; 
    }
}
```
