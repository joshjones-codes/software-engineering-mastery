# Operating Systems

Book: *Operating Systems: Three Easy Pieces* (free online). Ends with the runtime you actually ship.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Processes & Threads](01-processes-and-threads.md) | 🔴 must | ~2 wknds | OSTEP virtualization chapters · fork/exec, threads vs processes |
| [Scheduling](02-scheduling.md) | 🟡 should | ~1 wknd | context switching, schedulers, priority |
| [Memory Management](03-memory-management.md) | 🔴 must | ~2 wknds | virtual memory, paging, stack vs heap — what your variables actually are |
| [Concurrency Primitives](04-concurrency-primitives.md) | 🔴 must | ~2 wknds | locks, semaphores, condition variables, race conditions · build: worker pool with a thread-safe queue |
| [Filesystems](05-filesystems.md) | 🟡 should | ~1 wknd | inodes, journaling, fsync — why databases care |
| [Node.js Runtime Internals](06-nodejs-runtime-internals.md) | 🔴 must | ~2 wknds | event loop phases, libuv, streams & backpressure, worker threads — deep in YOUR runtime |
