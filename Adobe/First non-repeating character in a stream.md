```java
class Solution
{
    public String FirstNonRepeating(String A)
    {
        Queue<Character> q=new LinkedList<>();
        int freq[]=new int[26];
        String ans="";
        
        for(char c: A.toCharArray()){
            q.offer(c);
            freq[c-'a']++;
            
            //keep poping elements from q until the curr element's freq if > 1
            while(!q.isEmpty() && freq[q.peek()-'a']!=1){
                q.poll();
            }
            
            if(!q.isEmpty()) ans+=String.valueOf(q.peek());
            else    ans+="#";
        }
        
        return ans;
    }
}
```
