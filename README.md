# Operating Systems — Course Notes

LaTeX notes for CSCI-GA 2250-002 (Operating Systems), NYU Courant, Fall 2026, taught by Dr. Yang Tang. Notes by You Li.

Each chapter follows one slide deck of the course, with one section per topic. Chapter 1 covers *1 — Introduction*; Chapter 2, Process Management, currently covers slides 2–162 of *2 — Process Management*. Sections marked (SUPPLEMENT) go beyond the slides; figures captioned "after slide n" redraw the corresponding slide in TikZ. Supplements draw on Bryant & O'Hallaron, *Computer Systems: A Programmer's Perspective*; Arpaci-Dusseau, *Operating Systems: Three Easy Pieces*; and Tanenbaum & Bos, *Modern Operating Systems*.

## Layout

```
main.tex          title page, notation, bibliography; includes the chapters
osnotes.sty       page layout, boxed definition/key-point environments, figure styles
chapters/
  ch1-introduction.tex         Chapter 1: reading list, roadmap; inputs intro/
  intro/
    01-what-is-os.tex          where the OS fits, the ls walkthrough, extended machine vs. resource manager
    02-interacting.tex         interrupts, system calls vs. library calls, kernel/user mode, fopen() walkthrough
    03-abstractions.tex        processes and the shell, files, address spaces, protection; course map
  ch2-process-management.tex   Chapter 2: reading list, roadmap; inputs process/
  process/
    01-program-to-process.tex  build pipeline, static/dynamic linking, what a process is
    02-fork-exec.tex           fork(), the exec*() family, system(), wait(), copy-on-write
    03-kernel-view.tex         task_struct, file descriptors and dup2(), syscall handling, process time
    04-syscall-internals.tex   fork/execve/exit/wait in the kernel, zombies
    05-signals.tex             signals, job control, kill(), signal(), pause(), alarm()
    06-organization.tex        booting, init, orphans and reparenting, the process tree
    07-scheduling.tex          process states, context switching, FCFS/SJF/PSJF/RR, priority scheduling, MLFQ
  appA-syscalls.tex            Appendix A: system call reference
```

## Build

Requires a TeX Live installation with `latexmk`.

```sh
latexmk -pdf main.tex   # produces main.pdf
latexmk -c              # remove intermediate files
```

To add a topic to a chapter, create a section file such as `chapters/process/08-ipc.tex` starting with `\section{...}` and `\input` it from the chapter file. To add a chapter (a new slide deck), create `chapters/chN-topic.tex` starting with `\chapter{...}`, put its sections in `chapters/<topic>/`, and add `\include{chapters/chN-topic}` to `main.tex`.
