```java
class Solution
{
    //Function to find the smallest window in the string s consisting
    //of all the characters of string p.
    public static String smallestWindow(String s, String p)
    {
        String ans="";
        HashMap<Character,Integer> map1=new HashMap<>();
        HashMap<Character,Integer> map2=new HashMap<>();
        for(char ch: p.toCharArray()){
            map2.put(ch,map2.getOrDefault(ch,0)+1);
        }
        
        int match_cnt=0,desired_mcnt=p.length();
        int i=-1,j=-1;
        
        while(true){
            boolean f1=false,f2=false;
            
            //acquire
            while(i<s.length()-1 && match_cnt<desired_mcnt){
                i++;
                map1.put(s.charAt(i),map1.getOrDefault(s.charAt(i),0)+1);
                
                if(map1.getOrDefault(s.charAt(i),0)<=map2.getOrDefault(s.charAt(i),0)){
                    match_cnt++;
                }
                
                f1=true;
            }
            
            //collect ans and release
            while(j<i && match_cnt==desired_mcnt){
                String potential_ans=s.substring(j+1,i+1);
                if(ans.length()==0 || potential_ans.length()<ans.length()){
                    ans=potential_ans;
                }
                
                j++;
                char ch=s.charAt(j);
                if(map1.get(ch)==1){
                    map1.remove(ch);
                }else{
                    map1.put(ch,map1.get(ch)-1);
                }
                
                if(map1.getOrDefault(ch,0)<map2.getOrDefault(ch,0)){
                    match_cnt--;
                }
                
                f2=true;
            }
            
            if(!f1 && !f2)  break;
        }
        
        return ans.length()>0 ? ans : "-1";
    }
}
```
