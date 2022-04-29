```java
//Solution 1 - Using reverse inorder traversal
/*
	Time Complexity : O(N)
	Space Complexity : O(N)

	Where 'N' is the number of nodes in the given binary search tree.
*/

class Solution {
	static int sum = 0;

	private static void applyReverseInOrder(TreeNode<Integer> root) {
		if (root == null) return;

		applyReverseInOrder(root.right);  // Go to the right subtree.

		int rootVal = root.val; // Store value of the root node.

		//Replace the value at root node with the sum of all the nodes which have value greater than the root.val.
		root.val = sum;

		sum = sum + rootVal;  // Store the sum.

		applyReverseInOrder(root.left); // Go to the left sub tree.
	}
	public static TreeNode<Integer> convertBstToGreaterSum(TreeNode<Integer> root) {
		// Apply reverse inorder.
		sum = 0;
		applyReverseInOrder(root);
		return root;
	}

}

//Solution 2
import java.util.*;
class Solution{
	public static TreeNode<Integer> convertBstToGreaterSum(TreeNode<Integer> root)
	{
		Map<Integer,Integer> pSum=new HashMap<>();
		ArrayList<Integer> ele=new ArrayList<>();
		ArrayList<Integer> ps=new ArrayList<>();
		inOrder(root,ele);
		
		for(int i=ele.size()-1;i>=0;i--){
			if(i==ele.size()-1){
				ps.add(0);
			}else{
				ps.add(0,ps.get(0)+ele.get(i+1));
			}
			pSum.put(ele.get(i),ps.get(0));
		}
		
		transformTree(root,pSum);
		return root;
	}
	public static void inOrder(TreeNode<Integer> root,ArrayList<Integer> ele){
		if(root==null){
			return;
		}
		
		inOrder(root.left,ele);
		ele.add(root.val);
		inOrder(root.right,ele);
	}
	public static void transformTree(TreeNode<Integer> root,Map<Integer,Integer> pSum){
		if(root==null){
			return;
		}
		
		transformTree(root.left,pSum);
		root.val=pSum.get(root.val);
		transformTree(root.right,pSum);
	}
}
```
