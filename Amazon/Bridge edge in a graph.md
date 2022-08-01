```java
class Solution
{
    private static int time = 0;
    
    static int isBridge(int V, ArrayList<ArrayList<Integer>> adj,int c,int d)
    {
        // code here
        boolean vis[] = new boolean [V];
        int disc[] = new int[V];
        int low[] = new int[V];
        
        int parent[] = new int[V];
        
        for(int i=0; i<V; i++){
            if(!vis[i]){
                bridgeUtil(i, adj, disc, low, parent, vis);
            }
        }
        
        if(low[d] > disc[c] || low[c] > disc[d]){
            return 1;
        }
        
        return 0;
    }
    
    private static void bridgeUtil(int u, ArrayList<ArrayList<Integer>> adj,int []disc,
                    int []low, int []parent, boolean vis[]){
        vis[u] = true;
        
        disc[u] = low[u] = time++;
        
        for(int v : adj.get(u)){
            if(!vis[v]){
                parent[v] = u;
                bridgeUtil(v, adj, disc, low, parent, vis);
                low[u] = Math.min(low[v], low[u]); 
            }
            else if(v != parent[u]){
                low[u] = Math.min(low[u], low[v]);
            }
        }
    }
}
```
