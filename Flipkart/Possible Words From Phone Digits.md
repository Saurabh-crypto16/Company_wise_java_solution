```java
class Solution{
    static ArrayList <String> possibleWords(int a[], int N){
        ArrayList<String> ans = new ArrayList<>();
        String[] ch = {"", "", "abc" , "def", "ghi", "jkl", "mno", "pqrs","tuv", "wxyz"};
        recur( ans , ch , "" , 0 , a);
        
        return ans;
    }
    public static void recur(ArrayList<String> ans ,String[] ch,String t,int cur,int a[]){
        if(cur==a.length){
            ans.add(t);
            return;
        }
        
        for(int i=0;i<ch[a[cur]].length();i++){
            recur(ans,ch,t+ch[a[cur]].charAt(i),cur+1,a);
        }
    }
}


```
