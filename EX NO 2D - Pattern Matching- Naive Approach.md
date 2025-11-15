
# EX 2D Pattern Matching using Naive Approach.
## DATE: 14.09.2025

## AIM:
To write a Java program to for given constraints.
Given text string with length n and a pattern with length m, the task is to prints all occurrences of pattern in text.
Note: You may assume that n > m.

Examples: 

Input:  text = "THIS IS A TEST TEXT", pattern = "TEST"
Output: Pattern found at index 10

Input:  text =  "AABAACAADAABAABA", pattern = "AABA"
Output: Pattern found at index 0, Pattern found at index 9, Pattern found at index 12

## Algorithm

1. Start the program and read the main string text.
  
2. Initialize variables,Let n = length of text and m = length of pattern.
   
3. For each position i from 0 to n - m,compare each character of pattern with the corresponding substring of text starting at index i.
   
4. For each position ,initialize j = 0.
   
5.If j == m, then a match is found print the result

## Program:
```
Program to implement Reverse a String
Developed by: Easwari M
Register Number:  212223240033

```
```
import java.util.Scanner;
public class NaivePatternSearch {
    static void search(String text,String pattern){
        int n=text.length();
        int m=pattern.length();
        for(int i=0;i<=n-m;i++){
            int j;
            for(j=0;j<m;j++){
                if(text.charAt(i+j)!=pattern.charAt(j))
                break;
            }
            if(j==m)
                System.out.println("Pattern found at index "+i);
        
    }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String text = scanner.nextLine();
        String pattern = scanner.nextLine();
        search(text, pattern);
        scanner.close();
    }
}
```

## Output:
<img width="795" height="237" alt="image" src="https://github.com/user-attachments/assets/a16c5696-9c82-41a3-a089-1b06f4a80179" />



## Result:
The program successfully implemented and the expected output is verified.
