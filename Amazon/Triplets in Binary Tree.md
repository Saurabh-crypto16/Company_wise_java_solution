```java
/*

    Time complexity: O(N)
    Space complexity: O(N)

    where 'N' is the number of nodes in the binary tree.

*/

import java.util.List;
import java.util.ArrayList;

public class Solution {

	private static void fillTriplets(List<List<Integer>> triplets, 
									 TreeNode<Integer> gParent, //grandparent
									 TreeNode<Integer> parent, //parent
									 TreeNode<Integer> child, //curr node
									 int x) {
	    if (child == null) {
	        return;
	    }

		/*
			If both parent and grand-parent are not null
			then it is a valid triplet.
		*/
	    if (gParent != null && parent != null) {
	        int currValue = gParent.data + parent.data + child.data;

	        if (currValue > x) {
	        	List<Integer> triplet = new ArrayList<>();
	        	
	        	triplet.add(gParent.data);
	        	triplet.add(parent.data);
	        	triplet.add(child.data);

	            triplets.add(triplet);
	        }
	    }

	    fillTriplets(triplets, parent, child, child.left, x);
	    fillTriplets(triplets, parent, child, child.right, x);
	}

	public static List<List<Integer>> findTriplets(TreeNode<Integer> root, int x) {
		List<List<Integer>> triplets = new ArrayList<>();

		fillTriplets(triplets, null, null, root, x);

		return triplets;
	}

}
```
