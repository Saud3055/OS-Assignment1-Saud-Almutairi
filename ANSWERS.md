# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**
tiny execution unit inside a shared memory process. Threads are quicker and lighter than processes, which are heavy and need more time to make.

Because threads are more effective at imitating scheduling, we used them in this assignment. Multiple jobs can operate simultaneously within the same software thanks to threads. The simulation would become more complicated and resource-intensive if processes were used.
[Write your answer here. Consider: What is a process? What is a thread? How do they differ in terms of memory, resources, creation overhead? Why are threads more suitable for this simulation?]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**
A process in Round-Robin scheduling is halted and pushed to the end of the ready queue if it does not complete within its time quantum. This ensures that all processes are fair by allowing other processes to run before it gets another turn. The procedure will keep going through the queue until there is no more time left.
[Write your answer here. Describe the specific behavior - where does the process go? When does it run again? Give an example from your actual program output showing a process that was re-queued.]

Example from my output:
```
▶ P1 executing quantum [3000ms]
⏸ P1 completed quantum 3000ms │ Overall progress: 53%
Remaining time: 2617ms
↻ P1 yields CPU for context switch

➕ P1 added to ready queue
[Paste a relevant snippet from your program output here showing a process being re-queued]
```

**Explanation of example:**
[Explain what's happening in the output snippet you pasted]

---
In this example, process P1 had 2617 ms left, therefore it did not complete within the 3000 ms time quantum. As a result, it gave up the CPU and was put back in the ready queue. P1 reappears at the end of the queue later  
## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: When P1 is initially created in the code using new Thread (process), it is in the New state. It hasn't yet begun execution. When P1 is first added to the ready queue

2. **Runnable**: When the start() method is invoked, P1 moves into the Runnable state. The thread is now prepared to execute and is awaiting CPU scheduling. This occurs when P1 is chosen from the queue, just before execution starts.

3. **Running**: P1 is in the Running state when it is actively executing its quantum

4. **Waiting**: When P1 is paused after completing its time quantum and before it has another turn, it enters the Waiting state. When it releases the CPU

5. **Terminated**: When P1 completes all of its execution and has no more time left, it enters the Terminated state. 

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: Web Server

**Description**: 
Multiple client requests are handled concurrently by a web server, where each request is handled as a distinct task or thread.
**Why Round-Robin works well here**: 
Every client request is given an equal amount of CPU time thanks to round robin scheduling. This enhances system responsiveness by preventing any one request from obstructing others. It is especially useful in environments where multiple users are interacting with the server simultaneously.
### Example 2: Operating System Scheduler

**Description**: 
Scheduling algorithms are used by operating systems to effectively manage several active processes and applications.
**Why Round-Robin works well here**: 
By assigning a set time quantum to each activity, round robin assures equity. It keeps people from starving and makes it possible for interactive systems to react fast. Because of this, it is perfect for time-sharing systems where numerous apps operate simultaneously.
---

## Summary

**Key concepts I understood through these questions:**
1. The difference between threads and processes
2. How Round-Robin scheduling works
3. Thread lifecycle and states

**Concepts I need to study more:**
1. Deadlocks
2. Advanced scheduling algorithms
