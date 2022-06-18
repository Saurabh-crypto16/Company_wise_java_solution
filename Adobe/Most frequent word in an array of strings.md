```java
class Solution
{
    //Function to find most frequent word in an array of strings.
    public String mostFrequentWord(String arr[],int n)
    {
        HashMap<String,Integer> map=new HashMap<>();
        
        for(String s: arr){
            map.put(s,map.getOrDefault(s,0)+1);
        }
        
        int max=0;
        String ans="";
        for(String s: arr){
            if(map.get(s)>=max){
                max=map.get(s);
                ans=s;
                map.put(s,0);
            }
        }
        
        return ans;
    }

}

```
