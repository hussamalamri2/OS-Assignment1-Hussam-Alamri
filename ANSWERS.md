# Technical Answers - Student ID: 445050170

## Question 1: Thread vs Process

The main difference between a thread and a process is that a process has its own separate memory space, while threads share the same memory space within a process. Another key difference is that creating a new process requires more system resources and overhead compared to creating a thread, which is lighter and faster. In this assignment, we used threads instead of separate processes because we needed multiple tasks (processes) to share CPU time within the same application. In SchedulerSimulation.java, each Process object is wrapped in a Thread, allowing them to run concurrently. Threads also allow easier communication since they share memory, as seen in the processMap that maps threads to processes. If we used separate processes, inter-process communication would require complex mechanisms like pipes or sockets, which are unnecessary for this simulation.

## Question 2: Ready Queue Behavior

In Round-Robin scheduling, when a process doesn't finish within its time quantum, it is preempted and moved to the end of the ready queue to wait for its next turn. For example, in my program output, P1 ran for 3000ms but still had 2817ms remaining. The output shows: "P1 yields CPU for context switch" and then "P1 added to ready queue" with the queue showing P1 at the end. This re-queueing behavior is important for fairness because it ensures every process gets equal CPU time in a cyclic manner. Without this, processes with long burst times could monopolize the CPU while short processes starve. This is the fundamental principle of Round-Robin scheduling: each process gets a fair share of CPU time in a circular order.

## Question 3: Thread Lifecycle

For a process like P1 in my simulation, the thread goes through all five states. First, when the Process object is created but the thread hasn't started yet, it's in the **New** state. When addProcessToQueue() calls new Thread(process), the thread enters the **Runnable** state. When the scheduler calls currentThread.start(), it becomes **Running** and executes the run() method. During execution, Thread.sleep() is called to simulate CPU work, which puts the thread in **Waiting** state temporarily. After completing its quantum, the thread finishes execution and enters the **Terminated** state. In my code, Thread.start() initiates the thread, Thread.join() in the main scheduler waits for it to finish, and Thread.sleep() inside the run() method simulates execution time.

## Question 4: Real-World Applications

Two real-world scenarios where Round-Robin scheduling with threads is useful:

First, **web servers like Apache or Nginx** use Round-Robin scheduling to handle incoming HTTP requests. When multiple users access a website, the server creates threads for each connection and uses a Round-Robin algorithm to ensure fair CPU distribution. This is appropriate because it provides responsiveness - no user waits too long for their request to be processed. The fairness aspect ensures that one heavy request doesn't block all other users.

Second, **operating system's process scheduler** itself uses Round-Robin for time-sharing systems. When you run multiple applications on your computer (like Chrome, Word, and Spotify), the OS scheduler uses Round-Robin to give each application a time slice. This provides responsiveness and smooth multitasking. The concepts from this assignment apply directly: each application is like a process, the time quantum determines how responsive the system feels, and context switching allows seamless switching between applications.

Example 1 : Web Server (Apache/Nginx)
Description:
Web servers handle multiple client requests simultaneously. When hundreds or thousands of users access a website at the same time, each HTTP request needs to be processed by the server. The server creates threads to handle each request, and the CPU must allocate time fairly among all active connections.

Why Round-Robin works well here:
Round-Robin scheduling is appropriate for web servers because it provides fairness and responsiveness. Each client request receives a fair share of CPU time, preventing a single heavy request (like a large file download) from blocking other lightweight requests (like simple HTML pages). The predictable time quantum ensures that all users experience consistent response times. This approach also prevents starvation, as every request eventually gets CPU time regardless of its complexity. In high-traffic scenarios, this fairness is crucial for maintaining good user experience across all connected clients.

Example 2 : Operating System Process Scheduler
Description:
Modern operating systems like Windows, Linux, or macOS run multiple applications simultaneously. A user might have a web browser, text editor, music player, and file explorer all open at once. The OS kernel uses a scheduler to allocate CPU time to each running application.

Why Round-Robin works well here:
Round-Robin scheduling is appropriate for general-purpose operating systems because it provides good interactivity and responsiveness. When a user switches between applications, each application gets CPU time quickly due to the small time quantum, creating the illusion that all applications are running simultaneously. This scheduling approach ensures that CPU-intensive background tasks (like file compression) do not make the system feel sluggish when the user is typing in a text editor or moving the mouse. The predictable time slices also make system performance more consistent compared to other scheduling algorithms. The concepts from this assignment directly apply to how operating systems manage processes: each application is like a process, the time quantum determines how responsive the system feels, and context switching allows seamless switching between applications.

Summary
Key concepts I understood through these questions:

Thread vs Process Differences: I now clearly understand that threads share memory space within a process, making communication faster and creation lighter, while processes have isolated memory and require more overhead. This explains why threads are used in CPU scheduling simulations.

Round-Robin Scheduling Behavior: I learned that when a process doesn't complete within its time quantum, it gets re-queued at the end of the ready queue, ensuring fairness and preventing starvation. The visual output from my simulation helped me see this behavior clearly.

Thread Lifecycle States: I can now trace a thread through all five states (New, Runnable, Running, Waiting, Terminated) and identify exactly when each state occurs based on method calls like Thread.start(), Thread.sleep(), and thread completion.

Real-World Applications: I understand how Round-Robin scheduling is applied in practical scenarios like web servers and operating systems, where fairness, responsiveness, and predictability are critical requirements.

Concepts I need to study more:

Thread Synchronization: I need to learn more about how to safely share data between threads without causing race conditions. Topics like synchronized blocks, locks, and atomic operations are areas I want to explore further.

Advanced Scheduling Algorithms: While I understand Round-Robin well, I want to study other scheduling algorithms like Priority Scheduling, Multilevel Queue Scheduling, and Real-Time Scheduling to understand their trade-offs and use cases.

Deadlock Prevention: I need to learn more about deadlock scenarios and how to prevent them when multiple threads wait for resources held by each other, which is an important concept in concurrent programming.


