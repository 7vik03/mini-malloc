# mini-malloc

A memory allocator library built from scratch in C to understand how malloc, free, and memory management actually work.

## What I'm Implementing

### Core Functions
- malloc (allocate memory)
- free (release memory)
- realloc (resize allocation)
- calloc (allocate + zero initialize)

### Allocator Types (Cause different problems need different solutions)
- **Free List** - General purpose, first-fit/best-fit search
- **Arena** - Bump pointer allocation, bulk free
- **Pool** - Fixed-size blocks, O(1) alloc/free
- **Stack** - LIFO allocation, scratch memory
- **Buddy System** - Power-of-2 blocks, split/merge

### Internals
- Block headers (size, flags)
- Block splitting (break large blocks)
- Coalescing (merge adjacent free blocks)
- Memory alignment (8/16 byte)
- sbrk/mmap system calls

### Debug Tools
- Leak detector (track allocations, report leaks)
- Heap visualizer (print memory layout)
- Corruption checker (detect buffer overflows)
- Allocation statistics

### Benchmarks
- Throughput (allocations per second)
- Fragmentation comparison
- Performance vs glibc malloc

### Advanced (Feeling Lucky)
- **Thread-Safe Allocator** - Mutex locks, per-thread arenas, lock-free free list
- **Garbage Collector** - Mark-and-sweep, reference counting, root set scanning

## Resources
- [malloc tutorial (danluu)](https://danluu.com/malloc-tutorial/) - Primary reference
- [Write a simple memory allocator](https://arjunsreedharan.org/post/148675821737/write-a-simple-memory-allocator) - Step-by-step guide
- [glibc malloc internals](https://sourceware.org/glibc/wiki/MallocInternals) - How real malloc works
- [Jacob Sorber](https://www.youtube.com/c/JacobSorber) - Memory videos
- [Baby's First Garbage Collector](https://journal.stuffwithstuff.com/2013/12/08/babys-first-garbage-collector/) - GC tutorial
- [tcmalloc](https://google.github.io/tcmalloc/design.html) - Thread-caching malloc design
