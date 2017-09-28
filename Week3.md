# Week 3: Processes

### Using the program shown in Figure 3.30, explain what the output will be at LINE A.

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
