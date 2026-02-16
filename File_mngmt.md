#FILE MANAGEMENT
## Basic i/o vs Standard i/o
| Feature        | Basic I/O Calls (System Calls)           | Standard I/O Calls (Library Functions)                    |
| -------------- | ---------------------------------------- | --------------------------------------------------------- |
| Also Called As | Low-level I/O                            | High-level I/O                                            |
| Provided By    | Kernel (OS)                              | C Standard Library                                        |
| Header File    | `<unistd.h>`                             | `<stdio.h>`                                               |
| Examples       | `open()`, `read()`, `write()`, `close()` | `fopen()`, `fread()`, `fwrite()`, `fclose()`, `fprintf()` |
| Works With     | File Descriptor (int)                    | File Pointer (`FILE *`)                                   |
| Buffering      | No buffering (direct system call)        | Buffered (uses user-space buffer)                         |
| Performance    | Slower (each call enters kernel mode)    | Faster (due to buffering)                                 |
| Control        | More control over file handling          | Easier to use                                             |
| Usage Level    | System programming                       | Application programming                                   |
| Portability    | POSIX dependent                          | More portable (C standard)                                |

## 
