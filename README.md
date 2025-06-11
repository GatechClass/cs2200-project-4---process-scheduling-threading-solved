# cs2200-project-4---process-scheduling-threading-solved
**TO GET THIS SOLUTION VISIT:** [CS2200 Project 4 – Process Scheduling & Threading Solved](https://mantutor.com/product/cs-2200-systems-and-networking-solved-7/)


---

**For Custom/Order Solutions:** **Email:** mantutorcodes@gmail.com  

*We deliver quick, professional, and affordable assignment help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;112904&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;3&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (3 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;CS2200 Project 4 - Process Scheduling \u0026amp; Threading Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (3 votes)    </div>
    </div>
Project 4: Process Scheduling Simulation

1 Overview

In this project, you will implement a multiprocessor operating system simulator using a popular threading library for Linux called pthreads. The framework for the multiprocessor OS simulator is nearly complete, but missing one critical component: the process scheduler! Your task is to implement the process scheduler and three different scheduling algorithms.

The simulated operating system supports only one thread per process making it similar to the systems that we discussed in Chapter 6. However, the simulator itself will use a thread to represent each of the CPUs in the simulated hardware. This means that the CPUs in the simulator will appear to operate concurrently.

We have provided you with source files that constitute the framework for your simulator. You will only need to modify answers.txt and student.c. However, it is in your best interest to read and understand the other files, and it will make it much easier to implement the functions in student.c.

We have provided you the following files:

1. os-sim.c – Code for the operating system simulator which calls your CPU scheduler.

2. os-sim.h – Header file for the simulator.

3. process.c – Descriptions of the simulated processes.

4. process.h – Header file for the process data.

5. student.c – This file contains stub functions for your CPU scheduler.

6. student.h – Header file for your code to interface with the OS simulator. Also contains the ready queue struct definition.

7. answers.txt – This is a text file that you should use to write your answers to the questions listed throughout the PDF.

1.1 Scheduling Algorithms

For your simulator, you will implement the following three CPU scheduling algorithms:

1. First Come, First Serve (FCFS) – Runnable processes are kept in a ready queue. FCFS is nonpreemptive; once a process begins running on a CPU, it will continue running until it either completes or blocks for I/O. The process with the earliest arrival time in the ready queue will be the next process selected. It is highly recommended to read the textbook section on FCFS before starting.

1

moved to the tail of the ready queue. It is highly recommended to read the textbook section on Round Robin before starting.

3. Preemptive Priority Scheduling with Aging – Processes with higher priority get to run first and processes with lower priority get preempted for a process with higher priority. There is a caveat, though. Our priority scheduler factors in the age of a process when determining priority.

1.2 Process States

In our OS simulation, there are five possible states for a process. These states are listed in the process state t enum in os-sim.h:

1. NEW – The process is being created, and has not yet begun executing.

2. READY – The process is ready to execute, and is waiting to be scheduled on a CPU.

3. RUNNING – The process is currently executing on a CPU.

4. WAITING – The process has temporarily stopped executing, and is waiting for an I/O request to complete.

5. TERMINATED – The process has completed.

There is a field named state in the PCB, which must be updated with the current state of the process. The simulator will use this field to collect statistics.

Figure 1: Process States

1.3 The Ready Queue

On most systems, there are a large number of processes that need to share the resources of a small number of CPUs. When there are more processes ready to execute than CPUs, processes must wait in the READY state until a CPU becomes available. To keep track of the processes waiting to execute, we keep a ready queue of the processes in the READY state.

1.4 Scheduling Processes

Note that in a multiprocessor environment, we cannot mandate that the currently running process be at the head of the ready queue. There is an array (one entry for each CPU) that will hold the pointer to the PCB currently running on that CPU.

1.5 CPU Scheduler Invocation

1. yield() – A process completes its CPU operations and yields the processor to perform an I/O request.

2. wake up() – A process that previously yielded completes its I/O request, and is ready to perform CPU operations. wake up() is also called when a process in the NEW state becomes runnable.

4. terminate() – A process exits or is killed.

5. idle() – Waits for a new process to be added to the ready queue. idle() contains the code that gets executed by the idle process. In the real world, the idle process puts the processor in a low-power mode and waits. For our OS simulation, you will use a pthread condition variable to block the thread until a process enters the ready queue.

1.6 The Simulator

We will use pthreads to simulate an operating system on a multiprocessor computer. We will use one thread per CPU and one thread as a ‘supervisor’ for our simulation. The supervisor thread will spawn new processes (as if a user started a process). The CPU threads will simulate the currently-running processes on each CPU, and the supervisor thread will print output.

Since the code you write will be called from multiple threads, the CPU scheduler you write must be threadsafe! This means that all data structures you use, including your ready queue, must be protected using mutexes.

The number of CPUs is specified as a command-line parameter to the simulator. For this project, you will be performing experiments with 1, 2, and 4 CPU simulations.

Also, for demonstration purposes, the simulator executes much slower than a real system would. In the real world, a CPU burst might range from one to a few hundred milliseconds, whereas in this simulator, they range from 0.2 to 2.0 seconds.

Figure 2: Simulator Function Calls

The above diagram should give you a good overview of how the system works in terms of the functions being called and PCBs moving around.

Below is a second diagram that shows the entire system overview and the code that you need to write is inside of the green cloud at the bottom. All of the items outside of the green cloud are part of the simulator and will not need to be modified by you.

Figure 3: System overview Compile and run the simulator with ./os-sim 2. After a few seconds, hit Control-C to exit. You will see the output below:

Figure 4: Sample Output

The simulator generates a Gantt Chart, showing the current state of the OS at every 100ms interval. The leftmost column shows the current time, in seconds. The next three columns show the number of Running, Ready, and Waiting processes, respectively. The next two columns show the process currently running on each CPU. The rightmost column shows the processes which are currently in the I/O queue, with the head of the queue on the left and the tail of the queue on the right.

As you can see, nothing is executing. This is because we have no CPU scheduler to select processes to execute! Once you complete Problem 1 and implement a basic FCFS scheduler, you will see the processes executing on the CPUs.

2 Problem 0: The Ready Queue

We have provided simple implementations of queue t, enqueue(), dequeue(), and is empty() in student.c. The struct you have to implement will serve as your ready queue, and you should be using these helper functions to add and remove processes from the ready queue in the problems to follow.

2.1 Provided Queue

• enqueue() will add a process to the ready queue.

• dequeue() will find the next process to remove according to the scheduling algorithm, remove it from the queue, and return a pointer to it.

• NOTE: When using the ready queue helper functions in the following problems, make sure to call them in a thread-safe manner. Read up on how to use mutex locks and lock/unlock the mutex for the ready queue when you call these functions. You might need to modify the enqueue() and dequeue() function to support the different scheduling algorithms as you move forward in the project.

3 Problem 1: FCFS Scheduler

• Implement the yield(), wake up(), and terminate() handlers. in student.c.

Checkout the hints in section 3.3, and note that preempt() is not necessary for this stage of the project. • Implement idle().

idle() must wait on a condition variable that is signalled whenever a process is added to the ready queue.

3.1 Hints

• Be sure to update the state field of the PCB in all the methods above. The library will read this field to generate the RUNNING (Ru), READY (Re), and WAITING (Wa) columns, and to print the statistics at the end of the simulation.

• context switch() takes a timeslice parameter, which is used for preemptive scheduling algorithms. Since FCFS is non-preemptive, use -1 for this parameter to give the process an infinite timeslice. • Make sure to use the helper functions in a thread-safe manner when adding and removing processes from the ready queue!

• The current[] array should be used to keep track of the process currently executing on each CPU. Since this array is accessed by multiple CPU threads, it must be protected by a mutex. current mutex has been provided for you.

4 Problem 2: Round-Robin Scheduler

Add Round-Robin scheduling functionality to your code. Alter the provided enqueue() and dequeue() to support round robin. You should modify main() to add a command line option, -r, which selects the Round-Robin scheduling algorithm, and accepts a parameter, the length of the timeslice. For this project, timeslices are measured in tenths of seconds. E.g.:

./os-sim &lt;# CPUs&gt; -r 5

should run a Round-Robin scheduler with timeslices of 500 ms. While:

./os-sim &lt;# of CPUs&gt;

should continue to run a FCFS scheduler. Note: you can use getopt(), which we used earlier in the semester or just parse the command line arguments passed into main using if statements.

Implement preempt().

To specify a timeslice when scheduling a process, use the timeslice parameter of context switch(). The simulator will simulate a timer interrupt to preempt the process and call your preempt() handler if the process executes on the CPU for the length of the timeslice without terminating or yielding for I/O.

5 Problem 3: Preemptive Priority Scheduling with Aging

Add Priority with Aging scheduling to your code. Alter the provided enqueue() and/or dequeue() to support priority with aging. Modify main() to accept the -p parameter to select the Priority Scheduling with Aging algorithm. The command line argument will follow this format. ./os-sim &lt;num CPUs&gt; -p &lt;age weight&gt;. Take a look at your homework 4 if you are struggling with this.

Implement the function priority with age(). Each process has a base priority, however, we need to factor in its age to give us the processes’ functional priority. To do this, we must understand a few variables.

1. current time is a running time function that tells us how long it has been since our simulator has been booted up. We can obtain this value by simply calling the function get current time().

2. enqueue time is a value in the PCB that tells us when the process was put into the ready queue. We update this every time we enqueue a process.

3. age weight is an argument that is passed in from the command line. This value determines how much priority a process gains per unit age.

To calculate our functional priority use the equation

functional priority = base priority + (current time − enqueue time) ∗ age weight

When a process is awakened, and all CPU cores are currently occupied by running processes, we preempt the lowest priority process if its priority is lower than that of the newly awakened process. Subsequently, we add this preempted process to the ready queue.

NOTE: Contrary to modern operating systems, higher number means higher priority..

Figure 5: Example Ready Queue

The above ready queue is an example of our priority with aging algorithm. Our example simulator is at current time 15, has an age weight of .2, and four processes in its ready queue. Notice the following:

• Process 1 is earlier in the queue than process 2, yet process 2 has a higher functional priority.

• Process 4 has a higher base priority than process 3, yet process 3 has a higher functional priority.

• Process 2 and 4 have the same base priority, yet process 2 has a much higher functional priority.

6 Problem 4: Short Answers

Please write your answers to the following questions in answers.txt.

6.1 FIFO Scheduler

Run your OS simulation with 1, 2, and 4 CPUs. Compare the total execution time of each. Is there a linear relationship between the number of CPUs and total execution time? Why or why not? Keep in mind that the execution time refers to the simulated execution time.

6.2 Round-Robin Scheduler

Run your Round-Robin scheduler with timeslices of 800ms, 600ms, 400ms, and 200ms. Use only one CPU for your tests. Compare the statistics at the end of the simulation. Is there a relationship between the total waiting time and timeslice length? If so, what is it? In contrast, in a real OS, the shortest timeslice possible is usually not the best choice. Why not?

6.3 Preemptive Priority Scheduler

Priority schedulers can sometimes lead to starvation among processes with lower priority. What is a way that operating systems can mitigate starvation in a priority scheduler?

6.4 Priority Inversion

Consider a non-preemptive priority scheduler. Suppose you have a high-priority process (P1) that wants to display a window on the monitor. But, the window manager is a process with low priority and will be placed at the end of the ready queue. While it is waiting to be scheduled, new medium-priority processes are likely to come in and starve the window manager process. The starvation of the window manager will also mean the starvation of P1 (the process with high priority), since P1 is waiting for the window manager to finish running.

If we want to keep our non-preemptive priority scheduler, what edits can we make to our scheduler to ensure that the P1 can finish its execution before any of the medium priority processes finish their execution? Explain in detail the changes you would make.

7 The Gradescope Environment

You will be submitting files to Gradescope, where they will be tested in a VM setup that runs through Gradescope. The specifications of this VM are that it runs Ubuntu 20.04 LTS (64-bit) and gcc 9.3.0, and so we expect that your files can run in such a setup. This means that when you are running your project locally, you will want to ensure you are using a VM/some setup that runs Ubuntu 20.04 LTS (64-bit) and gcc 9.3.0; this way, you can ensure that what occurs locally is what will occur when you submit to Gradescope.

IMPORTANT: Since we are dealing with different threads of execution, the result of each run in the simulation will be different. As a result, our gradescope autograder will accept a range of results for your simulation. In past semesters, we found that the range will start to increase the more computations you do in your enqueue/dequeue methods. If you find that you aren’t passing the autograder but you believe that your code is right, it is likely that you need to trim down your enqueue/dequeue methods. We are planning to start our autograder with a tighter acceptable range, and if required, we will increase it.

8 Deliverables

NOTE: You need to upload student.c, and answers.txt to Gradescope, and an autograder will run to check if your scheduler is working. The autograder might take a couple of minutes to run. Remember to upload student.c, and answers.txt for every submission as your last submission would be one we will grade.

Keep your answers detailed enough to cover the question, including support from simulator results if appropriate. Don’t write a book; but if you’re not sure about an answer, give us more information.

9 How to Run / Debug Your Code – Debugging deadlocks and synchronization errors

9.1 Running

We have provided a Makefile that will run gcc for you. To compile your code with no optimizations (which you should do while developing, it will make debugging easier) and test with the FCFS algorithm and one CPU, run: $ make debug

$./ os−sim 1

To run the other algorithms, run with the flags you implemented for round robin and priority. Remember that round robin requires you to enter a time slice.

In case you encounter difficulties with Project 4 and are uncertain about the direction to take, various resources are available to assist you.

9.2 GDB

Let us investigate how to debug deadlocks through a basic example:

Following the execution and compilation of the code, it appears to become unresponsive. To investigate the root cause of this issue, it is recommended to utilize the GNU Debugger (gdb) to identify the problem:

As anticipated, the program continues to remain unresponsive when run within the gdb environment. To interrupt the program, press Ctrl + c. To analyze the various threads associated with the program, utilize the ”info threads” command within gdb, which provides detailed information regarding each active thread:

function. To obtain the backtrace of these threads, we can use the ”thread apply all” command along with the ”backtrace” command, which can be abbreviated as ”t a a bt”.

The backtrace command confirms that threads 2 and 3 are indeed stuck at the pthread mutex lock function. To gain a more in-depth understanding of the specific thread’s state, we can utilize the gdb command ”thread [thread number]” to switch to a particular thread and examine its current state.

By switching to thread 3 within gdb, we can identify the precise line of code where it has become deadlocked. Once we have identified the problematic line, we can utilize gdb’s features, such as printing values or switching stack frames, to investigate further and gain a better understanding of the issue at hand. Read the gdb thread documentation here for more information.

9.3 Valgrind (Helgrind or DRD)

Lets run Helgrind with the command ’valgrind tool=helgrind &lt;program&gt;’. This is the result:

Upon executing Valgrind’s tool Helgrind, we can observe that it has successfully identified an issue within the program where thread2 is accessing a shared variable without acquiring a corresponding lock. Additionally, DRD (another tool within Valgrind) also provides comparable output, albeit with fewer error lines. It is essential to rectify these issues to ensure proper synchronization and avoid potential data race conditions. To compare, here is the same program run with DRD (’valgrind tool=drd &lt;program&gt;’):

Valgrind and DRD are also able to debug other types of synchronization errors. You can read the documentation about Helgrind here and DRD here.

Credit to this video from an old class.

9.4 Tips and Tricks

1. When implementing enqueue() and dequeue(), think about all the possible edge cases. For example, how would you handle a case where both the head and tail are pointing to the same process?

2. When you dequeue, remember to set the next pointer of the removed process to null.

3. If you are deadlocking, utilize GDB. Follow the instructions above to understand the current state of the threads and pinpoint the issues. Think about whether you are properly locking and unlocking threads at the correct points in time. Utilize backtrace.

4. Make sure you are setting the state based on the handler/function. Take a look at Figure 1 to understand what state should be set when.

5. Make sure you are setting the enqueue time whenever you enqueue a process.

6. In wake up(), make sure your final decision on whether to force preempt is based on priority with age.

7. When unlocking/locking, don’t mix up current mutex and queue mutex.

8. Utilize your approach for parsing command line arguments in HW 4 for Part 4.
