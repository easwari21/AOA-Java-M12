
# EX 2E Pattern Matching using KMP Algorithm.
## DATE: 23.09.2025

## AIM:
To write a Java program for the following constraints.
Longest Palindromic Substring
Given a string s, return the longest palindromic substring in s.
using Manacher's Algorithm

## Algorithm

1. Start the program and get user input
   
2. Initialize an empty list result to store the starting indices of matches,n = length of text and m = length of pattern
   
3.For each position i from 0 to n - m,compare each character of pattern with the substring of text starting at index i.

4.If all characters match j == m, add index i to result.

5.If result is empty, add -1 to indicate that the pattern was not found. 

6.. Print all indices in result amd end the program.


## Program:
```
Program to implement Reverse a String
Developed by: Easwari M
Register Number: 212223240033
```
```
import java.util.*;
public class PatternMatching {
    public static List<Integer> findPatternIndices(String text, String pattern) {
       List<Integer>result=new ArrayList<>();
       int n=text.length();
       int m=pattern.length();
       for(int i=0;i<=n-m;i++){
           int j;
           for(j=0;j<m;j++){
               if(text.charAt(i+j)!=pattern.charAt(j)){
                   break;
               }
           }
           if(j==m){
               result.add(i);
           }
       }
       if(result.isEmpty()){
           result.add(-1);
       }
       return result;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int T = Integer.parseInt(scanner.nextLine()); // number of test cases
        for (int t = 0; t < T; t++) {
            String text = scanner.nextLine();
            String pattern = scanner.nextLine();
            List<Integer> indices = findPatternIndices(text, pattern);
            for (int idx : indices) {
                System.out.print(idx + " ");
            }
            System.out.println();
        }

        scanner.close();
    }
}
```

## Output:
<img width="677" height="255" alt="image" src="https://github.com/user-attachments/assets/3b599b6f-f17c-44c0-860f-2c58df85372c" />



## Result:
The program successfully implemented and the expected output is verified.
