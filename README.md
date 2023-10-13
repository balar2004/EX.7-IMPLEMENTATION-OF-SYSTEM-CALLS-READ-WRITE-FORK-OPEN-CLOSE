# EX.7-IMPLEMENTATION-OF-SYSTEM-CALLS-READ-WRITE-FORK-OPEN-CLOSE
## Aim:
C program using open, read, write, close , create , fork() system calls.
## Algorithm:
1. Star the program.
2. Open a file for O_RDWR for R/W,O_CREATE for creating a file ,O_TRUNC for truncate a file.
3. Using getchar(), read the character and stored in the string[] array.
4. The string [] array is write into a file close it.
5. Then the first is opened for read only mode and read the characters and displayed it and close the file.
6. Use Fork().
7. Stop the program.
## Program:
```
#include <sys/stat.h>
#include <stdio.h>
#include <fcntl.h>
#include <sys/types.h>
#include <unistd.h>
int main()
{
    int n, i = 0;
    int f1, f2;
    char c, strin[100];
    f1 = open("data", O_RDWR | O_CREAT | O_TRUNC, 0666);
    while ((c = getchar()) != '\n')
    {
        strin[i++] = c;
    }
    strin[i] = '\0';
    write(f1, strin, i);
    close(f1);
    f2 = open("data", O_RDONLY);
    n = read(f2, strin, 100);
    close(f2);
    strin[n] = '\0';
    printf("\n%s\n", strin);
    return 0;
}
```
## Output:
![read](https://github.com/balar2004/EX.7-IMPLEMENTATION-OF-SYSTEM-CALLS-READ-WRITE-FORK-OPEN-CLOSE/assets/118791778/04b95ed8-0668-46f3-8c20-a1694981e134)
## Result:
Thus, open, read, write, close , create , fork() system calls implemented successfully using c
program.
