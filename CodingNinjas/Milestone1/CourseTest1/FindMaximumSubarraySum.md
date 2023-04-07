<pre>
Find Maximum Subarray Sum

You are given an integer array, arr, of size N and a positive integer K. Out of all subarrays of 'arr' of size K, find the sum of the subarray that has the maximum sum.


Sample Input 1:
4 1
1 2 3 4
Sample Output 1:
4
Sample Input 2:
6 2
2 7 3 6 7 7
Sample Output 2:
14
Explanation for Sample Output 2:
There are 5 subarrays of size 2 in this array. They are {2, 7}, {7, 3}, {3, 6}, {6, 7}, {7, 7}. Since the subarray {7, 7} has the maximum sum among all the subarrays, the output will be 7 + 7 = 14
</pre>


```Java
    import java.util.Scanner;
    public class Solution {
        public static void main(String[] args) {
            Scanner sc = new Scanner(System.in);
            int n = sc.nextInt();
            int k = sc.nextInt();
            int arr[] = new int[n];
            for(int i=0; i<n; i++)
                arr[i] = sc.nextInt();

            // if (n < k) {
            //   System.out.println("Invalid");
            //   return -1;
            // }

            int res = 0;
            for (int i = 0; i < k; i++)
                res += arr[i];
            int curr_sum = res;
            for (int i = k; i < n; i++) {
                curr_sum += arr[i] - arr[i - k];
                res = Math.max(res, curr_sum);
            }
            System.out.println(res);
        }
    }
```
