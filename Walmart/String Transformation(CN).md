```java
/*
    Time Complexity - O(N * log(K))
    Space Complexity - O(K)
    where K is the window size and N is the length of the input string
*/

import java.util.PriorityQueue;

public class Solution {
    public static String getTransformedString(String str, int k) {
        StringBuilder answer = new StringBuilder();

        // Build the minHeap
        PriorityQueue<Character> minHeap = new PriorityQueue<>();
        for (int i = 0; i < Math.min(k, str.length()); i++) {
            minHeap.add(str.charAt(i));
        }

        int indexToBeAdded = k;

        // While all the characters from the string have not been removed,
        // keep removing the smallest character among the first k characters.
        while (!minHeap.isEmpty()) {
            answer.append(minHeap.poll());
            if (indexToBeAdded < str.length()) {
                minHeap.add(str.charAt(indexToBeAdded));
                indexToBeAdded++;
            }
        }

        return answer.toString();
    }
}
```
