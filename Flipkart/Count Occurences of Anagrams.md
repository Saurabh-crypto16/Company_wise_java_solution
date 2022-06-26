```java
class Solution {
   int search(String pat, String txt) {
        int [] freq1 = new int[26];
        int [] freq2 = new int[26];
       
        int window = pat.length();
        for(int i = 0; i < window ; i++){
            freq1[pat.charAt(i)-'a']++;
        }
       
        int i = 0;
        int j = 0;
        int anagram = 0;
       
        while( j < txt.length()){
            freq2[txt.charAt(j) - 'a']++;
           
            if(j - i + 1 == window){
                if(Arrays.equals(freq1,freq2)){
                    anagram++;
                }
                freq2[txt.charAt(i)-'a']--;
                i++;
            }
            j++;
        }
       
        return anagram;
   }
}
```
