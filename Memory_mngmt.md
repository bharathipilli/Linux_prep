1. What is a Process?

A program in execution.

Has its own virtual address space.

Needs memory to store:

Code (text)

Data

Stack

Heap

✔️ 2. What is RAM vs Hard Disk?
RAM	Hard Disk
Very fast	Very slow
Volatile	Non-volatile
Directly accessed by CPU	Cannot be directly executed

⚠️ CPU cannot execute instructions directly from hard disk.

This is very important.

🔹 2️⃣ Conceptual Questions You Must Understand
❓ Q1: Why don’t we execute programs directly from Hard Disk?
✅ Answer:

Because:

Hard disk is extremely slow compared to RAM.

CPU can only access data through memory (RAM).

Hard disk is secondary storage.

RAM is connected to CPU via memory bus.

📌 Real-time example:

Imagine:

RAM = your study table

Hard disk = cupboard

You cannot solve problems directly from cupboard.
You first bring book to table.

Same way:
Program → loaded into RAM → then executed.

❓ Q2: If RAM is limited, how do we run large programs?
✅ Answer:

That is why Virtual Memory exists.

Virtual memory:

Gives illusion of large memory.

Uses disk space as extension of RAM.

Loads only required parts into RAM.

🔹 3️⃣ Important Virtual Memory Concepts (Interview Format)
❓ Q3: What is Virtual Memory?
✅ Answer:

Virtual memory is a memory management technique that:

Allows execution of large programs.

Uses disk as backup for RAM.

Provides isolation between processes.

Gives each process its own virtual address space.

❓ Q4: What is Paging?
✅ Answer:

Paging is a memory management technique where:

Virtual memory is divided into pages

Physical memory is divided into frames

Pages are mapped to frames

Page size = Frame size

❓ Q5: Why Paging is needed?
✅ Answer:

Eliminates external fragmentation.

Allows non-contiguous memory allocation.

Enables virtual memory.

Simplifies memory management.

❓ Q6: What is Page Table?
✅ Answer:

Page table is a data structure maintained by OS that:

Maps virtual page number → physical frame number.

It contains:

Frame number

Valid/Invalid bit

Dirty bit

Access permissions

Reference bit

❓ Q7: What is MMU?
✅ Answer:

MMU (Memory Management Unit):

Hardware component.

Converts virtual address → physical address.

Uses page table.

❓ Q8: What is TLB?
✅ Answer:

TLB (Translation Lookaside Buffer):

Cache for page table entries.

Speeds up address translation.

Reduces memory access time.

❓ Q9: What is Page Fault?
✅ Answer:

Page fault occurs when:

Requested page is not in RAM.

Steps:

CPU generates interrupt.

OS loads page from disk to RAM.

Page table updated.

Process resumes.

❓ Q10: What is Thrashing?
✅ Answer:

Thrashing happens when:

Too many page faults.

System spends more time swapping than executing.

🔹 4️⃣ Important Address Translation Concept

Very important for mock:

Logical Address = (Page number + Offset)

Virtual Address Structure:

| Page Number | Offset |


Physical Address:

| Frame Number | Offset |


MMU replaces:
Page number → Frame number
Offset remains same.

🔹 5️⃣ Very Important Basic Questions Interviewer May Ask

Here are some beginner-friendly mock questions:

🔹 What is fragmentation?

Internal fragmentation

External fragmentation

🔹 Difference between Paging and Segmentation?
Paging	Segmentation
Fixed size	Variable size
No external fragmentation	Has external fragmentation
Based on memory	Based on logical units
🔹 What is Demand Paging?

Load page only when required.

🔹 What is Swap Space?

Disk area used to store pages temporarily.

🔹 Why page size matters?

Large page size:

Less page table entries

More internal fragmentation

Small page size:

Less internal fragmentation

Bigger page table
