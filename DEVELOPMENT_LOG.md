# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

# Development Log - Student ID: 445050170

## Entry 1: March 20, 2026 - 9:00 PM
**What I worked on:**
- Created GitHub account using university email (445050170@std.psau.edu.sa)
- Forked the starter repository from the provided link
- Renamed repository to "OS-Assignment1-Hussam-Alamri"
- Set student ID (445050170) in SchedulerSimulation.java
- Made first commit with student ID modification

**Challenges encountered:**
- First time using GitHub, was confused about forking vs cloning
- Had to verify email before being able to fork

**Solutions implemented:**
- Watched a YouTube tutorial on GitHub basics
- Read the README.md file carefully which explained each step
- Download Apach NetBeans IDE 22 

**Time spent:** 45 minutes

---

## Entry 2: March 21, 2026 - 2:00 PM
**What I worked on:**
- Feature 1: Adding Priority field to Process class
- Modified Process class to include priority variable (1-5)
- Updated constructor to accept priority parameter
- Added getPriority() method
- Modified SchedulerSimulation to generate random priority for each process
- Updated addProcessToQueue method to display priority when process enters ready queue
- Updated ready queue display to show priority
- Made commit: "Feature 1: Added priority field to Process class"

**Challenges encountered:**
- Understanding where to generate the random priority value
- Making sure priority displays correctly in all output locations

**Solutions implemented:**
- Generated priority in the process creation loop using random.nextInt(5) + 1
- Added priority display in both addProcessToQueue and ready queue visualization
- Tested with multiple runs to ensure priority shows correctly

**Time spent:** 1 hour

---

## Entry 3: March 22, 2026 - 4:00 PM
**What I worked on:**
- Feature 2: Implementing Context Switch Counter
- Added static variable contextSwitchCount in SchedulerSimulation class
- Incremented counter before each process execution in the scheduler loop
- Added display at the end showing total context switches with formatted box
- Made commit: "Feature 2: Implemented context switch counter"

**Challenges encountered:**
- Deciding exactly where to increment the counter
- Understanding what counts as a context switch in Round-Robin scheduling

**Solutions implemented:**
- Researched context switch definition: when CPU switches from one process to another
- Placed counter increment right before starting each thread
- Verified count by comparing with number of process executions

**Time spent:** 45 minutes

---

## Entry 4: March 23, 2026 - 3:00 PM
**What I worked on:**
- Feature 3: Implementing Waiting Time Tracking
- Added creationTime and totalWaitingTime fields to Process class
- Added addWaitingTime(), getTotalWaitingTime(), getCreationTime() methods
- Created allProcesses list to store all processes for final summary
- Calculated waiting time when process is re-queued using System.currentTimeMillis()
- Added formatted summary table at the end showing each process with burst time and waiting time
- Made commit: "Feature 3: Added waiting time tracking and summary"

**Challenges encountered:**
- Calculating waiting time accurately without affecting process execution
- Ensuring waiting time accumulates correctly across multiple cycles
- Formatting the summary table properly with alignment

**Solutions implemented:**
- Used System.currentTimeMillis() to get accurate timestamps
- Stored creation time when process is first created
- Calculated waiting time only when process is re-queued (not when completed)
- Used printf with proper formatting for table alignment

**Time spent:** 1.5 hours

---

## Entry 5: March 24, 2026 - 7:00 PM
**What I worked on:**
- Testing all features together with multiple runs
- Fixed waiting time calculation bug (creation time was being reset incorrectly)
- Verified context switch counter accuracy
- Confirmed priority display works correctly for all processes
- Tested with different random seeds to ensure consistency
- Made commit: "Testing: Verified all three features work correctly"

**Challenges encountered:**
- Waiting time was showing incorrect values initially for some processes
- Some processes had waiting time of 0 when they should have waited

**Solutions implemented:**
- Realized that creation time was being reset when process was re-queued
- Fixed by only setting creation time in constructor, never resetting it
- Added additional print statements to debug timing calculations
- Tested with only 2 processes to isolate and verify waiting time logic

**Time spent:** 1 hour

---

## Entry 6: March 25, 2026 - 10:00 AM
**What I worked on:**
- Recording video demonstration (2 minutes 45 seconds)
- Updated all documentation files (DEVELOPMENT_LOG, REFLECTION, ANSWERS)
- Added video link to README.md
- Final testing before submission
- Made final commit: "Documentation: Completed all files and added video link"

**Challenges encountered:**
- Making video within 2-3 minutes while covering all requirements
- Ensuring good audio quality and clear screen recording
- Speaking clearly while explaining code and concepts

**Solutions implemented:**
- Practiced twice before final recording
- Created a script with bullet points to stay organized
- Used NVIDIA ShadowPlay for screen recording
- Tested microphone before recording to ensure clear audio

**Time spent:** 2 hours

---

## Summary

**Total time spent on assignment:** Approximately 7 hours and 15 minutes

**Most challenging part:** 
The waiting time tracking feature was the most challenging part of this assignment. I struggled to understand how to accurately calculate the time each process spent waiting in the queue without interfering with the actual execution. The main difficulty was ensuring that waiting time accumulated correctly across multiple cycles for processes that were re-queued multiple times. I initially made mistakes where creation time was being reset, causing incorrect waiting time values. Debugging this required careful tracing of when processes were created, when they ran, and when they were re-queued. I also found it challenging to format the final summary table correctly with proper alignment while maintaining the color-coded output style of the original code.

**Most interesting learning:** 
The most interesting thing I learned was how context switching actually works in a Round-Robin scheduler. Seeing the processes move through the ready queue and watching the context switch counter increase each time the CPU switched to a new process made the theoretical concept very tangible. I also found it fascinating how using a small time quantum (2-5 seconds in our simulation) creates the illusion of parallelism even though only one process runs at a time. Additionally, I learned the importance of careful timing calculations when tracking waiting times, and how small bugs in timestamp management can lead to completely wrong results. The visual progress bars and color-coded output also taught me how to make terminal output more user-friendly and informative.

**What I would do differently next time:** 
Next time, I would plan my commits better and make them more granular. While I made separate commits for each feature, I could have made smaller commits for each step within a feature (like commit after adding priority variable, then another commit after updating constructor, etc.). I would also start the documentation earlier rather than leaving most of it for the end. Keeping the DEVELOPMENT_LOG updated as I worked would have been easier than reconstructing it from memory. Additionally, I would spend more time testing edge cases, such as when all processes have the same priority or when some processes have very short burst times. Finally, I would set up my IDE with better debugging tools to help track thread execution more easily, as debugging multithreaded programs with print statements was sometimes inefficient.
