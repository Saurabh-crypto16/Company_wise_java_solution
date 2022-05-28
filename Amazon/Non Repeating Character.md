```java
class Solution
{
    //Function to find the first non-repeating character in a string.
    static char nonrepeatingCharacter(String S)
    {
        int freq[]=new int[26];
        for(char c: S.toCharArray()){
            freq[c-'a']++;
        }
        
        for(char c: S.toCharArray()){
            if(freq[c-'a']==1)  return c;
        }
        
        return '$';
    }
}

```
