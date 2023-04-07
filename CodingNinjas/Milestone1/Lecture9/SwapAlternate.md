<pre>
Swap Alternate

You have been given an array/list(ARR) of size N. You need to swap every pair of alternate elements in the array/list.

Sample Input 1:
1
6
9 3 6 12 4 32
Sample Output 1 :
3 9 12 6 32 4
</pre>

```Java
    public class Solution {
        public static void swapAlternate(int arr[]) {
            for(int i=0; i<arr.length-1; i+=2) {
                int temp = arr[i];
                arr[i] = arr[i+1];
                arr[i+1] = temp;
            }
        }
    }
```
