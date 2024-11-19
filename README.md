# get_next_line

## Description
Get Next Line (GNL) is a function that reads a line from a file descriptor. When called in a loop, get_next_line returns the file's content line by line. This project is part of the 42 Network cursus and helps understand file descriptors, static variables, and memory management in C.

## Function Prototype
```c
char *get_next_line(int fd);
```

## Returns
- Read line: correct behavior
- NULL: nothing else to read or an error occurred

## Compilation
```bash
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line.c get_next_line_utils.c
```

## Files
- `get_next_line.c`
- `get_next_line.h`
- `get_next_line_utils.c`

## Example Usage
```c
#include "get_next_line.h"
#include <fcntl.h>

int main(void)
{
    int     fd;
    char    *line;

    fd = open("example.txt", O_RDONLY);
    while ((line = get_next_line(fd)))
    {
        printf("%s", line);
        free(line);
    }
    close(fd);
    return (0);
}
```

## Features
- Handles multiple file descriptors
- Memory efficient
- Norm compliant
- No memory leaks
