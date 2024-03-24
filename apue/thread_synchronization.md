When there are multiple threads running in the same time, which thread would run first is questionable(For it is unable to tell the order of the cpu time allocation  to the thread ). So when we talk about multi-threading synchronization, we're actually talking about that the operation on the thread-shared-data has to be done in one thread at a time. if some parts of the operation is done in one thread and the other is dome in another thread, the final result would be uncertained.

# Lock

A pretty ancient and still widly used way to synchronize message between threads. The key concept is: if the thread acquired the lock, the thread keep running. Otherwise the thread is blocked until the lock is released. There are few locks that is oftenly used:

## Mutex

If a thread owns a mutex (firstly lock the mutex, in other word), the thread would keep going. Otherwise, it would be block until the lock is released.
