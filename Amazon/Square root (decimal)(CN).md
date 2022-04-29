```java
import java.util.*;

public class Solution {
    public static double squareRoot(long n, int d) {
    int l = 1, r = (int)Math.min((long)1000000000, n);
    double ans = 0D;
        
		// We will reduce the range until the range is greater than precision.
    while (l <= r) {
      long mid = (l + r) / 2;
      if (mid * mid == n) {
        ans = mid;
        break;
      } else if (mid * mid > n) {
        r = (int)mid - 1;
      }else {
        ans = mid;
        l = (int)mid + 1;
			}
    }

    // We have calculated integral part now we will find decimal part upto d places.
    for (int i = 1; i <= d; i++) {
      // We will add this increment in our answer until its square is less than n.
      double increment = Math.pow(10, -i);
      for (int j = 0; j < 9; j++) {
        if (Math.pow(ans + increment, 2) <= n) {
          ans += increment;
        }else { break;  }
      }
    }

    return ans;
    }
}
```
