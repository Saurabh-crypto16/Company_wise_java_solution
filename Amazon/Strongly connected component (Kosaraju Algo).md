```java
class Solution
{
    public void topo_dfs(int node,Stack<Integer> st,boolean vis[],
            ArrayList<ArrayList<Integer>> adj){
        vis[node]=true;
        
        for(int it: adj.get(node)){
            if(!vis[it]) topo_dfs(it,st,vis,adj);
        }
        
        st.push(node);
    }
    public void dfs(int node,TreeSet<Integer> list,boolean vis[],
            ArrayList<ArrayList<Integer>> adj){
        vis[node]=true;
        list.add(node);
        
        for(int it: adj.get(node)){
            if(!vis[it]) {
                dfs(it,list,vis,adj);
            }
        }
    }
    //Function to return a list of lists of integers denoting the members 
    //of strongly connected components in the given graph.  
    public ArrayList<ArrayList<Integer>> tarjans(int V, ArrayList<ArrayList<Integer>> adj) 
    {
        ArrayList<ArrayList<Integer>> ans=new ArrayList<>();
        PriorityQueue<ArrayList<Integer>> pq = new PriorityQueue<>(
                (a,b)-> a.get(0) - b.get(0));
        Stack<Integer> st=new Stack<>();
        boolean vis[]=new boolean[V];
        
        for(int i=0;i<V;i++){
            if(!vis[i]){
                topo_dfs(i,st,vis,adj);
            }
        }
        
        ArrayList<ArrayList<Integer>> transpose=new ArrayList<>();
        for(int i=0;i<V;i++)    transpose.add(new ArrayList<Integer>());        
        
        Arrays.fill(vis,false);
        for(int i=0;i<V;i++){
            for(int it: adj.get(i)){
                transpose.get(it).add(i);
            }
        }
        
        while(!st.isEmpty()){
            int i=st.pop();
            
            if(!vis[i]){
                TreeSet<Integer> list=new TreeSet<>();
                dfs(i,list,vis,transpose);
                pq.offer(new ArrayList(list));
            }
        }
        
        while(!pq.isEmpty()) ans.add(pq.remove());
        return ans;
    }
}
```
