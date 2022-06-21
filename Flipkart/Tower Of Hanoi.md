```java
class Hanoi {

    public long toh(int N, int from, int to, int aux) {
        if(N > 0){
           toh(N-1,from,aux,to);
           System.out.println("move disk "+N+" from rod "+from+" to rod "+to);
           toh(N-1,aux,to,from);
        }
        
        return (long)(Math.pow(2,N)-1);
    }
}

```
