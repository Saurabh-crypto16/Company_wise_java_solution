```java
class Solution
{
    //Function to return the name of candidate that received maximum votes.
    public static String[] winner(String arr[], int n)
    {
        HashMap <String,Integer> hm = new HashMap<>();
        for(String i : arr){
           hm.put(i,hm.getOrDefault(i,0)+1); // the number of votes for the candidates
        }
       
        int max=0;
        String name="";
        String ans[] = new String[2];
        for(Map.Entry<String, Integer> items: hm.entrySet()){
            if(items.getValue()>max){
               max = items.getValue();
               name=items.getKey();
            }
            if(max == items.getValue()){
                if(name.compareTo(items.getKey())>0){
                   name=items.getKey();
                }
            }
        }
        ans[0] = name;
        ans[1] = Integer.toString(max);
        
        return ans;
    }
}


```
