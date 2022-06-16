```java
class Solution
{
    //Function to check if two strings are rotations of each other or not.
    public static boolean areRotations(String s1, String s2 )
    {
        return s1.length()==s2.length() && (s1+s1).contains(s2);
    }
    
}
```
