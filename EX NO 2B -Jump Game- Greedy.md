
# EX 2B Jump Game using Greedy Algorithm.
## DATE:04.09.2025

## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.

## Algorithm
```
1. Start the Program with array nums[] of size n.

2.If n <= 1, no jump is needed  return 0.If nums[0] == 0, the end cannot be reached return -1.

3. Initialize jumps = 0  to count the number of jumps made,currentReach = 0  farthest index reachable with the current number of jumps,maxReach = 0  farthest index reachable from all positions checked so far.

4. Iterate through the array,Update maxReach = max(maxReach, i + nums[i]) to find how far we can reach from index i.

5. If i == currentReach,Increment jumps and update currentReach.

6. If the loop ends without reaching the last index, return -1.

7. Print the result and end the program.
 
```   

## Program:
```
Program to implement Reverse a String
Developed by: Easwari M
Register Number: 212223240033
```

```
import java.util.Scanner;

public class MinJumpToEnd {
    public static int minimumJumps(int[] nums) {
        if(nums.length<=1) return 0;
        if(nums[0]==0) return -1;
        int jump=0;
        int cur=0;
        int far=0;
        for(int i=0;i<nums.length;i++){
            far=Math.max(far,i+nums[i]);
            if(i==cur){
                jump++;
                cur=far;
            }
            if(cur>=nums.length-1){
                break;
            }
            if(cur==i) return -1;
        }
        return cur>=nums.length-1?jump:-1;
    }
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Number of elements
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        System.out.println("Minimum jumps to reach last index: " + minimumJumps(nums));
    }
}

```

## Output:

<img width="929" height="306" alt="image" src="https://github.com/user-attachments/assets/a7c5ca32-2ecf-42f7-a698-0fedc69fe5eb" />



## Result:
The program successfully implemented and the expected output is verified.
