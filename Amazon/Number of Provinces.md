```java
class Solution {
    static int numProvinces(ArrayList<ArrayList<Integer>> adj, int V) {
        int cnt=0;
        boolean vis[]=new boolean[V+1];
        
        for(int i=1;i<=V;i++){
            if(!vis[i]){
                cnt++;
                dfs(i,vis,adj);
            }
        }
        
        return cnt;
    }
    static  void dfs(int node,boolean []visited,ArrayList<ArrayList<Integer>> adj){
        visited[node]=true;
        
        for(int i=0;i<adj.get(node-1).size();i++){
           if(adj.get(node-1).get(i)==1 && !visited[i+1]){
                dfs(i+1,visited,adj);
           }
        }
        return;
    }
};
```
