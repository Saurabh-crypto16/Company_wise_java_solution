```java
class Solution
{
    public String findOrder(String [] dict, int N, int K)
    {
        // Write your code here
        Map<Character,Character> g=new HashMap<Character,Character>();
        for(int i=0;i<N-1;i++){
            for(int j=0;j<Math.min(dict[i].length(),dict[i+1].length());j++){
                if(dict[i].charAt(j)!=dict[i+1].charAt(j)){
                    //it means that dict[i].charAt(j) comes before dict[i+1].charAt(j)
                    //in alien dict
                    g.put(dict[i].charAt(j), dict[i+1].charAt(j));
                    break;
                }
            }
        }
        
        //Applying Topo sort
        Stack<Character> st=new Stack<Character>();
        Set<Character> vis=new HashSet<Character>();
        for(int i=65;i<65+K;i++){
            if(!vis.contains((char)i)){
                topoSort((char)i,vis,g,st);
            }
        }
        
        String ans="";
        while(!st.isEmpty()){
            ans+=st.pop();
        }
        
        return ans;
    }
    void topoSort(char i, Set<Character> vis, Map<Character,Character> g, Stack<Character> st){
        vis.add(i);
        if(!vis.contains(g.get(i)) && g.get(i)!=null){
            topoSort(g.get(i),vis,g,st);
        }
        st.push(i);
    }
}
```
