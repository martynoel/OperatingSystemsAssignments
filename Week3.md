# Week 3: Processes

### Warmups 3.1, 3.2, 3.3, 3.4

### 3.1) Using the program shown in Figure 3.30, explain what the output will be at LINE A.

```C
#include <sys/types.h> 
#include <stdio.h> 
#include <unistd.h>

int value = 5; 

int main()
{
  pid_t pid;
  pid = fork();
  if (pid == 0) { /* child process */ 
    value += 15;
    return 0;
  } else if (pid > 0) { /* parent process */ 
      wait(NULL);
      printf("PARENT: value = %d",value); /* LINE A */ 
      return 0;
  }
}
```

The output will be `"PARENT: value = 5"`: The value of the parent node.

### 3.2) Including the initial parent process, how many processes are created by the program shown in Figure 3.31?

```C
#include <stdio.h> 
#include <unistd.h>

int main()
{
  /* fork a child process */
  fork();
  /* fork another child process */
  fork();
  /* and fork another */
  fork();
  return 0;
}
```

8 processes are created. Both the parent and the child process execute the code after the `fork()` call.

### 3.3) Original versions of Apple’s mobile iOS operating system provided no means of concurrent processing. Discuss three major complications that concurrent processing adds to an operating system.


1. Memory usage and distribution -- the OS has to allocate each process the fair amount of space, and record which process has what space, in order to keep processes from corrupting other processes' data.

2. Time overhead -- one process may take too long to run and free up resources

3. Switching processes is complicated -- to switch from one process to another, the OS must remember the register values of the current process in memory and load the next process's register value from its PCB.

### The Sun UltraSPARC processor has multiple register sets. Describe what happens when a context switch occurs if the new context is already loaded into one of the register sets. What happens if the new context is in memory rather than in a register set and all the register sets are in use?

If the new context is already loaded into one of the register sets when a context switch happens, the CPU's pointer to the current register set is changed to the register set that the new context is in. If the new context is in memory rather than in a register set, and all the register sets happen to be in use, one of the register sets will be freed up (the context in that register set will be moved to memory, and the new context will be moved to the register set from memory). 

### Exercises 3.8, 3.10, 3.13, 3.14, 3.18

### 3.8) Describe the differences among short-term, medium-term, and long- term scheduling.

Short-term scheduling -- Selects a process that is already loaded into memory and allows it to use the CPU. Selects processes often.

Medium-term scheduling -- Removes processes in the ready or blocked queue from memory, and restores them later.

Long-term scheduling -- Selects the processes to run. This may take a while, because processes may take a while to run before completing. 

### 
