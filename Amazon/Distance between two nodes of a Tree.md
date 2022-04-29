```java
public class Solution
{
	public static TreeNode LCA(TreeNode root,int node1,int node2){
		if(root==null || root.val==node1 || root.val==node2)
			return root;
		
		TreeNode left=LCA(root.left,node1,node2);
		TreeNode right=LCA(root.right,node1,node2);
		
		if(left==null)	return right;
		else if(right==null)	return left;
		else return root;
	}
	public static int distance(TreeNode root, int node, int dist){
		if(root==null)	return -1;
		
		if(root.val==node){
			return dist;
		}
		
		int left=distance(root.left,node,dist+1);
		if(left!=-1)	return left;
		
		int right=distance(root.right,node,dist+1);
		return right;
	}
	public static int findDistanceBetweenNodes(TreeNode root, int node1, int node2){
		TreeNode lca=LCA(root,node1,node2);
		
		int d1=distance(lca,node1,0);
		int d2=distance(lca,node2,0);
		
		return (d1==-1 || d2==-1) ? -1 : d1+d2;
	}
}
```
