```java
/*
    Time Complexity: O(N*M).
    Space Complexity: O(N*M).

    Where 'N' is the number of rows, and 'M' is the number of columns in the given matrix.
*/

import java.util.Queue;
import java.util.LinkedList;

class Pair {
	int x;
	int y;

	Pair(int x, int y) {
		this.x = x;
		this.y = y;
	}
}

public class Solution {
	public static int maximumZeroOneDistance(int matrix[][], int N, int M) {
        // Queue to store the co-ordinate of ones.
        Queue<Pair> levelOrder = new LinkedList<>();	//contains coordinates of all 1s
		int levelCount = 0, X, a, b;

		for (int i = 0; i < N; i++) {
            for (int j = 0; j < M; j++) {
                if (matrix[i][j] == 1) {
					levelOrder.add(new Pair(i, j));
				}
			}
		}
	
    // If all the elements are 1, then return -1.
    if (levelOrder.size() == N * M)   return -1;

    // Level-order traversal of the matrix.
		while (!levelOrder.isEmpty()) {
			X = levelOrder.size();

			for (int i = 0; i < X; i++) {
				Pair xy = levelOrder.poll();
				a = xy.x;
				b = xy.y;

				if (a + 1 < N && matrix[a + 1][b] == 0) {
					matrix[a + 1][b] = 1;
					levelOrder.add(new Pair(a + 1, b));
				}

				if (a - 1 >= 0 && matrix[a - 1][b] == 0) {
					matrix[a - 1][b] = 1;
					levelOrder.add(new Pair(a - 1, b));
				}

				if (b + 1 < M && matrix[a][b + 1] == 0) {
					matrix[a][b + 1] = 1;
					levelOrder.add(new Pair(a, b + 1));
				}

				if (b - 1 >= 0 && matrix[a][b - 1] == 0) {
					matrix[a][b - 1] = 1;
					levelOrder.add(new Pair(a, b - 1));
				}
			}

			levelCount++;
		}

		return levelCount - 1;
	}
}
``
