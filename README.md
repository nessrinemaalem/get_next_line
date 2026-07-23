# get_next_line

A function that reads a text file (or any file descriptor, including `stdin`) line by line, one call at a time — written in pure C as part of the École 42 curriculum. Focuses on manual memory management and static/persistent state between calls.

## Signature

```c
char *get_next_line(int fd);
```

Each call returns the next line (including the trailing `\n`, except possibly on the last line), or `NULL` at end of file / on error.

## Features

- Works with any buffer size (`BUFFER_SIZE` configurable at compile time)
- Handles multiple file descriptors simultaneously (bonus)
- No memory leaks: internal static buffers are correctly freed across calls

## Build / use

```bash
gcc -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line.c get_next_line_utils.c your_file.c -o your_program
```

## Files

```
get_next_line.c / .h              mandatory part
get_next_line_bonus.c / .h        bonus: multiple fds handled at once
get_next_line_utils.c             string helpers (no libft allowed here)
```

## Constraints

Only `read`, `malloc`, and `free` are allowed. No `lseek`, no reading the whole file into memory at once.
