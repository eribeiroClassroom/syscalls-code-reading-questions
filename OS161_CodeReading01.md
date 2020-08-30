#### OS/161 Code Reading, Traps, Interrupts, System Calls, and Debugging Practice

**Questions**:

1. Traps and interrupts are mechanisms used to transfer control between user-level processes and the operating system. Tell us where we can find the first C-language function of OS/161 that is executed when a trap occurs. Then, tell us where control gets transferred to from that point (i.e., what function services the trap). Be sure to describe the control flow for each type of trap that may occur (e.g., system calls, VM faults, and hardware interrupts).

> Answer: 
>
> 


2. Where is the trapframe constructed for the first time? 

> Answer: 
>
> 



3. Each OS/161 exception has its own code. What are the exception codes for the exceptions: **interrupt**, **system call**, and **arithmetic overflow**?

> Answer: 
>
> 


4. What information is saved in **struct trapframe**?

> Answer: 
>
> 



5. What is the name of the c-language function that plays the role of the system-call handler in OS/161? In which directory is this function implementation located?

> Answer: 
>
> 


6. One of the kernel's main function is to provide support for user-level programs. Most such support is accessed via "system calls”. For example, consider the system call **reboot()**, which is implemented in the function **sys_reboot()** in *src/kern/main/main.c*. Using GDB, put a breakpoint on **sys_reboot** and then run the "reboot" program (by typing "p /sbin/reboot" at the OS/161 menu prompt). Use "backtrace" to see how the OS/161 got there. **Show the output of your debugging session as well as the output printed by the OS/161.**

> Answer: 
>
> 

