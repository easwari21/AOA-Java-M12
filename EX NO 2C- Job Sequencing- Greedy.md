
# EX 2C Job Sequencing using Greedy Approach
## DATE: 08.09.2025

## AIM:
To write a Java program to for given constraints.
Given an integer array nums and an integer k, return the number of pairs (i, j) where i < j such that |nums[i] - nums[j]| == k.

The value of |x| is defined as:

x if x >= 0.
-x if x < 0.You're given N jobs, each with:

A unique jobId

A deadline (by which it must be completed)

A profit (earned only if completed on or before the deadline)

Each job:

Takes exactly 1 unit of time

Only one job can be done at a time

Your goal is to maximize total profit while completing the maximum number of jobs possible within their deadlines.

## Algorithm
```
1. Start the program and read the number of jobs n.

2. Sort all jobs in descending order of profit.

3.Determine the largest deadline among all jobs.

4. Create a boolean array slot[maxDeadline + 1], where each index represents a time slot.

5.For each job in sorted order,check from its deadline slot backward .

6.Print the number of jobs scheduled and total profit obtained.
```
## Program:
```
Program to implement Reverse a String
Developed by: Easwari M
Register Number: 212223240033
```

```
import java.util.*;
public class JobScheduling {

    static class Job {
        int id, deadline, profit;

        Job(int id, int deadline, int profit) {
            this.id = id;
            this.deadline = deadline;
            this.profit = profit;
        }
    }

    public static int[] jobScheduling(Job[] jobs, int n) {
        Arrays.sort(jobs,(a,b)->b.profit-a.profit);
        int maxDeadline=0;
        for (Job job:jobs){
            maxDeadline =Math.max(maxDeadline,job.deadline);
        }
        boolean[] slot=new boolean[maxDeadline+1];
        int jobsDone=0,totalProfit=0;
        for(Job job:jobs){
            for(int j=job.deadline;j>0;j--){
                if(!slot[j]){
                    slot[j]=true;
                    jobsDone++;
                    totalProfit+=job.profit;
                    break;
                }
            }
        }
        return new int[]{jobsDone,totalProfit};
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        Job[] jobs = new Job[n];

        for (int i = 0; i < n; i++) {
            int id = sc.nextInt();
            int deadline = sc.nextInt();
            int profit = sc.nextInt();
            jobs[i] = new Job(id, deadline, profit);
        }

        int[] result = jobScheduling(jobs, n);
        System.out.println(result[0] + " " + result[1]);
    }
}
```

## Output:
<img width="368" height="421" alt="image" src="https://github.com/user-attachments/assets/2fd461df-a61d-4302-b4d5-baf2e4fcadc9" />



## Result:
The program successfully implemented and the expected output is verified.
