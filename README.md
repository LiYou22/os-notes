# Operating Systems Notes

LaTeX notes for CSCI-GA 2250-002 (Operating Systems), NYU Courant, Fall 2026, Dr. Yang Tang. The compiled notes are in `os-notes.pdf`.

## Chapters

1. **Introduction**: what an OS is, interrupts and system calls, kernel and user mode, the basic abstractions (processes, files, address spaces, protection).
2. **Process Management**: from program to process, `fork`/`exec`/`wait`, the kernel's view of a process and system call internals, signals, booting and the process tree, scheduling, IPC, critical sections and semaphores, classical IPC problems, threads, deadlocks.
3. **File Systems**: files, attributes, and directories; contiguous, linked, FAT, and inode allocation; free-space management and on-disk metadata; FAT32 and ext2/3/4 in action; the Linux VFS; the buffer cache; crash consistency, `fsck`, and journaling; RAID.

Appendix: A. quick reference for the system calls.
