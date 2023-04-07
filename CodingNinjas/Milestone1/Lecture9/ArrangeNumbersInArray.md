<pre>
Arrange Numbers In Array

You have been given an empty array(ARR) and its size N. The only input taken from the user will be N and you need not worry about the array.
Your task is to populate the array using the integer values in the range 1 to N(both inclusive) in the order - 1,3,5,.......,6,4,2.

Sample Input 1 :
1
6
Sample Output 1 :
1 3 5 6 4 2
Explanation of Sample Input 1 :
Since the value of N is 6, the number will be stored in the array in such a fashion that 1 will appear at 0th index, then 2 at the last index, in a similar fashion 3 is stored at index 1. Hence the array becomes 1 3 5 6 4 2.
</pre>

```Java
    public class Solution {
        public static void arrange(int[] arr, int n) {
            int flag = 1, left = 0, right = arr.length-1;
            for(int i=1; i<=n; i++) {
                if(flag == 1) {
                    arr[left++] = i;
                    flag = 0;
                } else {
                    arr[right--] = i;
                    flag = 1;
                }
            }
        }
    }
```
