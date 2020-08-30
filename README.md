# Syscalls code-reading questions

## Objectives

By the time you complete this assignment, you should be able to:
- Discover important design aspects of OS/161 by examining its code base

## Assignment description
The goal of this assignment is to introduce you to the OS/161 code. You are already a bit familiar with OS/161 after setting up your virtual machine and learning how to configure and build OS/161 kernels. OS/161 is a simplified skeleton of a modern operating system. It comes with a configurable build system, code for some useful user-level utilities that can be run from within OS/161, and of course code for the operating system itself. 

Some of the assignments in CSE4001 will be related to OS/161. To complete these OS/161-related assignments, you will need to get your hands deep in the guts of the OS/161 codebase, and the sooner you become familiar with it, the better. To that end, you should look through the files and begin to learn how the code is structured, what goes where, and how things work. This applies both to the build system and the codebase itself.

To guide you in this process, please write up and hand in answers to the questions found below.  

**Note**: in these questions, and throughout the course of the semester, we will refer to the terms "trap", "interrupt", "exception", and "system call". Although these terms might take on different meanings in different classes, in OS/161, they mean the following:

- We use "trap" as a generic term of transferring control into the kernel.
- We use "exception" for events that are synchronous with respect to user processes and cause a trap into the kernel: these include things like divide-by-0 or NULL pointer dereference exceptions and the trap caused by the syscall instruction in MIPS.
- We use "interrupt" for asynchronous events that cause a trap into the kernel: this includes things like interrupts from the serial console hardware, the timer hardware, etc.
- We use "system call" for synchronous requests user processes make to request service from the OS: system calls are invoked using traps -- specifically using the syscall instruction on MIPS.



## Working with markdown

Most OS/161 assignments in CSE4001 require you to write using the markdown format. A good interactive tutorial on how to use markdown is available from the following link: 

https://www.markdowntutorial.com

Alternatively, you can also simply learn from this README.md markdown file. This README.md contains most of the features that you will need to use for CSE4001 (i.e., create sections with headers, add figures, add code extracts). To learn how a markdown file is write, just open and study this README.md file.

To edit markdown files, you can use a basic source-code editor (i.e., ASCII text editor) or an actual markdown editor. Some online markdown editors are: https://stackedit.io, https://dillinger.io/, and https://jbt.github.io/markdown-editor/.

# Displaying code extracts in markdown

The following markdown pattern shows a code extract in C++:
````markdown
```cpp
void *threadA ( void *ptr )
{
    printf("Statement A \n");
    fflush(stdout);
    pthread_exit(0); 
}
```
````
which will be rendered as: 
```cpp
void *threadA ( void *ptr )
{
    printf("Statement A \n");
    fflush(stdout);
    pthread_exit(0); 
}
```

Use the following markdown pattern to add a figure to a markdown text: 

```markdown
![](Ubuntu_16.04_Desktop.png)
```

which will be rendered as: 
![](Ubuntu_16.04_Desktop.png)



## Begin your assignment 

1. Configure your kernel for assignment ASST1. For some OS/161 assignments, the *configuration file* will be provided to you as part of the repository. For this first assignment, you will simply create a new kernel-configuration file by duplicating an existing configuration file by calling the following commands on your Linux terminal: 

```shell
cd kern/conf  
cp DUMBVM ASST1
./config ASST1
``` 

The `./config` script will create a new configuration directory. You should now see an `ASST1` directory in the `kern/compile/` directory.

2. Clone the assignment repository. 
3. Write your answers into the markdown file `OS161_CodeReading01.md`. Illustrate your answers with relevant code extracts from OS/161 and with screenshots of the kernel running. 
4. Commit and push all changes into the assignment's GitHub repository. Remember that **all new files that you create must be "git added" prior to committing**. Also, all images referred by the markdown must also be uploaded into the repository so they can be displayed properly by the markdown renderer. 

