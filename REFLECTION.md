# Reflection Questions

## Instructions
Answer the following questions about your learning experience. Each answer should be **at least 5-7 sentences** and show your understanding.

---

## Question 1: What did you learn about multithreading?

**Your Answer: Through this assignment, I gained a deep understanding of how multithreading works in Java. I learned that threads allow multiple tasks to run concurrently, which is essential for CPU scheduling simulations. I discovered that when we call Thread.start(), it creates a new thread of execution and the run() method is invoked automatically. I also learned about thread synchronization and how multiple threads can share CPU time using scheduling algorithms like Round-Robin. The concept of context switching became clearer to me as I implemented the counter that tracks each time the CPU switches from one process to another. Additionally, I learned about thread states (New, Runnable, Running, Terminated) by observing how processes move through the ready queue. Finally, I understood the importance of Thread.sleep() for simulating execution time and how it helps visualize the scheduling process. This assignment also taught me how to manage multiple threads simultaneously and coordinate their execution using join() to wait for thread completion.**

---

## Question 2: What was the most challenging part of this assignment?

**My Answer: The most challenging part was implementing the waiting time tracking feature. Initially, I struggled to understand how to calculate the time each process spent waiting in the queue without interfering with the actual execution. I had to think carefully about when to start the timer (when the process is created) and when to calculate the waiting time (when the process is re-queued after its quantum). Another difficulty was ensuring that the waiting time accumulated correctly across multiple cycles of the same process. I also faced challenges with the context switch counter because I had to determine the exact moment when a context switch occurs. At first, I was incrementing the counter at the wrong place, which gave incorrect numbers. After reading about CPU scheduling theory, I realized that a context switch happens when a new process starts executing, so I placed the counter right before each process runs.**

---

## Question 3: How did you overcome the challenges you faced?

**My Answer: To overcome these challenges, I used a systematic approach. First, I reviewed the lecture slides on Round-Robin scheduling to understand the theory behind context switching and waiting time. Then, I added print statements throughout the code to track variable values and understand the flow of execution. This helped me identify exactly when processes were being created, when they were running, and when they were being re-queued. For the waiting time calculation, I created a simple test case with only 2 processes to isolate the issue and verify my calculations. I also used System.currentTimeMillis() to get accurate timestamps. For the context switch counter, I researched online to confirm the definition of a context switch. I also asked my classmates for clarification on where to place the counter. Finally, I tested each feature individually before combining them to ensure each one worked correctly on its own. **

---

## Question 4: How can you apply multithreading concepts in real-world applications?

**My Answer: Multithreading concepts are essential in many real-world applications. First, web servers use multithreading to handle multiple client requests simultaneously. When you visit a website, the server creates a separate thread for each request, allowing hundreds or thousands of users to access the site at the same time without waiting for each other. Round-Robin scheduling ensures fair CPU time distribution among all active connections. Second, video game engines heavily rely on multithreading. One thread handles rendering graphics, another handles physics calculations, another processes user input, and another manages audio. This separation allows games to run smoothly at high frame rates. Without multithreading, the game would freeze while processing complex calculations. Third, media players like Spotify or YouTube use threads to download, buffer, and play content simultaneously. One thread downloads the next part of the song or video while another thread plays the current part, providing seamless playback without interruptions. **

---

## Additional Reflections (Optional)

### What would you like to learn more about?

I am very interested in learning more about advanced synchronization techniques in multithreading, especially how to avoid race conditions and deadlocks. This assignment used basic thread management with start() and join(), but I want to understand more complex scenarios like producer-consumer problems, reader-writer locks, and semaphores. I am also curious about how operating systems handle thread scheduling at the kernel level versus user-level threads. Additionally, I would like to learn about parallel programming frameworks like Java's Fork/Join framework and how they differ from traditional threading. Another topic that fascinates me is how modern multi-core processors handle thread execution and how we can optimize our code to take full advantage of multiple CPU cores. Finally, I want to explore how real-time operating systems (RTOS) use scheduling algorithms differently than general-purpose OSes to meet strict timing requirements.

---

### How confident do you feel about multithreading concepts now?

I feel moderately confident about multithreading concepts now. I understand well how to create threads using the Runnable interface and how to start and join threads. I also have a good grasp of the Round-Robin scheduling algorithm and how context switching works between processes. I can explain the different thread states (New, Runnable, Running, Waiting, Terminated) and when a thread transitions between them. The concept of time quantum and how it affects system responsiveness is also clear to me.

However, I still need more practice with more advanced topics. I want to improve my understanding of thread safety and how to properly use synchronization to prevent data corruption when multiple threads access shared resources. I also need more experience with thread pools and executor services, which are more efficient than creating threads manually. Another area I want to practice is debugging multithreaded applications, as issues like race conditions are hard to reproduce and fix. Overall, this assignment gave me a solid foundation, and I feel ready to tackle more complex threading challenges in future projects.


---

### Feedback on the assignment

This assignment was extremely helpful for understanding how multithreading and CPU scheduling work in practice. The starter code was well-structured and the color-coded output made it easy to visualize the process execution. I found the three features I had to add (priority, context switch counter, waiting time) to be appropriately challenging - they required me to understand the existing code thoroughly before making modifications. The requirements to use GitHub with meaningful commits taught me good version control practices that I will use in my career. The video demonstration requirement was also valuable because it forced me to articulate my understanding clearly.

The assignment was not too difficult, but it required careful attention to detail. One suggestion for improvement would be to include a small test case with expected output so students can verify their code works correctly. Another suggestion is to add a bonus feature option for students who finish early, such as implementing a priority-based scheduling variant or calculating turnaround time. Overall, this was one of the most practical and engaging assignments I've completed, and I feel I learned a lot from it. The combination of coding, documentation, version control, and video presentation gave me a complete experience of software development workflow.
