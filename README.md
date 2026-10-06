# Operating Systems Notes

My LaTeX notes for CSCI-GA 2250-002 (Operating Systems) at NYU Courant, Fall 2026, taught by Dr. Yang Tang.

I write one chapter per slide deck and split each chapter into sections by topic. So far there are two chapters: the introduction deck, and Process Management up to slide 162. Figures captioned "after slide n" are my TikZ redraws of that slide. Sections marked (SUPPLEMENT) are things I looked up outside the slides, mostly in CS:APP (Bryant & O'Hallaron), OSTEP (Arpaci-Dusseau), and Tanenbaum & Bos.

## Files

```
main.tex          title page, notation, bibliography
osnotes.sty       layout, the boxed environments, figure styles
chapters/
  ch1-introduction.tex         Chapter 1 (reading list and roadmap; sections are in intro/)
  intro/
    01-what-is-os.tex          what an OS is, what happens when you run ls
    02-interacting.tex         interrupts, system calls vs. library calls, kernel and user mode, fopen()
    03-abstractions.tex        processes, files, address spaces, protection
  ch2-process-management.tex   Chapter 2 (sections are in process/)
  process/
    01-program-to-process.tex  compiling and linking, what a process is
    02-fork-exec.tex           fork(), exec*(), system(), wait(), copy-on-write
    03-kernel-view.tex         task_struct, file descriptors, dup2(), how a syscall is handled
    04-syscall-internals.tex   fork/execve/exit/wait inside the kernel, zombies
    05-signals.tex             signals and job control
    06-organization.tex        booting, init, orphans, the process tree
    07-scheduling.tex          process states, context switches, scheduling policies up to MLFQ
  appA-syscalls.tex            Appendix A: quick reference for the system calls
```

## Building

You need TeX Live with `latexmk`.

```sh
latexmk -pdf main.tex   # builds main.pdf
latexmk -c              # cleans up the aux files
```

When the course moves on, a new topic in an existing deck gets its own file (e.g. `chapters/process/08-ipc.tex`, starting with `\section{...}`) and an `\input` line in the chapter file. A new deck gets a new `chapters/chN-topic.tex` with a `\chapter{...}`, a folder for its sections, and an `\include` in `main.tex`.
