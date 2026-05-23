
# EX 1A Print All Numbers 
## DATE: 16/04/2026

## AIM:
To Write a Java program that takes an integer input N from the user and prints all the numbers from 1 to N, separated by spaces, on a single line..

## Algorithm
1.Start the program.

2.Input an integer N from the user.

3.Check condition:
If N <= 0, display "Invalid input. N must be greater than 0." and stop.

4.Initialize a variable i = 1.

5.Use a loop to print numbers from 1 to N:

While i <= N, print i followed by a space.

Increment i by 1.

End loop and stop the program. 
 

## Program:
```
/*
Program to implement Reverse a String
Developed by: DHINESH R
Register Number:  212223220019

*/

import java.util.*; 
public class demo   
{
    public static void main(String args[]) 
    {
        int N,i;
        Scanner sc=new Scanner(System.in);
        N=sc.nextInt();  
        if(N<=0)
        {
            System.out.println("Invalid input. N must be greater than 0.");
            
        }
        else{
            for(i=1;i<=N;i++){
                System.out.print(i+" ");    
            }
        }
    }
}
```

## Output:
<img width="425" height="152" alt="image" src="https://github.com/user-attachments/assets/54163f54-8ab1-4383-ad7b-35428ac584b3" />



## Result:
The program successfully print all the numbers from 1 to N. 

# EX 1B Power of 2
## DATE: 17/04/2026

## AIM:
To write a Java program to for given constraints.Given an integer n, return true if it is a power of two. Otherwise, return false.

An integer n is a power of two, if there exists an integer x such that n == 2x.

## Algorithm
1. Start the program.

2.Read an integer input n from the user.

3.Check if n is less than or equal to 0.

4.If yes, return false (since powers of two are positive).

5.Perform a bitwise AND operation between n and n - 1.

6.If the result is 0, then n is a power of two (only one bit is set in its binary form).

7.Otherwise, it is not a power of two.

8.Display the result (true or false) to the user. 

## Program:
```
/*
Program to implement Reverse a String
Developed by: DHINESH R
Register Number:  212223220019

import java.util.Scanner;

public class Solution {

    public boolean isPowerOfTwo(int n) {
        if (n <= 0) {
            return false;
        }
        return (n & (n - 1)) == 0; 
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Solution sol = new Solution();
        int n = scanner.nextInt();

        boolean result = sol.isPowerOfTwo(n);
        System.out.println(result);

        scanner.close();
    }
}

*/
```

## Output:
<img width="510" height="230" alt="image" src="https://github.com/user-attachments/assets/d4f55e9f-2f7c-423e-bcff-73dc3303fa4c" />

## Result:
The program successfully implemented and the expected output is verified.

# EX 1C Valid Pairs using Brute Force Approach
## DATE:17/04/2026
## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.

## Algorithm
1.Start the program.

2.Input the size of the array n, the n array elements, and an integer k.

3.Initialize a counter variable count = 0.

4.Compare each pair of elements:

Use two loops:
For each i from 0 to n-1,
and for each j from i+1 to n-1,
check if the absolute difference |nums[i] - nums[j]| == k.

If true, increment count by 1.

5.Display the total count of such pairs and stop the program. 

## Program:
```
/*
Program to implement Reverse a String
Developed by: DHINESH R
Register Number:  212223220019
*/
import java.util.Scanner;
public class CountPairsWithDifference {
    public static int countKDifference(int[] nums, int k) {
        //Type your code here
        int count=0;
        for(int i=0;i<nums.length;i++){
            for(int j=i+1;j<nums.length;j++){
                if(Math.abs(nums[i]-nums[j])==k){
                    count++;
                }
            }
            
        }
        return count;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] nums = new int[n];
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }
        int k = sc.nextInt();
        int result = countKDifference(nums, k);
        System.out.println(result);
        sc.close();
    }
}

```

## Output:

<img width="396" height="290" alt="image" src="https://github.com/user-attachments/assets/71cc1b06-d4e6-422a-8707-63a95b3a879b" />

## Result:
The program successfully implemented and the expected output is verified.

# EX 1D Sorted Array using Divide and Conquer Approach.
## DATE:17/04/2026

## AIM:
To write a Java program to for given constraints.
Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).

## Algorithm
1.Start the program.
Read the sizes of two sorted arrays m and n, then input the elements of both arrays nums1 and nums2.

2.Initialize two pointers p1 = 0 and p2 = 0 to traverse both arrays.

3.Use a helper function getMin() to return the smaller of the current elements from both arrays and move the corresponding pointer forward.

4.Find the median:

If the total number of elements (m + n) is even, skip (m + n)/2 - 1 elements, then take the average of the next two smallest elements as the median.

If (m + n) is odd, skip (m + n)/2 elements, then take the next smallest element as the median.

5.Display the computed median and stop the program.  

## Program:
```
/*
Program to implement Reverse a String
Developed by: DHINESH R
Register Number:  212223220019

*/

import java.util.Scanner;

public class Solution {
    private int p1 = 0, p2 = 0;

    // Get the smaller value between nums1[p1] and nums2[p2], and move the pointer forward
    private int getMin(int[] nums1, int[] nums2) {
        if (p1 < nums1.length && p2 < nums2.length) {
            return nums1[p1] < nums2[p2] ? nums1[p1++] : nums2[p2++];
        } else if (p1 < nums1.length) {
            return nums1[p1++];
        } else if (p2 < nums2.length) {
            return nums2[p2++];
        }
        return -1; // Should not reach here if input is valid
    }

    // Main logic to find median of two sorted arrays
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
       //Type code here...
       int m=nums1.length,n=nums2.length;
       if((m+n)%2==0){
           for(int i=0;i<(m+n)/2-1;++i){
               int tmp=getMin(nums1,nums2);
           }
           return (double) (getMin(nums1,nums2)+getMin(nums1,nums2))/2;
       }
       else{
           for(int i=0;i<(m+n)/2;++i){
               int tmp=getMin(nums1,nums2);
           }
           return getMin(nums1,nums2);
       }
    }

    // Main method with user input
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        // Input for nums1
        //System.out.print("Enter size of first sorted array: ");
        int m = sc.nextInt();
        int[] nums1 = new int[m];
        //System.out.println("Enter " + m + " sorted integers for first array:");
        for (int i = 0; i < m; i++) {
            nums1[i] = sc.nextInt();
        }

        // Input for nums2
        //System.out.print("Enter size of second sorted array: ");
        int n = sc.nextInt();
        int[] nums2 = new int[n];
        //System.out.println("Enter " + n + " sorted integers for second array:");
        for (int i = 0; i < n; i++) {
            nums2[i] = sc.nextInt();
        }

        // Find and display the median
        double median = sol.findMedianSortedArrays(nums1, nums2);
        System.out.println("Median of the two sorted arrays = " + median);
        
        sc.close();
    }
}

```

## Output:
<img width="883" height="330" alt="image" src="https://github.com/user-attachments/assets/d430c9c0-0455-4220-811f-1a6ab58b32f7" />

## Result:
The program successfully implemented and the expected output is verified.
# EX 1E Integer Multiplication using Divide and Conquer Approach(Strassen’s algorithm).
## DATE:17/04/2026


## AIM:
To write a Java program to for given constraints.
You are given two square matrices A and B of size n × n (where n is a power of 2). Your task is to compute their matrix product using Strassen’s Matrix Multiplication algorithm and return the resulting matrix.

Unlike traditional matrix multiplication which takes O(n3)O(n^3)O(n3) time, Strassen’s algorithm improves this by reducing the number of recursive multiplications from 8 to 7, achieving approximately O(n2.81)O(n^{2.81})O(n2.81) complexity.
## Algorithm
1.Start the program.
Read the size n (power of 2) and input two n × n matrices A and B.

2.Divide each matrix into four submatrices:
A11, A12, A21, A22 and B11, B12, B21, B22, each of size (n/2) × (n/2).

3.Compute seven intermediate products (M1 to M7) using Strassen’s formulas:

M1 = (A11 + A22) × (B11 + B22)
M2 = (A21 + A22) × B11
M3 = A11 × (B12 - B22)
M4 = A22 × (B21 - B11)
M5 = (A11 + A12) × B22
M6 = (A21 - A11) × (B11 + B12)
M7 = (A12 - A22) × (B21 + B22)


4.Combine the results to form the resulting submatrices:

C11 = M1 + M4 - M5 + M7  
C12 = M3 + M5  
C21 = M2 + M4  
C22 = M1 + M3 - M2 + M6


Then merge C11, C12, C21, C22 to get the final matrix C.

5.Display the resultant matrix C as the product of A and B, and stop the program. 


## Program:
```
/*
Program to implement Reverse a String
Developed by: DHINESH R
Register Number:  212223220019
*/

import java.util.Scanner;

public class StrassenMatrix {

    // Add two matrices
    static int[][] add(int[][] A, int[][] B) {
        int n = A.length;
        int[][] C = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                C[i][j] = A[i][j] + B[i][j];
        return C;
    }

    // Subtract matrix B from A
    static int[][] subtract(int[][] A, int[][] B) {
        int n = A.length;
        int[][] C = new int[n][n];
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                C[i][j] = A[i][j] - B[i][j];
        return C;
    }

    // Strassen recursive multiplication
    static int[][] strassen(int[][] A, int[][] B) {
        //Type code here...
        int n = A.length;
        int[][] C = new int[n][n];
        if (n == 1) {
            C[0][0] = A[0][0] * B[0][0];
            return C;
        }
        int mid =n/2;
        int[][] A11 = new int[mid][mid],A12 = new int[mid][mid],A21 = new int[mid][mid], A22 = new int[mid][mid];
        int[][] B11 = new int[mid][mid],B12 = new int[mid][mid], B21 = new int[mid][mid],B22 = new int[mid][mid];
        for (int i=0;i<mid;i++){
            for(int j=0;j<mid;j++) {
                A11[i][j] = A[i][j];
                A12[i][j] = A[i][j+mid];
                A21[i][j] = A[i+mid][j];
                A22[i][j] = A[i+mid][j+mid];
                B11[i][j] = B[i][j];
                B12[i][j] = B[i][j+mid];
                B21[i][j] = B[i+mid][j];
                B22[i][j] = B[i+mid][j+mid];
            }
        }
                
            int[][] M1 =strassen(add(A11,A22),add(B11,B22));
            int[][] M2 =strassen(add(A21,A22),B11);
            int[][] M3 =strassen(A11,subtract(B12,B22));
            int[][] M4 =strassen(A22,subtract(B21,B11));
            int[][] M5 =strassen(add(A11,A12),B22);
            int[][] M6 =strassen(subtract(A21,A11),add(B11,B12));
            int[][] M7 =strassen(subtract(A12,A22),add(B21,B22));
            int[][] C11 = add(subtract(add(M1,M4),M5),M7);
            int[][] C12 = add(M3,M5);
            int[][] C21 = add(M2,M4);
            int[][] C22 = add(subtract(add(M1,M3),M2),M6);
            for (int i=0; i<mid;i++){
                for (int j=0;j<mid;j++) {
                    C[i][j] = C11[i][j];
                    C[i][j+mid] = C12[i][j];
                    C[i+mid][j] = C21[i][j];
                    C[i+mid][j+mid] = C22[i][j];
                }
            }
        
                return C;
            }
        
        
    

    // Function to print matrix
    static void printMatrix(int[][] matrix) {
        for (int[] row : matrix) {
            for (int val : row)
                System.out.print(val + " ");
            System.out.println();
        }
    }

    // Main method to get input and run Strassen multiplication
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Read size of matrix
        //System.out.print("Enter matrix size (power of 2): ");
        int n = sc.nextInt();

        int[][] A = new int[n][n];
        int[][] B = new int[n][n];

        // Input Matrix A
        //System.out.println("Enter elements of matrix A:");
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                A[i][j] = sc.nextInt();

        // Input Matrix B
        //System.out.println("Enter elements of matrix B:");
        for (int i = 0; i < n; i++)
            for (int j = 0; j < n; j++)
                B[i][j] = sc.nextInt();

        // Multiply using Strassen
        int[][] result = strassen(A, B);

        // Output the result matrix
        System.out.println("Result of Strassen Matrix Multiplication:");
        printMatrix(result);
    }
}
```

## Output:
<img width="493" height="432" alt="image" src="https://github.com/user-attachments/assets/b8057f32-f7ff-4854-82cd-d9fa62ee8073" />

## Result:
The program successfully implemented and the expected output is verified.
