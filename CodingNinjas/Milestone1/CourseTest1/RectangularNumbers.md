<pre>
Sample Input :
3
Sample Output :
33333
32223
32123
32223
33333
</pre>

```Java
    public class solution {

        public static void print(int n) {
            int size = (2 * n) - 1;
            int row, col, ans;
            for (int i = 1; i <= size; i++) {
                for (int j = 1; j <= size; j++) {
                    row = (i>=n)? (i-n+1) : (n-i+1);
                    col = (j>=n)? (j-n+1) : (n-j+1);
                    ans = row >= col ? row : col;
                    System.out.print(ans);
                }
                System.out.println();
            }
        }

    }
```
