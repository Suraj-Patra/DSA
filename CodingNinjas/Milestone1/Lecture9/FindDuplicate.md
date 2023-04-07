<pre>
Find Duplicate

You have been given an integer array/list(ARR) of size N which contains numbers from 0 to (N - 2). Each number is present at least once. That is, if N = 5, the array/list constitutes values ranging from 0 to 3 and among these, there is a single integer value that is present twice. You need to find and return that duplicate number present in the array.

Note : Duplicate number is always present in the given array/list.

Sample Input 1:
1
9
0 7 2 5 4 7 1 3 6
Sample Output 1:
7
</pre>

```Java
    public class Solution{
        public static int duplicateNumber(int arr[]) {
            //Your code goes here
            int ans = 0;
            int n = arr.length;

            for(int i=0; i<n; i++) {
                ans ^= arr[i];
            }

            for(int i=0; i<=n-2; i++) {
                ans ^= i;
            }

            return ans;
        }
    }
```
