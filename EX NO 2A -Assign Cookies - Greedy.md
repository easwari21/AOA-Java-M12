
# EX 2A Assign Cookies using Greedy Algorithm. 
## DATE: 03.09.2025

## AIM:
To Write a Java program for the following Constraints.
Assume you are an awesome parent and want to give your children some cookies. But, you should give each child at most one cookie.

Each child i has a greed factor g[i], which is the minimum size of a cookie that the child will be content with; and each cookie j has a size s[j]. If s[j] >= g[i], we can assign the cookie j to the child i, and the child i will be content. Your goal is to maximise the number of your content children and output the maximum number.

## Algorithm

1. Start the program

2. Sort both arrays g[] and s[] in ascending order to distribute the smallest cookie that satisfies each child.
   
3. Initialize two pointers,i = 0 to track children.,j = 0 → to track cookies.
   
4. Use a loop to iterate through cookies,If the current cookie s[j] satisfies the child g[i] increment i.
   
5. After the loop, the variable i represents the total number of content (satisfied) children.
    
6.Print i and stop the program.

## Program:
```
Program to implement Reverse a String
Developed by: Easwari M
Register Number: 212223240033
```
```
import java.util.*;

public class AssignCookies {
    
    public static int findContentChildren(int[] g, int[] s) {
        // Type Your Logic Here.
        Arrays.sort(g);
        Arrays.sort(s);
        int i=0,j=0;
        while(i<g.length && j<s.length){
            if(s[j]>=g[i])i++;
            j++;
        }
        return i;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] g = new int[n];
        for (int i = 0; i < n; i++) g[i] = sc.nextInt();
        int m = sc.nextInt();
        int[] s = new int[m];
        for (int i = 0; i < m; i++) s[i] = sc.nextInt();
        System.out.println(findContentChildren(g, s));
    }
}
```
## Output:
<img width="363" height="348" alt="512703936-a26571d2-ff87-4db9-a8b4-abc089e04f62" src="https://github.com/user-attachments/assets/31e11d8e-e716-4f54-bacf-c4fcc20a115f" />
## Result:
The program successfully print all the numbers from 1 to N. 
