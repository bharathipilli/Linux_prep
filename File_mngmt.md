# FILE MANAGEMENT
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

## 1. What is a file in Linux?

A file is a collection of data stored on disk. In Linux, everything is treated as a file (regular files, directories, devices, sockets, pipes).

## 2️⃣ What are different types of files in Linux?

Regular file

Directory

Character device file

Block device file

FIFO (named pipe)

Socket

Symbolic link

## 3️⃣ What is a file descriptor?

A file descriptor (FD) is a non-negative integer returned by open() used to access a file.

0 → stdin

1 → stdout

2 → stderr

---

## 4️⃣ Difference between file descriptor and file pointer?
File Descriptor	File Pointer
Integer value	FILE *
Used in system calls	Used in stdio functions
No buffering	Buffered
---

## 5️⃣ What happens internally when we open a file?

Process calls open()

Kernel checks permissions

VFS layer identifies filesystem

Inode is loaded

File table entry created

File descriptor returned

## 6️⃣ What is an inode?

An inode stores metadata of a file:

File size

Permissions

Owner

Timestamps

Block pointers

It does not store filename.

## 7️⃣ What system calls are used in file handling?

open()

read()

write()

lseek()

close()

stat()

## 8️⃣ What is the difference between stat() and fstat()?
stat()	fstat()
Takes file path	Takes file descriptor
Works before opening	Works after opening

## 9️⃣ What is lseek()?

Used to change file offset (move file pointer).

Example:

lseek(fd, 0, SEEK_SET);  // move to beginning

## 🔟 What is buffering?

Buffering temporarily stores data in memory before writing to disk to reduce system calls.

1️⃣1️⃣ What is a sparse file?

A file that has empty blocks (holes) not physically stored on disk but logically present.

1️⃣2️⃣ What is file permission in Linux?

Three types:

Read (r)

Write (w)

Execute (x)

Applied to:

User

Group

Others

Example: rwxr-xr--

1️⃣3️⃣ What is umask?

umask sets default permission bits when creating new files.

1️⃣4️⃣ What is VFS?

Virtual File System layer provides a common interface to different filesystems (ext4, ntfs, etc.).

1️⃣5️⃣ What is difference between character and block device?
Character Device	Block Device
Data byte by byte	Data in blocks
No buffering	Uses buffer cache
Example: keyboard	Example: hard disk
1️⃣6️⃣ What is a hard link?

Points to same inode

Shares same data

Cannot link directories

1️⃣7️⃣ What is a soft link (symbolic link)?

Points to filename

Has different inode

Can link directories

1️⃣8️⃣ What happens if two processes write to same file?

Data may interleave

Use file locking (flock, fcntl) to avoid corruption

1️⃣9️⃣ What is file locking?

Mechanism to prevent multiple processes from modifying file simultaneously.

2️⃣0️⃣ What is mmap() in file handling?

Maps file into process virtual memory, allowing file access like memory.
