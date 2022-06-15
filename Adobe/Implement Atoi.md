```java
class Solution
{
    int atoi(String str) {
    	if(str.charAt(0)=='-'){
    	    if(checkForDigits(str.substring(1))){
    	        return -Integer.parseInt(str.substring(1));
    	    }
    	}
    	
    	if(checkForDigits(str)){
    	    return Integer.parseInt(str);
    	}
    	
    	return -1;
    }
    public boolean checkForDigits(String str){
        for(char ch: str.toCharArray()){
            if(!Character.isDigit(ch))  return false;
        }
        
        return true;
    }
}
```
